---
title: Compilação baseada em gráfico
description: Explica o conceito e o funcionamento da compilação baseada em gráfico.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 4%

---

# Compilação baseada em gráfico

Na compilação baseada em gráfico, especifique um conjunto de dados de evento. E, para esse conjunto de dados de evento, você especifica a ID persistente (cookie) e o namespace de compilação desejado no gráfico de identidade que contém os valores de ID de pessoa. A compilação baseada em gráfico adiciona uma nova coluna para a ID compilada ao conjunto de dados do evento. A ID persistente é usada para consultar o gráfico de identidade do Experience Platform Identity Service, usando o namespace de compilação especificado, para atualizar a ID compilada.


![Compilação baseada em gráfico](/help/stitching/assets/gbs.png)

## IdentityMap

A compilação baseada em gráfico oferece suporte ao uso do [`identityMap` grupo de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) nos seguintes cenários:

- Uso da identidade primária em `identityMap` namespaces para definir a persistentID:
   - Se várias identidades primárias forem encontradas em namespaces diferentes, as identidades nos namespaces serão classificadas lexicograficamente e a primeira identidade será selecionada.
   - Se várias identidades primárias forem encontradas em um único namespace, a primeira identidade primária lexicográfica disponível será selecionada.

  No exemplo abaixo, os namespaces e as identidades resultam em uma lista de identidades primárias classificada e, por fim, na identidade selecionada.

  <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Lista de identidades</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Lista de identidades classificadas</th>
      <th>Identidade selecionada</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>

- Uso do namespace `identityMap` para definir a persistentID:
   - Se vários valores para persistentID forem encontrados em um namespace `identityMap`, a primeira identidade lexicográfica disponível será usada.

  No exemplo abaixo, você selecionou ECID como o namespace a ser usado. Essa seleção resulta em uma lista de identidades classificadas e, por fim, na identidade selecionada.

  <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Lista de identidades</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Lista de identidades classificadas</th>
      <th>Identidade selecionada</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>


## Como funciona a compilação baseada em gráfico

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que elas chegam, usando a ID persistente para pesquisar a ID de pessoa para o namespace selecionado, consultando o gráfico de identidade. Se a ID de pessoa estiver disponível na pesquisa, essa ID de pessoa será compilada imediatamente.

- **Repetir compilação**: *repete* dados com base em identidades atualizadas do gráfico de identidade. É nesse estágio que as ocorrências de dispositivos anteriormente desconhecidos (IDs persistentes) são compiladas, pois o gráfico de identidade resolveu a identidade de um namespace. Dois parâmetros determinam a repetição: **frequência** e **janela de pesquisa**. A Adobe oferece as seguintes combinações desses parâmetros:
   - **Pesquisa diária em uma frequência diária**: os dados são repetidos todos os dias com uma janela de pesquisa de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os perfis não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Pesquisa semanal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa semanal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.
   - **Pesquisa quinzenal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa quinzenal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de duas semanas não são reprocessados até a próxima repetição semanal.
   - **Pesquisa mensal em uma frequência semanal**: os dados são repetidos todas as semanas com uma janela de pesquisa mensal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de um mês não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada do conjunto de dados de origem, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita. Além disso, a identidade deve ser removida do gráfico de identidade para evitar futuras compilações baseadas em gráfico para essa identidade específica.

  >[!IMPORTANT]
  >
  >O processo de descompilação, como parte das solicitações de privacidade, muda no início de 2025. O processo de descompilação atual recompila os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
  > 

Os dados além da janela de pesquisa não são repetidos. Um perfil deve ser autenticado em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

Considere as duas atualizações de gráfico de identidade a seguir ao longo do tempo para o visitante A (com ID persistente `246`) e o visitante B (com ID persistente `3579`) e como essas atualizações afetam as etapas na compilação baseada em gráfico.

![Gráfico de identidade 3579](assets/identity-graphs.svg)

Você pode exibir um gráfico de identidade ao longo do tempo para um perfil específico usando o [Visualizador de Gráficos de Identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulte também [Lógica de vinculação do serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) para entender melhor a lógica usada ao vincular identidades.

### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento, após a coleção, às informações conhecidas no momento do gráfico de identidade.

+++ Detalhes

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID compilada (após compilação em tempo real) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) *indefinida* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) *indefinida* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Você pode ver como a ID compilada é resolvida para cada evento. Com base no horário, na ID persistente e na pesquisa do gráfico de identidade para o namespace especificado (nesse mesmo momento).
Quando a pesquisa é resolvida para mais de uma id compilada (como para o evento 7), a primeira id lexicográfica retornada pelo gráfico de identidade é selecionada (`a.b@yahoo.co.uk` no exemplo).

+++

### Etapa 2: Repetir a compilação

