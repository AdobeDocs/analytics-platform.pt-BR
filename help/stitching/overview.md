---
title: Visão geral da compilação
description: Visão geral da compilação.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 83e568d686a541bb6472a33dc0a7400cf6e8de2a
workflow-type: tm+mt
source-wordcount: '3712'
ht-degree: 12%

---

# Compilação

{{select-package}}

A compilação de identidade (ou simplesmente, compilação) é um recurso poderoso que eleva a adequação de um conjunto de dados de evento para análise entre canais. A análise entre canais é um caso de uso principal que o Customer Journey Analytics pode manipular, permitindo combinar e executar relatórios de maneira contínua em vários conjuntos de dados de diferentes canais, com base em um identificador comum (ID de pessoa).

Quando você combina conjuntos de dados com IDs de pessoa semelhantes, a atribuição é transportada entre dispositivos e canais. Por exemplo, um usuário visita o site pela primeira vez por meio de um anúncio no computador desktop. Esse usuário encontra um problema com seu pedido e, em seguida, faz uma chamada à equipe de atendimento ao cliente para ajudá-lo a resolver o problema. Com a análise entre canais, você pode atribuir eventos da central de atendimento ao anúncio em que eles clicaram originalmente.

Infelizmente, nem todos os conjuntos de dados baseados em eventos que fazem parte da sua conexão no Customer Journey Analytics estão preenchidos com dados suficientes para dar suporte a essa atribuição pronta para uso. Especialmente, os conjuntos de dados de experiência baseados na Web ou em dispositivos móveis geralmente não têm informações reais de ID de pessoa disponíveis em todos os eventos.

A compilação permite rechavear identidades em linhas de um conjunto de dados, garantindo que a ID de pessoa (ID compilada) esteja disponível em cada evento. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para determinar o valor da ID transitória comum (ID de pessoa) que pode ser usada como ID compilada. Esse rechaveamento permite resolver registros desiguais em uma única ID compilada para análise no nível da pessoa, em vez de no nível do dispositivo ou do cookie.

O Customer Journey Analytics oferece suporte a dois tipos de costura: compilação em campo e compilação em gráfico.

## Pré-requisitos 

>[!IMPORTANT]
>
>O não cumprimento de todos os pré-requisitos pode resultar na incapacidade de realizar a análise entre canais corretamente.

Antes de usar a compilação, verifique se sua organização está preparada com o seguinte:

- A compilação inclui a mesclagem de dados de usuário autenticados e não autenticados. Cumpra as leis e regulamentos aplicáveis e obtenha as permissões necessárias do usuário final antes de ativar a compilação em um conjunto de dados de evento. Consulte [Definir campos de identidade na interface](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/ui/fields/identity) para obter mais informações.

