---
title: Compilação em campo
description: Explicação da compilação em campo
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Compilação em campo

Na compilação em campo, você especifica um conjunto de dados de evento, bem como a ID persistente (cookie) e a ID transitória (ID de pessoa) para esse conjunto de dados. A compilação em campo cria uma nova coluna de ID compilada no novo conjunto de dados compilado e atualiza essa coluna de ID compilada com base em linhas que têm uma ID transitória para essa ID persistente específica. <br/>Você pode usar a compilação em campo ao usar o Customer Journey Analytics como uma solução independente (sem acesso ao Serviço de Identidade do Experience Platform e ao gráfico de identidade associado). Ou quando não quiser usar o gráfico de identidade disponível.

![Compilação em campo](/help/stitching/assets/fbs.png)

## Como funciona a compilação em campo

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que elas chegam. As ocorrências de dispositivos que são &quot;novas&quot; para o conjunto de dados (nunca foram autenticadas) normalmente não são compiladas neste nível. As ocorrências de dispositivos já reconhecidos são compiladas imediatamente.

- **Repetir compilação**: &quot;repete&quot; dados com base em identificadores exclusivos (IDs transitórias) que ele aprendeu. É nesse estágio que as ocorrências de dispositivos desconhecidos anteriormente (IDs persistentes) são compiladas (em IDs transitórias). A repetição é determinada por dois parâmetros: **frequência** e **janela de pesquisa**. Adobe oferece as seguintes combinações desses parâmetros:
   - **Pesquisa diária em uma frequência diária**: os dados são repetidos todos os dias com uma janela de pesquisa de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os visitantes não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Pesquisa semanal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa semanal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.
   - **Pesquisa quinzenal em uma frequência semanal**: os dados são repetidos uma vez por semana com uma janela de pesquisa quinzenal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de duas semanas não são reprocessados até a próxima repetição semanal.
   - **Pesquisa mensal em uma frequência semanal**: os dados são repetidos todas as semanas com uma janela de pesquisa mensal (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de um mês não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita.

  >[!IMPORTANT]
  >
  >O processo de descompilação, como parte das solicitações de privacidade, muda no início de 2025. O processo de descompilação atual recompila os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
  > 


Os dados além da janela de pesquisa não são repetidos. Um visitante deve se autenticar em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento após a coleção em dispositivos e canais conhecidos.

+++ Detalhes

Considere o exemplo a seguir, em que Bob registra eventos diferentes como parte de um conjunto de dados de evento.

*Dados como aparecem no dia em que são coletados:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
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

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Seta para Cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Seta para Cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>`246`, `Bob`, `3579`, `81911` | **2 pessoas**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

A atribuição funciona quando a variável personalizada de identificação está vinculada a um dispositivo. No exemplo acima, o evento 1 e 10 são compilados como resultado da repetição, deixando apenas o evento 8 e o 9 não compilados. E reduzindo a métrica de pessoas (cumulativa) para 2.

+++

### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade para Bob tem nos dados após o processamento. As linhas em que Bob é autenticado são removidas (2, 3, 5, 7 e 11) juntamente com a remoção de Bob como uma ID transitória para outras linhas.

*Os mesmos dados após uma solicitação de privacidade para Bob:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) | ID transitória (ID de logon) | ID com título (após solicitação de privacidade) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Seta para Cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a Direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Seta para Cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246, `Bob`, `3579`, `81911` | **2 pessoas**:<br/>Bob, `3579` |  | **3 pessoas**:<br/>`246`, `3579`, `81911` |

+++

## Pré-requisitos

Os seguintes pré-requisitos se aplicam especificamente à compilação em campo:

- O conjunto de dados do evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter duas colunas que ajudem a identificar visitantes:

   - Uma **ID persistente**, um identificador disponível em cada linha. Por exemplo, uma ID de visitante gerada por uma biblioteca de AppMeasurements do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Adobe Experience Platform.
   - Uma **ID transitória**, um identificador disponível em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash quando um visitante é autenticado. Você pode usar praticamente qualquer identificador que desejar. A compilação considera esse campo como mantendo as informações reais da ID de pessoa. Para obter melhores resultados de compilação, uma ID transitória deve ser enviada nos eventos do conjunto de dados pelo menos uma vez para cada ID persistente. Se você planeja incluir esse conjunto de dados em uma conexão Customer Journey Analytics, é preferível que os outros conjuntos de dados também tenham um identificador comum semelhante.

- Ambas as colunas (ID persistente e ID transitória) devem ser definidas como um campo de identidade com um namespace de identidade no esquema para o conjunto de dados que você deseja compilar. Ao usar a identificação de identidade na Real-time Customer Data Platform, usando o [`identityMap` grupo de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), você ainda precisará adicionar campos de identidade com um namespace de identidade. Essa identificação de campos de identidade é necessária, pois a compilação de Customer Journey Analytics não oferece suporte ao grupo de campos `identityMap`. Ao adicionar um campo de identidade no esquema, ao mesmo tempo em que usa o grupo de campos `identityMap`, não defina o campo de identidade adicional como uma identidade primária. Definir um campo de identidade adicional como identidade primária interfere no grupo de campos `identityMap` usado para o Real-time Customer Data Platform.

## Limitações

As seguintes limitações se aplicam especificamente à compilação em campo:

- Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID transitória). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID transitória e, em seguida, para outra ID transitória) não é suportado.
- Se um dispositivo for compartilhado por várias pessoas e o número total de transições entre usuários exceder 50.000, o Customer Journey Analytics interromperá a compilação de dados para esse dispositivo.
- Não há suporte para mapas de ID personalizados usados em sua organização.
- A compilação diferencia maiúsculas e minúsculas. Para conjuntos de dados gerados pelo conector de origem do Analytics, o Adobe recomenda revisar todas as regras VISTA ou regras de processamento que se aplicam ao campo de ID transitória. Essa revisão garante que nenhuma dessas regras introduza novos formulários da mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas no campo de ID transitória em apenas uma parte dos eventos.
- A compilação não combina nem concatena campos.
- O campo de ID transitória deve conter um único tipo de ID (IDs de um único namespace). Por exemplo, o campo ID transitória não deve conter uma combinação de IDs de logon e IDs de email.
- Se vários eventos ocorrerem com o mesmo carimbo de data e hora para a mesma ID persistente, mas com valores diferentes no campo de ID transitória, a compilação selecionará a ID com base na ordem alfabética. Portanto, se a ID persistente A tiver dois eventos com o mesmo carimbo de data e hora e um dos eventos especificar Bob e o outro especificar Ann, a compilação selecionará Ann.
- Tenha cuidado com cenários em que as IDs transitórias contenham valores de espaço reservado, por exemplo `Undefined`. Consulte as [Perguntas frequentes](faq.md) para obter mais informações.