Em intervalos regulares (dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base na versão mais recente do gráfico de identidade, no momento do intervalo.

+++ Detalhes

Com uma repetição da compilação em 2023-05-13 16:30, com uma configuração de janela de retrospectiva de 24 horas, alguns eventos da amostra são recompilados (indicado por ![Reproduzir](/help/assets/icons/Replay.svg)).

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID compilada<br/> (após compilação em tempo real) | ID compilada<br/> (após 24 horas de repetição) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Repetir](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Repetir](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Repetir](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg)`a.b@yahoo.co.uk`<br/>`246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Com a repetição da compilação em 2023-05-13 16:30, com uma configuração de janela de retrospectiva de 7 dias, todos os eventos da amostra são recompilados.


| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID compilada<br/> (após compilação em tempo real) | ID compilada<br/> (após 7 dias de repetição) |
|---|---|---|---|---|---|
| ![Repetir](/help/assets/icons/Replay.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) *indefinida* | `246` | `a.b@yahoo.co.uk` |
| ![Repetir](/help/assets/icons/Replay.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](/help/assets/icons/Replay.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](/help/assets/icons/Replay.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Repetir](/help/assets/icons/Replay.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Repetir](/help/assets/icons/Replay.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](/help/assets/icons/Replay.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade (por exemplo, em 2023-05-13 18:00) tem nos eventos de exemplo.

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![DataMapping](/help/assets/icons/DataMapping.svg) | ID com título (após solicitação de privacidade) |
|--:|---|---|---|---|
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 2 | 2023-05-12 14:00 | `246` | `246`![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Ramificação1](/help/assets/icons/Branch1.svg) `ted.w@gmail.com` | `3579` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk` | `246` |
| ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Ramificação1](/help/assets/icons/Branch1.svg) `a.b@yahoo.co.uk`<br/>`246` ![Ramificação1](/help/assets/icons/Branch1.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Pré-requisitos

Os seguintes pré-requisitos se aplicam especificamente à compilação baseada em gráfico:

- O conjunto de dados de evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter uma coluna que identifique um perfil em cada linha, a **ID persistente**. Por exemplo, uma ID de visitante gerada por uma biblioteca AppMeasurement do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Experience Platform.
- O gráfico de identidade do Experience Platform Identity Service deve ser configurado no nível da sandbox, antes de ativar a compilação baseada em gráfico.
   - O gráfico de identidade deve ter um namespace (por exemplo, `Email` ou `Phone`) que você deseja usar durante a compilação para resolver a ID de pessoa.
   - O gráfico de identidade deve ser preenchido com informações de identidades de qualquer conjunto de dados relevante (do tipo *evento* ou *perfil* e que contenha pelo menos dois namespaces úteis com valores de ID).
   - Todos os conjuntos de dados que contêm essas identidades relevantes devem ser [habilitados para assimilação de dados do gráfico de identidade](faq.md#enable-a-dataset-for-the-identity-service). Essa ativação garante que as identidades recebidas sejam adicionadas ao gráfico ao longo do tempo de todas as fontes necessárias.
   - Se você já estiver usando o Perfil de dados do cliente em tempo real ou o Adobe Journey Optimizer por algum tempo, o gráfico já deverá estar configurado até certo ponto.<br/>Se o preenchimento retroativo de compilação histórica também for necessário para o conjunto de dados habilitado com compilação baseada em gráfico, o gráfico já deverá conter identidades históricas para todo o período para obter os resultados de compilação desejados.
- Se quiser usar a compilação com base em gráficos e antecipar que o conjunto de dados do evento contribua para o gráfico de identidade, você deve [habilitar o conjunto de dados para o Serviço de identidade](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
- A ID persistente e a ID de pessoa podem ser usadas com [identityMap](#identitymap). Ou a ID persistente e a ID de pessoa podem ser campos do esquema XDM, nesse caso, os campos devem ser [definidos como uma identidade](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity?lang=en) no esquema.

>[!NOTE]
>
>Você **não** precisa de uma licença da Real-time Customer Data Platform para a compilação baseada em gráfico. O pacote **Prime** ou posterior do Customer Journey Analytics inclui os direitos necessários do Experience Platform Identity Service.


## Limitações

As seguintes limitações se aplicam especificamente à compilação baseada em gráfico:

- Os carimbos de data e hora não são considerados ao consultar a ID de pessoa usando o namespace especificado. Portanto, é possível que uma ID persistente seja compilada com uma ID de pessoa de um registro que tenha um carimbo de data e hora anterior.
- Em cenários de dispositivos compartilhados, em que o namespace no gráfico contém várias identidades, a primeira identidade lexicográfica é usada. Se as prioridades e os limites de namespace forem configurados como parte do lançamento das regras de vinculação de gráficos, a identidade do último usuário autenticado será usada. Consulte [Dispositivos compartilhados](/help/use-cases/stitching/shared-devices.md) para obter mais informações.
- Há um limite rígido de três meses de preenchimento retroativo de identidades no gráfico de identidade. Você usaria o preenchimento retroativo de identidades caso não estivesse usando um aplicativo da Experience Platform, como a Real-time Customer Data Platform, para preencher o gráfico de identidade.
- As [medidas de proteção do Serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) se aplicam. Consulte, por exemplo, os [seguintes limites estáticos](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Número máximo de identidades em um gráfico: 50.
   - Número máximo de links para uma identidade para uma única assimilação de lote: 50.
   - Número máximo de identidades em um registro XDM para assimilação de gráfico: 20.
   - Número mínimo de identidades em um registro XDM para assimilação de gráfico: 2.
