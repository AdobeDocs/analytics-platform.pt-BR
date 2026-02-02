---
title: Compilação em campo
description: Explica o conceito e o funcionamento da compilação em campo.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 9%

---

# Compilação em campo

Na compilação em campo, você especifica um conjunto de dados de evento, bem como a ID persistente (cookie) e a ID de pessoa para esse conjunto de dados. A compilação em campo adiciona uma nova coluna de ID compilada ao conjunto de dados do evento e atualiza essa ID compilada com base em linhas que têm uma ID de pessoa para essa ID persistente específica. <br/>Você pode usar a compilação em campo ao usar o Customer Journey Analytics como uma solução independente (sem acesso ao Serviço de Identidade da Experience Platform e ao gráfico de identidade associado). Ou quando não quiser usar o gráfico de identidade disponível.

![Compilação em campo](/help/stitching/assets/fbs.png)


## IdentityMap

A compilação em campo oferece suporte ao uso do [`identityMap` grupo de campos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition#identity) nos seguintes cenários:

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


- Uso do namespace `identityMap` para definir a ID persistente, a ID de pessoa ou ambas:
   - Se vários valores de ID persistente ou ID de pessoa forem encontrados em um namespace `identityMap`, o primeiro valor lexicográfico disponível será usado.
   - Os namespaces da ID persistente e da ID de pessoa devem ser mutuamente exclusivos.

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

## Como funciona a compilação em campo

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que elas chegam. As ocorrências de dispositivos que são *novos* para o conjunto de dados (nunca foram autenticadas) normalmente não são compiladas neste nível. As ocorrências de dispositivos já reconhecidos são compiladas imediatamente.

- **Repetir compilação**: *repete* dados com base em identificadores exclusivos (IDs de pessoa). É nesse estágio que as ocorrências de dispositivos anteriormente desconhecidos (IDs persistentes) se tornam compiladas (para IDs de pessoa). Dois parâmetros determinam a repetição: **frequência** e **janela de pesquisa**. A Adobe oferece as seguintes combinações desses parâmetros:
   - **Pesquisa diária em uma frequência diária**: os dados são repetidos todos os dias com uma janela de pesquisa de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os perfis não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Pesquisa semanal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa semanal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.
   - **Pesquisa quinzenal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa quinzenal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de duas semanas não são reprocessados até a próxima repetição semanal.
   - **Pesquisa mensal em uma frequência semanal**: os dados são repetidos todas as semanas com uma janela de pesquisa mensal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de um mês não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita.

  >[!IMPORTANT]
  >
  >O processo de descompilação, como parte das solicitações de privacidade, muda no início de 2025. O processo de descompilação atual recompila os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
  > 


Os dados além da janela de pesquisa não são repetidos. Um perfil deve ser autenticado em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento após a coleção em dispositivos e canais conhecidos.

+++ Detalhes

Considere o exemplo a seguir, em que Bob registra eventos diferentes como parte de um conjunto de dados de evento.

*Dados como aparecem no dia em que são coletados:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID da pessoa | ID compilada (após compilação em tempo real) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivos** | | **4 pessoas**:<br/>`246`, `Bob`, `3579`, `81911` |

Os eventos não autenticados e autenticados em novos dispositivos são contados como pessoas separadas (temporariamente). Eventos não autenticados em dispositivos reconhecidos são compilados em tempo real.

A atribuição funciona quando a variável personalizada de identificação está vinculada a um dispositivo. No exemplo acima, todos os eventos, exceto o 1, 8, 9 e 10, são compilados em tempo real (todos eles usam o identificador `Bob`). A compilação em tempo real &quot;resolve&quot; a ID compilada para o evento 4, 6 e 12.

Os dados atrasados (dados com um carimbo de data e hora superior a 24 horas) são tratados com base no &quot;melhor esforço&quot;, priorizando a compilação de dados atuais para obter a mais alta qualidade.

+++ 

### Etapa 2: Repetir a compilação

Em intervalos regulares (uma vez por semana ou uma vez por dia, dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base nos dispositivos que agora ela reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, a repetição da compilação vinculará esses eventos não autenticados à pessoa correta.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID da pessoa | ID compilada (após compilação em tempo real) | ID compilada (após repetição) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Seta para cima](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | `Bob` ![Seta para cima](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>`246`, `Bob`, `3579`, `81911` | **2 pessoas**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

A atribuição funciona quando a variável personalizada de identificação está vinculada a um dispositivo. No exemplo acima, o evento 1 e 10 são compilados como resultado da repetição, deixando apenas o evento 8 e o 9 não compilados. E reduzindo a métrica de pessoas (cumulativa) para 2.

+++ 

### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade para Bob tem nos dados após o processamento. As linhas em que Bob é autenticado são removidas (2, 3, 5, 7 e 11) juntamente com a remoção de Bob como uma ID de pessoa para outras linhas.

*Os mesmos dados após uma solicitação de privacidade para Bob:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID da pessoa | ID compilada (após compilação em tempo real) | ID compilada (após repetição) | ID da pessoa | ID com título (após solicitação de privacidade) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Seta para Cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![SetaDireita](/help/assets/icons/ArrowRight.svg) | `Bob` ![Seta para baixo](/help/assets/icons/ArrowDown.svg) | `Bob` ![Seta para cima](/help/assets/icons/ArrowUp.svg) | ![RemoverCírculo](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246, `Bob`, `3579`, `81911` | **2 pessoas**:<br/>Bob, `3579` |  | **3 pessoas**:<br/>`246`, `3579`, `81911` |

+++ 

## Pré-requisitos

Os seguintes pré-requisitos se aplicam especificamente à compilação em campo:

- O conjunto de dados do evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter duas colunas que ajudem a identificar perfis:

   - Uma **ID persistente**, um identificador disponível em cada linha. Por exemplo, uma ID de visitante gerada por uma biblioteca AppMeasurement do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Adobe Experience Platform.
   - Uma **ID de pessoa**, um identificador disponível em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash depois que um perfil é autenticado. Você pode usar praticamente qualquer identificador que desejar. A compilação considera esse campo como mantendo as informações reais da ID de pessoa. Para obter melhores resultados de compilação, uma ID de pessoa deve ser enviada nos eventos do conjunto de dados pelo menos uma vez para cada ID persistente. Se você planeja incluir esse conjunto de dados em uma conexão do Customer Journey Analytics, é preferível que os outros conjuntos de dados também tenham um identificador comum semelhante.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Limitações

As seguintes limitações se aplicam especificamente à compilação em campo:

- Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID de pessoa). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID de pessoa e, em seguida, para outra ID de pessoa) não é suportado.
- Se várias pessoas compartilharem um dispositivo e o número total de transições entre usuários exceder 50.000, o Customer Journey Analytics interromperá a compilação de dados para esse dispositivo.
- Não há suporte para mapas de ID personalizados usados em sua organização.
- A compilação diferencia maiúsculas e minúsculas. Para conjuntos de dados gerados por meio do conector de origem do Analytics, a Adobe recomenda revisar quaisquer regras VISTA ou regras de processamento que se aplicam ao campo de ID de pessoa. Essa revisão garante que nenhuma dessas regras introduza novos formulários da mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas no campo de ID de pessoa em apenas uma parte dos eventos.
- A compilação não combina nem concatena campos.
- O campo de ID de pessoa deve conter um único tipo de ID (IDs de um único namespace). Por exemplo, o campo ID de pessoa não deve conter uma combinação de IDs de logon e IDs de email.
- Se vários eventos ocorrerem com o mesmo carimbo de data e hora para a mesma ID persistente, mas com valores diferentes no campo de ID de pessoa, a compilação selecionará a ID com base na ordem alfabética. Portanto, se a ID persistente A tiver dois eventos com o mesmo carimbo de data e hora e um dos eventos especificar Bob e o outro especificar Ann, a compilação selecionará Ann.
- Tenha cuidado com cenários em que as IDs de pessoa contêm valores de espaço reservado, por exemplo `Undefined`. Consulte as [Perguntas frequentes](faq.md) para obter mais informações.
- Não é possível usar o mesmo namespace para a ID persistente e a ID de pessoa. Os namespaces precisam ser mutuamente exclusivos.
