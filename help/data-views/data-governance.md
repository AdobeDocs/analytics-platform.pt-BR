---
title: Rótulos e políticas
description: Saiba como as políticas e os rótulos de dados definidos na Adobe Experience Platform afetam as visualizações de dados e os relatórios no Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 100%

---

# Rótulos e políticas

Ao criar um conjunto de dados na Experience Platform, é possível criar [rótulos de uso de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/reference) para alguns ou todos os elementos no conjunto de dados. É possível visualizar esses rótulos e políticas no Customer Journey Analytics.

Os rótulos seguintes são de especial interesse para o Customer Journey Analytics:

* O rótulo `C8` - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análise nos sites ou aplicativos da sua organização.

* O rótulo `C12`: **[!UICONTROL sem exportação de dados gerais]**. Os campos de esquema rotulados dessa maneira não podem ser exportados nem baixados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.)

>[!NOTE]
>
>Os rótulos de uso de dados não são propagados automaticamente para os conjuntos de dados compilados. No entanto, eles podem ser adicionados manualmente.

A rotulação por si só não significa que esses rótulos de uso de dados serão aplicados. É para isso que as políticas são usadas. Você pode criar suas políticas usando a [Interface da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/policies/user-guide) ou por meio da [API do serviço de política](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/api/overview) na Experience Platform.

Duas políticas definidas pela Adobe estão disponíveis na Experience Platform que podem ser exibidas no Customer Journey Analytics e afetar relatórios e exportação de dados:

* Política de **[!UICONTROL Restrição de análise de uso e medição baseada no usuário]** usando o rótulo `C8` e
* política de **[!UICONTROL Restrição de exportação de dados]** usando o rótulo `C12`.

## Exibir rótulos de dados em visualizações de dados do Customer Journey Analytics

Os rótulos de dados que você ou outras pessoas criaram na Experience Platform são exibidos em três locais na interface do usuário das visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Informação em um campo do esquema | Clicar nesse botão indica quais [!UICONTROL rótulos de uso de dados] aplicam-se atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os [!UICONTROL rótulos de uso de dados] estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | Você pode adicionar [!UICONTROL rótulos de uso de dados] como uma coluna nas colunas [!UICONTROL Componentes incluídos] nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar **[!UICONTROL Rótulos de uso de dados]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrar por rótulos de governança de dados nas visualizações de dados

No editor de visualizações de dados, selecione o ícone de [!UICONTROL filtro] no painel à esquerda e filtre os componentes de visualizações de dados por **[!UICONTROL Governança de dados]** e tipo de **[!UICONTROL Rótulo]**:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

## Filtrar as políticas de governança de dados nas visualizações de dados

É possível verificar se uma política (por exemplo, uma política que você criou, denominada **[!UICONTROL Aplicar análise]**) está ativada. E se essa política bloqueia o uso de determinados elementos de visualização de dados do Customer Journey Analytics para análise ou exportação de dados.

Novamente, clique no ícone de [!UICONTROL filtro] no painel esquerdo, em **[!UICONTROL Governança de dados]** e selecione **[!UICONTROL Políticas]**:

![Filtrar componentes incluídos por lista mostrando as opções Restringir análise de uso e medição baseada em usuário selecionadas](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão habilitadas.

## Como as políticas habilitadas afetam as visualizações de dados

Se uma ou mais políticas estiverem ativadas com rótulos C8 ou C12, os componentes do esquema que têm determinados rótulos de dados aplicados não poderão ser adicionados às visualizações de dados.

Esses componentes ficam esmaecidos na lista [!UICONTROL Campos do esquema] no painel esquerdo:

![Componentes esmaecidos e a mensagem de Políticas indicando que políticas foram aplicadas a este campo restringindo o uso dos dados](assets/component-greyed.png)

Também não é possível salvar uma visualização de dados que tenha campos bloqueados.

Tenha cuidado ao tentar aplicar rótulos de acesso e governança de dados (por meio de políticas) em campos ou grupos de campos na Experience Platform para os quais você já tem componentes definidos na visualização de dados. Você poderá ver esta caixa de diálogo.

![Violação](assets/violation.png)

Primeiro, é necessário resolver a violação (por exemplo, remover os componentes da visualização de dados).


>[!MORELIKETHIS]
>
>[Baixar dados sigilosos](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[O que são os rótulos restritos no Report Builder?](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


