---
title: Compilação baseada em gráfico
description: Explicação da compilação baseada em gráfico
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 7%

---

# Compilação baseada em gráfico


Na compilação baseada em gráfico, você especifica um conjunto de dados de evento, bem como a ID persistente (cookie) e o namespace da ID transitória (ID de pessoa) para esse conjunto de dados. A compilação baseada em gráfico cria uma nova coluna para a ID compilada no novo conjunto de dados compilado. Em seguida, o usa a ID persistente para consultar o gráfico de identidade do Serviço de identidade do Experience Platform, usando o namespace especificado, para atualizar a ID compilada.

![Compilação baseada em gráfico](/help/stitching/assets/gbs.png)

## Como funciona a compilação baseada em gráfico

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que elas chegam, usando a ID persistente para pesquisar a ID transitória do namespace selecionado, consultando o gráfico de identidade. Se a ID transitória estiver disponível na pesquisa, essa ID transitória será imediatamente compilada.

- **Repetir compilação**: *repete* dados com base em identidades atualizadas do gráfico de identidade. É nesse estágio que as ocorrências de dispositivos anteriormente desconhecidos (IDs persistentes) são compiladas, pois o gráfico de identidade resolveu a identidade de um namespace. A repetição é determinada por dois parâmetros: **frequência** e **janela de pesquisa**. Adobe oferece as seguintes combinações desses parâmetros:
   - **Pesquisa diária em uma frequência diária**: os dados são repetidos todos os dias com uma janela de pesquisa de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os visitantes não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Pesquisa semanal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa semanal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.
   - **Pesquisa quinzenal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa quinzenal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de duas semanas não são reprocessados até a próxima repetição semanal.
   - **Pesquisa mensal em uma frequência semanal**: os dados são repetidos todas as semanas com uma janela de pesquisa mensal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de um mês não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada do conjunto de dados de origem, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita. Além disso, a identidade deve ser removida do gráfico de identidade para evitar futuras compilações baseadas em gráfico para essa identidade específica.

  >[!IMPORTANT]
  >
  >O processo de descompilação, como parte das solicitações de privacidade, muda no início de 2025. O processo de descompilação atual recompila os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
  > 

Os dados além da janela de pesquisa não são repetidos. Um visitante deve se autenticar em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

Considere os dois gráficos de identidade a seguir para a ID persistente `246` e `3579`, como esses gráficos de identidade são atualizados ao longo do tempo e como essas atualizações afetam as etapas na compilação baseada em gráfico.

![Gráfico de identidade 246](assets/identity-graph-246.svg)
![Gráfico de identidade 3579](assets/identity-graph-3579.svg)

Você pode exibir um gráfico de identidade ao longo do tempo para um perfil específico usando o [Visualizador de Gráficos de Identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulte também [Lógica de vinculação do serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) para entender melhor a lógica usada ao vincular identidades.

### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento, após a coleção, às informações conhecidas no momento do gráfico de identidade.

+++ Detalhes

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada (após compilação em tempo real) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *indefinido* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *indefinido* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Você pode ver como a ID compilada é resolvida para cada evento. Com base no horário, na ID persistente e na pesquisa do gráfico de identidade para o namespace especificado (nesse mesmo momento).
Quando a pesquisa é resolvida para mais de uma id compilada (como para o evento 7), a primeira id lexicográfica retornada pelo gráfico de identidade é selecionada (`a.b@yahoo.co.uk` no exemplo).

+++

### Etapa 2: Repetir a compilação

Em intervalos regulares (dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base na versão mais recente do gráfico de identidade, no momento do intervalo.

+++ Detalhes

Com uma repetição da compilação ocorrendo às 16:30 do dia 2023-05-13, com uma configuração de janela de retrospectiva de 24 horas, alguns eventos da amostra são recompilados (indicado por ![Reproduzir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada<br/> (após compilação em tempo real) | ID compilada<br/> (após 24 horas de repetição) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Com a repetição da compilação em 2023-05-13 às 16:30, com uma configuração de janela de retrospectiva de 7 dias, todos os eventos da amostra são recompilados.


| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada<br/> (após compilação em tempo real) | ID compilada<br/> (após 7 dias de repetição) |
|---|---|---|---|---|---|
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *indefinido* | `246` | `a.b@yahoo.co.uk` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Repetir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade (por exemplo, em 2023-05-13 18:00) tem nos eventos de amostra.

| | Hora | ID Persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID com título (após solicitação de privacidade) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Pré-requisitos

Os seguintes pré-requisitos se aplicam especificamente à compilação baseada em gráfico:

- O conjunto de dados de evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter uma coluna que identifique um visitante em cada linha, a **ID persistente**. Por exemplo, uma ID de visitante gerada por uma biblioteca de AppMeasurements Adobe Analytics ou uma ECID gerada pelo Serviço de identidade Experience Platform.
- A ID persistente também deve ser [definida como uma identidade](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) no esquema.
- O gráfico de identidade do Experience Platform Identity Service deve ter um namespace (por exemplo, `Email` ou `Phone`) que você deseja usar durante a compilação para resolver a **ID transitória**. Consulte [Experience Platform Identity Service](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/home) para obter mais informações.

>[!NOTE]
>
>Você **não** precisa de uma licença Real-time Customer Data Platform para compilações baseadas em gráficos. O pacote **Prime** ou posterior de Customer Journey Analytics inclui os direitos necessários para o Serviço de Identidade de Experience Platform.


## Limitações

As seguintes limitações se aplicam especificamente à compilação baseada em gráfico:

- Os carimbos de data e hora não são considerados ao consultar a ID transitória usando o namespace especificado. Portanto, é possível que uma ID persistente seja compilada com uma ID transitória de um registro que tenha um carimbo de data e hora anterior.
- Sem suporte a dispositivo compartilhado. Quando várias identidades são retornadas, ao consultar o gráfico de identidade usando um namespace, a primeira identidade lexicográfica é usada.
- Há um limite rígido de três meses de preenchimento retroativo de identidades no gráfico de identidade. Caso não esteja usando um aplicativo Experience Platform, como o Real-time Customer Data Platform, para preencher o gráfico de identidade, você usaria identidades de preenchimento retroativo.
- As [medidas de proteção do Serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) se aplicam. Consulte, por exemplo, os [seguintes limites estáticos](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Número máximo de identidades em um gráfico: 50.
   - Número máximo de links para uma identidade para uma única assimilação de lote: 50.
   - Número máximo de identidades em um registro XDM para assimilação de gráfico: 20.
   - Número mínimo de identidades em um registro XDM para assimilação de gráfico: 2.