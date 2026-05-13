---
title: Referência de componente padrão
description: Saiba mais sobre os detalhes e as informações de todos os componentes padrão que podem ser adicionados a qualquer visualização de dados.
exl-id: e23ce27a-77ab-4641-a126-93f00d4e6e14
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/r4-Y3zJ51tsClEQFdjQnBYH-D2XQ8cibGYLkSmi3Ttc
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 779
ht-degree: 90%

---

# Referência de componente padrão

A maioria das dimensões e métricas no Customer Journey Analytics são baseadas em elementos de esquema do seu conjunto de dados da Adobe Experience Platform. No entanto, vários componentes estão disponíveis para serem adicionados a uma visualização de dados, independentemente da conexão usada.

[!UICONTROL Componentes padrão] são componentes que não são gerados de campos de esquema do conjunto de dados, mas que são gerados pelo sistema. Alguns componentes do sistema são necessários para facilitar os recursos de relatórios no Analysis Workspace, enquanto outros são opcionais.

![Componentes padrão](assets/dataview-standard-components.png)

## Componentes padrão obrigatórios {#required}

Esses componentes padrão obrigatórios são adicionados a cada visualização de dados por padrão. Eles são essenciais para os recursos de relatórios que o Customer Journey Analytics oferece.

### Dimensões padrão

{{standard-dimensions}}


### Métricas padrão

{{standard-metrics}}


## Componentes padrão opcionais {#optional}

Os componentes padrão opcionais estão disponíveis em **[!UICONTROL Visualizações de dados]** > **[!UICONTROL Editar visualização de dados]** > **[!UICONTROL Componentes]** > **[!UICONTROL Componentes padrão]**.

| Nome do componente | Dimensão ou métrica | Notas e valores |
| --- | --- | --- |
| [!UICONTROL AM/PM] | Dimensão de separação de tempo | AM ou PM |
| [!UICONTROL ID do lote] | Dimensão | Identificador do lote Experience Platform do qual um [!UICONTROL Evento] fazia parte. |
| [!UICONTROL ID do conjunto de dados] | Dimensão | Identificador do conjunto de dados Experience Platform do qual um [!UICONTROL Evento] fazia parte. |
| [!UICONTROL Dia do mês] | Dimensão de separação de tempo | 1-31 |
| [!UICONTROL Dia da semana] | Dimensão de separação de tempo | Segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira, sábado, domingo |
| [!UICONTROL Dia do ano] | Dimensão de separação de tempo | 1-366 |
| [!UICONTROL Hora do dia] | Dimensão de separação de tempo | 0-23 |
| [!UICONTROL  Mês do ano] | Dimensão de separação de tempo | Janeiro - Dezembro |
| [!UICONTROL Primeiras sessões] | Métrica | A primeira sessão definida por uma pessoa na janela de relatórios. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Sessões de retorno] | Métrica | O número de sessões que não foram a primeira sessão de uma pessoa. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL ID de pessoa] | Dimensão | Cada esquema do conjunto de dados definido na Experience Platform pode ter seu próprio conjunto de uma ou mais identidades definidas e associadas a um namespace de identidade. Qualquer uma dessas identidades pode ser usada como a ID de pessoa. Os exemplos incluem: ID de cookie, ID compilada, ID de usuário, código de rastreamento etc. A dimensão [!UICONTROL ID de pessoa] é a base da combinação de conjuntos de dados e da identificação de pessoas únicas no Customer Journey Analytics.<p>Os possíveis casos de uso incluem:<ul><li>Crie um segmento em um valor de ID de pessoa específico para segmentar tudo de acordo com o comportamento desse usuário.</li><li>Depuração: certificar-se de que os dados de uma ID de cookie específica (ou uma ID de cliente específica) estejam lá.</li><li>Identificação dos usuários que entraram em contato com uma central de atendimento.</li></ul> |
| [!UICONTROL Namespace da ID de pessoa] | Dimensão | O tipo de ID no qual a [!UICONTROL ID de pessoa] consiste. São exemplos: `email address`, `cookie ID`, `Analytics ID` |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL ID da conta global] | Dimensão | A [!UICONTROL ID da conta global] quando você usa o container da conta global em sua conexão. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL ID da conta] | Dimensão | A [!UICONTROL ID da Conta], quando você usa o contêiner de Conta em sua conexão. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL ID da oportunidade] | Dimensão | A [!UICONTROL ID de oportunidade] quando você usa o container de oportunidade em sua conexão. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>[!UICONTROL ID do grupo de compra] | Dimensão | A [!UICONTROL ID do grupo de compra] quando você usa o container do grupo de compra em sua conexão. |
| [!UICONTROL Trimestre do ano] | Dimensão de separação de tempo | T1, T2, T3, T4 |
| [!UICONTROL Repetição de sessão] | Métrica | O número de sessões que não foram a primeira sessão de uma pessoa. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Tipo de sessão] | Dimensão | Essa dimensão tem dois valores: 1. [!UICONTROL Primeira vez] e 2. Retornando. O item da linha [!UICONTROL Primeira vez] inclui todo o comportamento (ou seja, métricas em relação a essa dimensão) de uma sessão que foi determinada como a primeira sessão definida de uma pessoa. Todo o restante está incluído no item da linha [!UICONTROL Retorno] (supondo que tudo pertença a uma sessão). Quando as métricas não fazem parte de nenhuma sessão, elas se encaixam no compartimento “Não aplicável” dessa dimensão. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=pt-BR#new-repeat) |
| [!UICONTROL Tempo gasto por evento] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Evento]. |
| [!UICONTROL Tempo gasto por sessão] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Sessão]. |
| [!UICONTROL Tempo gasto por pessoa] | Dimensão | Segmenta a métrica [!UICONTROL Tempo gasto] em segmentos de [!UICONTROL Pessoa]. |
| [!UICONTROL Final de semana]/[!UICONTROL Dia de semana] | Dimensão de separação de tempo | Final de semana ou Dia de semana |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Descubra insights do cliente mais profundos com o recurso Profundidade do evento](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/discover-deeper-customer-insights-with-adobe-customer-journey/ba-p/753947?profile.language=pt#M576)
>