- Importe os dados desejados para o Adobe Experience Platform:

   - Para obter dados do Adobe Analytics, consulte [Utilização dos dados do conjunto de relatórios do Adobe Analytics no Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Para outros tipos de dados, consulte [Criar um esquema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) e [Assimilar dados](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) na documentação da Adobe Experience Platform.

Você se beneficia da análise entre canais se combinar um ou mais conjuntos de dados compilados com outros conjuntos de dados, como dados da central de atendimento, como parte da definição da conexão Customer Journey Analytics. Essa configuração de conexão pressupõe que esses outros conjuntos de dados já contenham uma ID de pessoa em cada linha, semelhante à ID compilada.


## Limitações

>[!IMPORTANT]
>
>- Não há suporte para usar o `identityMap` como a ID persistente. É necessário definir um identificador específico no conjunto de dados (por exemplo, `ECID`) como a ID persistente.
>
>- Aplique qualquer alteração feita ao esquema do conjunto de dados do evento de origem também ao novo esquema do conjunto de dados compilado, caso contrário, ela quebrará o conjunto de dados compilado.
>
>- Se você remover o conjunto de dados de origem, o conjunto de dados compilado parará de ser processado e será removido pelo sistema.
>
>- Os rótulos de uso de dados não são propagados automaticamente para o esquema do conjunto de dados compilado. Se você tiver rótulos de uso de dados aplicados ao esquema do conjunto de dados de origem, será necessário aplicar esses rótulos de uso de dados manualmente ao esquema do conjunto de dados compilado. Consulte [Gerenciamento de rótulos de uso de dados no Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) para obter mais informações.

A costura é um recurso inovador e robusto, mas tem limitações na forma de uso.

- Somente conjuntos de dados de evento são suportados. Outros conjuntos de dados, como conjuntos de dados de pesquisa, não são suportados.
- A compilação não transforma de maneira alguma o campo usado para compilação. A compilação usa o valor no campo especificado, como ele existe no conjunto de dados não compilado no data lake.
- O processo de compilação diferencia maiúsculas de minúsculas. Por exemplo, se às vezes aparecer no campo a palavra &quot;Bob&quot; e, às vezes, a palavra &quot;BOB&quot;, essas IDs serão tratadas como duas pessoas separadas.

Não confunda a compilação com:

- A mesclagem de dois ou mais conjuntos de dados. A compilação se aplica a apenas um conjunto de dados. A mesclagem de conjuntos de dados ocorre como resultado da configuração de uma conexão Customer Journey Analytics e da seleção da mesma ID de pessoa nos conjuntos de dados selecionados na conexão.

- A associação de dois conjuntos de dados. No Customer Journey Analytics, uma junção é frequentemente usada para pesquisas ou classificações no Analysis Workspace. Embora a compilação use a funcionalidade de associação, o próprio processo envolve mais do que associações.


## Compilação em campo

Você especifica um conjunto de dados de evento, bem como a ID persistente (cookie) e a ID transitória (ID de pessoa) para esse conjunto de dados. A compilação em campo cria uma nova coluna de ID compilada no novo conjunto de dados compilado e atualiza essa coluna de ID compilada com base em linhas que têm uma ID transitória para essa ID persistente específica. <br/>Você pode usar a compilação em campo ao usar o Customer Journey Analytics como uma solução independente (sem acesso ao Serviço de identidade do Experience Platform e ao gráfico de identidade associado). Ou quando não quiser usar o gráfico de identidade disponível.

![Compilação em campo](/help/stitching/assets/fbs.png)

### Como funciona a compilação em campo

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que ela chega. As ocorrências de dispositivos que são &quot;novas&quot; para o conjunto de dados (nunca foram autenticadas) normalmente não são compiladas neste nível. As ocorrências de dispositivos já reconhecidos são compiladas imediatamente.

- **Reproduzir compilação novamente**: &quot;repete&quot; dados com base em identificadores exclusivos (IDs transitórias) que ele aprendeu. É nesse estágio que as ocorrências de dispositivos desconhecidos anteriormente (IDs persistentes) são compiladas (em IDs transitórias). A Adobe oferece dois intervalos de repetição:
   - **Diariamente**: os dados são repetidos todos os dias com uma janela de retrospectiva de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os visitantes não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Semanalmente**: os dados são repetidos uma vez por semana com a janela de pesquisa selecionada (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita.

Os dados além da janela de pesquisa não são repetidos. Um visitante deve se autenticar em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

#### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento após a coleção em dispositivos e canais conhecidos.

+++ Detalhes

Considere o exemplo a seguir, em que Bob registra eventos diferentes como parte de um conjunto de dados de evento.

*Dados como aparecem no dia em que são coletados:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 dispositivos** | | **4 pessoas**:<br/>`246`, `Bob`, `3579`, `81911` |

Os eventos não autenticados e autenticados em novos dispositivos são contados como pessoas separadas (temporariamente). Eventos não autenticados em dispositivos reconhecidos são compilados em tempo real.

A atribuição funciona quando a variável personalizada de identificação está vinculada a um dispositivo. No exemplo acima, todos os eventos, exceto o 1, 8, 9 e 10, são compilados em tempo real (todos eles usam o `Bob` identificador). A compilação em tempo real &quot;resolve&quot; a ID compilada para o evento 4, 6 e 12.

Os dados atrasados (dados com um carimbo de data e hora superior a 24 horas) são tratados com base no &quot;melhor esforço&quot;, priorizando a compilação de dados atuais para obter a mais alta qualidade.

+++

#### Etapa 2: Repetir a compilação

Em intervalos regulares (uma vez por semana ou uma vez por dia, dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base nos dispositivos que agora ela reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, a repetição da compilação vinculará esses eventos não autenticados à pessoa correta.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>`246`, `Bob`, `3579`, `81911` | **2 pessoas**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

A atribuição funciona quando a variável personalizada de identificação está vinculada a um dispositivo. No exemplo acima, o evento 1 e 10 são compilados como resultado da repetição, deixando apenas o evento 8 e o 9 não compilados. E reduzindo a métrica de pessoas (cumulativa) para 2.

+++

#### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade para Bob tem nos dados após o processamento. As linhas em que Bob é autenticado são removidas (2, 3, 5, 7 e 11) juntamente com a remoção de Bob como uma ID transitória para outras linhas.

*Os mesmos dados após uma solicitação de privacidade para Bob:*

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) | ID transitória (ID de logon) | ID com título (após solicitação de privacidade) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246 `Bob`, `3579`, `81911` | **2 pessoas**:<br/>Bob, `3579` |  | **3 pessoas**:<br/>`246`, `3579`, `81911` |

+++

### Pré-requisitos 

Os seguintes pré-requisitos se aplicam especificamente à compilação em campo:

- O conjunto de dados do evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter duas colunas que ajudem a identificar visitantes:

   - A **ID persistente**, um identificador disponível em cada linha. Por exemplo, uma ID de visitante gerada por uma biblioteca de AppMeasurements do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Adobe Experience Cloud.
   - A **ID transitória**, um identificador disponível em apenas algumas linhas. Por exemplo, um nome de usuário ou endereço de email com hash quando um visitante é autenticado. Você pode usar praticamente qualquer identificador que desejar. A compilação considera esse campo como mantendo as informações reais da ID de pessoa. Para obter melhores resultados de compilação, uma ID transitória deve ser enviada nos eventos do conjunto de dados pelo menos uma vez para cada ID persistente. Se você planeja incluir esse conjunto de dados em uma conexão Customer Journey Analytics, é preferível que os outros conjuntos de dados também tenham um identificador comum semelhante.

- Ambas as colunas (ID persistente e ID transitória) devem ser definidas como um campo de identidade com um namespace de identidade no esquema para o conjunto de dados que você deseja compilar. Ao usar a compilação de identidade na Real-time Customer Data Platform, use o [`identityMap` grupo de campos](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), ainda será necessário adicionar campos de identidade com um namespace de identidade. Essa identificação de campos de identidade é necessária, pois a compilação de Customer Journey Analytics não é compatível com o `identityMap` grupo de campos. Ao adicionar um campo de identidade no esquema, ao mesmo tempo em que usa a variável `identityMap` grupo de campos, não defina o campo de identidade adicional como uma identidade primária. Definir um campo de identidade adicional como identidade primária interfere na `identityMap` grupo de campos usado para o Real-time Customer Data Platform.

### Limitações

As seguintes limitações se aplicam especificamente à compilação em campo:

- Os recursos atuais de rechaveamento são limitados a uma etapa (ID persistente para ID transitória). O rechaveamento de várias etapas (por exemplo, ID persistente para uma ID transitória e, em seguida, para outra ID transitória) não é suportado.
- Se um dispositivo for compartilhado por várias pessoas e o número total de transições entre usuários exceder 50.000, o Customer Journey Analytics interromperá a compilação de dados para esse dispositivo.
- Não há suporte para mapas de ID personalizados usados em sua organização.
- A compilação diferencia maiúsculas e minúsculas. Para conjuntos de dados gerados pelo conector de origem do Analytics, o Adobe recomenda revisar todas as regras VISTA ou regras de processamento que se aplicam ao campo de ID transitória. Essa revisão garante que nenhuma dessas regras introduza novos formulários da mesma ID. Por exemplo, você deve garantir que nenhuma regra VISTA ou de processamento introduza letras minúsculas no campo de ID transitória em apenas uma parte dos eventos.
- A compilação não combina nem concatena campos.
- O campo de ID transitória deve conter um único tipo de ID (IDs de um único namespace). Por exemplo, o campo ID transitória não deve conter uma combinação de IDs de logon e IDs de email.
- Se vários eventos ocorrerem com o mesmo carimbo de data e hora para a mesma ID persistente, mas com valores diferentes no campo de ID transitória, a compilação selecionará a ID com base na ordem alfabética. Portanto, se a ID persistente A tiver dois eventos com o mesmo carimbo de data e hora e um dos eventos especificar Bob e o outro especificar Ann, a compilação selecionará Ann.
- Tenha cuidado com cenários em que as IDs transitórias contenham valores de espaço reservado, por exemplo `Undefined`. Consulte a [Perguntas frequentes](faq.md) para obter mais informações.


## Compilação baseada em gráfico

Você especifica um conjunto de dados de evento, bem como a ID persistente (cookie) e o namespace da ID transitória (ID de pessoa) para esse conjunto de dados. A compilação baseada em gráfico cria uma nova coluna para a ID compilada no novo conjunto de dados compilado. Em seguida, o usa a ID persistente para consultar o gráfico de identidade do Serviço de identidade do Experience Platform, usando o namespace especificado, para atualizar a ID compilada.

![Compilação baseada em gráfico](/help/stitching/assets/gbs.png)

### Como funciona a compilação baseada em gráfico

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados.

- **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que elas chegam, usando a ID persistente para pesquisar a ID transitória do namespace selecionado, consultando o gráfico de identidade. Se a ID transitória estiver disponível na pesquisa, essa ID transitória será imediatamente compilada.

- **Reproduzir compilação novamente**: &quot;repete&quot; dados com base em identidades atualizadas do gráfico de identidade. É nesse estágio que as ocorrências de dispositivos anteriormente desconhecidos (IDs persistentes) são compiladas, pois o gráfico de identidade resolveu a identidade de um namespace. A Adobe oferece dois intervalos de repetição:
   - **Diariamente**: os dados são repetidos todos os dias com uma janela de retrospectiva de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os visitantes não autenticados devem se autenticar no mesmo dia em que visitam o site.
   - **Semanalmente**: os dados são repetidos uma vez por semana com a janela de pesquisa (consulte [opções](#options)). Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.

- **Privacidade**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada do conjunto de dados de origem, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita. Além disso, a identidade deve ser removida do gráfico de identidade para evitar futuras compilações baseadas em gráfico para essa identidade específica.

Os dados além da janela de pesquisa não são repetidos. Um visitante deve se autenticar em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

Considere os dois gráficos de identidade a seguir para a ID persistente `246` e `3579`, como esses gráficos de identidade são atualizados ao longo do tempo e como essas atualizações afetam as etapas da compilação baseada em gráficos.

![Gráfico de identidade 246](assets/identity-graph-246.svg)
![Gráfico de identidade 3579](assets/identity-graph-3579.svg)

É possível exibir um gráfico de identidade ao longo do tempo para um perfil específico usando o [Visualizador de gráfico de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Consulte também [Lógica de vinculação do Serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) para obter uma melhor compreensão da lógica usada ao vincular identidades.

#### Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento, após a coleção, às informações conhecidas no momento do gráfico de identidade.

+++ Detalhes

| | Hora | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada (após compilação em tempo real) |
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
Quando a pesquisa é resolvida para mais de uma id compilada (como para o evento 7), a primeira id lexicográfica retornada pelo gráfico de identidade é selecionada (`a.b@yahoo.co.uk` no exemplo ).

+++

#### Etapa 2: Repetir a compilação

Em intervalos regulares (dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base na versão mais recente do gráfico de identidade, no momento do intervalo.

+++ Detalhes

Com uma repetição da compilação em 2023-05-13 às 16:30, com uma configuração de janela de retrospectiva de 24 horas, alguns eventos da amostra são recompilados (indicado por ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Hora | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada<br/>(após compilação em tempo real) | ID compilada<br/>(após a repetição 24 horas) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


Com a repetição da compilação em 2023-05-13 às 16:30, com uma configuração de janela de retrospectiva de 7 dias, todos os eventos da amostra são recompilados.


| | Hora | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID compilada<br/>(após compilação em tempo real) | ID compilada<br/>(após a repetição 7 dias) |
|---|---|---|---|---|---|
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *indefinido* | `246` | `a.b@yahoo.co.uk` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Reproduzir novamente](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de acesso a dados pessoais, a ID compilada é excluída em todos os registros para o usuário sujeito à solicitação de acesso a dados pessoais.

+++ Detalhes

A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade (por exemplo, em 2023-05-13 18:00) tem nos eventos de amostra.

| | Hora | ID persistente<br/>`ECID` | Namespace<br/>`Email` ![Gráfico](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | ID com título (após solicitação de privacidade) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### Pré-requisitos 

Os seguintes pré-requisitos se aplicam especificamente à compilação baseada em gráfico:

- O conjunto de dados do evento no Adobe Experience Platform, ao qual você deseja aplicar a compilação, deve ter uma coluna que identifique um visitante em cada linha, a variável **ID persistente**. Por exemplo, uma ID de visitante gerada por uma biblioteca de AppMeasurements do Adobe Analytics ou uma ECID gerada pelo serviço de identidade da Adobe Experience Cloud.
- o gráfico de identidade do Experience Cloud Identity Service deve ter um namespace (por exemplo, `Email`ou `Phone`) que você deseja usar durante a compilação para resolver o **ID transitória**. Consulte [Serviço de identidade Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) para obter mais informações.


### Limitações

As seguintes limitações se aplicam especificamente à compilação baseada em gráfico:

- Os carimbos de data e hora não são considerados ao consultar a ID transitória usando o namespace especificado. Portanto, é possível que uma ID persistente seja compilada com uma ID transitória de um registro que tenha um carimbo de data e hora anterior.
- Sem suporte a dispositivo compartilhado. Quando várias identidades são retornadas, ao consultar o gráfico de identidade usando um namespace, a primeira identidade lexicográfica é usada.
- Há um limite rígido de três meses de preenchimento retroativo de identidades no gráfico de identidade. Caso não esteja usando um aplicativo Experience Platform, como o Real-time Customer Data Platform, para preencher o gráfico de identidade, você usaria identidades de preenchimento retroativo.
- A variável [Medidas de proteção do serviço de identidade](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) aplicável. Consulte, por exemplo, o seguinte [limites estáticos](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Número máximo de identidades em um gráfico: 50.
   - Número máximo de links para uma identidade para uma única assimilação de lote: 50.
   - Número máximo de identidades em um registro XDM para assimilação de gráfico: 20.
   - Número mínimo de identidades em um registro XDM para assimilação de gráfico: 2.


## Usar compilação

Assim que sua organização atender a todas as [pré-requisitos](#prerequisites) e compreenda as [limitações](#limitations) e específico do método de compilação ([baseado em campo](#limitations-1) e [baseado em gráfico](#limitations-2)), é possível seguir essas etapas para começar a usar a compilação no Customer Journey Analytics.

### Opções

Selecione as opções de compilação. O pacote Customer Journey Analytics determina as opções disponíveis para a duração do preenchimento retroativo inicial, a janela de pesquisa, a frequência de repetição e o número máximo de conjuntos de dados permitidos para compilação.

| | Customer Journey Analytics<br/>Selecionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Duração do preenchimento retroativo de compilação única | 13 meses | 13 meses | 25 meses |
| Janela de pesquisa e frequência de repetição | <li>1 dia, todos os dias</li><li>até 7 dias, semanalmente</li> | <li>1 dia, todos os dias</li><li>até 14 dias, semanalmente</li> | <li>1 dia, todos os dias</li><li>até 30 dias, semanalmente</li> |
| Número máximo de conjuntos de dados permitidos para compilação | 5 | 10 | 15 |

### Solicitar suporte

1. Entre em contato com o Suporte ao cliente da Adobe com as seguintes informações:

   - Uma solicitação para ativar a compilação.
   - A ID do conjunto de dados que você deseja rechavear.
   - O nome da coluna (caminho de identidade e namespace) da ID persistente para o conjunto de dados desejado (o identificador que aparece em cada linha).
   - Para a compilação em campo, o nome da coluna da ID transitória para o conjunto de dados desejado (o identificador de pessoa, que também atua como um link entre conjuntos de dados no contexto de uma conexão). Para compilação baseada em gráfico, o namespace de identidade a ser usado para consultar o gráfico de identidade.
   - Sua preferência por janela de retrospectiva e frequência de repetição. Consulte seu pacote Customer Journey Analytics para obter o [opções](#options) disponíveis.
   - Nome da sandbox.


2. O Suporte ao cliente do Adobe trabalha com a engenharia de Adobe para permitir a compilação ao receber sua solicitação. Depois de habilitada, um novo conjunto de dados rechaveado que contém uma nova coluna de ID compilada é exibido no Adobe Experience Platform. O Suporte ao cliente do Adobe pode fornecer a ID do novo conjunto de dados.

3. Quando ativado pela primeira vez, o Adobe fornece um preenchimento retroativo de dados compilados. Consulte seu pacote Customer Journey Analytics para obter o [opção](#options) disponíveis.

4. Se você quiser usar o novo conjunto de dados compilado em uma análise entre canais, é necessário adicionar o novo conjunto de dados compilado a uma [conexão](../connections/overview.md) em Customer Journey Analytics. Em seguida, adicione outros conjuntos de dados necessários para a análise entre canais e selecione a ID de pessoa correta para cada conjunto de dados.

5. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados estiver configurada, você poderá executar sua análise de relatório de Customer Journey Analytics em canais e dispositivos.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

