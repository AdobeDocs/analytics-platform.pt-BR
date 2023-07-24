---
title: Rótulos e políticas
description: Saiba como os rótulos e políticas de dados definidos no Adobe Experience Platform afetam as visualizações de dados e os relatórios no Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
source-git-commit: d14db99f6cf597c4b62cdb148853b0f11503eaa1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 58%

---

# Rótulos e políticas

Ao criar um conjunto de dados na Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=pt-BR) para alguns ou todos os elementos no conjunto de dados. Você pode visualizar esses rótulos e políticas no Customer Journey Analytics.

Os seguintes rótulos são de especial interesse para o Customer Journey Analytics:

* O rótulo `C8` - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análises nos sites ou aplicativos de sua organização.

* O rótulo `C12` - **[!UICONTROL Nenhuma exportação de dados gerais]**. Campos de esquema rotulados dessa maneira não podem ser exportados ou baixados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.)

>[!NOTE]
>
>Os rótulos de uso de dados não são propagados automaticamente para conjuntos de dados compilados. No entanto, elas podem ser adicionadas manualmente.

A rotulação por si só não significa que esses rótulos de uso de dados serão aplicados. É para isso que as políticas são usadas. Você cria suas políticas usando o [IU DO EXPERIENCE PLATFORM](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=pt-BR) ou por meio da [API de serviço de política](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=pt-BR) em Experience Platform.

Duas políticas definidas por Adobe são exibidas no Customer Journey Analytics e afetam os relatórios e o download/compartilhamento:

* Política **[!UICONTROL Forçar análise]**
* Política **[!UICONTROL Forçar download]**

## Exibir rótulos de dados em visualizações de dados do Customer Journey Analytics

Os rótulos de dados criados na Experience Platform são exibidos em três locais na interface das visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Informação em um campo do esquema | Clicar nesse botão indica quais [!UICONTROL rótulos de uso de dados] aplicam-se atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os [!UICONTROL rótulos de uso de dados] estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | Você pode adicionar [!UICONTROL rótulos de uso de dados] como uma coluna nas colunas [!UICONTROL Componentes incluídos] nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar **[!UICONTROL Rótulos de uso de dados]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrar rótulos de governança de dados em visualizações de dados

No editor de visualizações de dados, clique no ícone [!UICONTROL filtro] ícone no painel esquerdo e filtrar os componentes de visualizações de dados por **[!UICONTROL Governança de dados]** e tipo de **[!UICONTROL Rótulo]**:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

## Filtrar as políticas de governança de dados nas visualizações de dados

É possível verificar se está ativada uma política que bloqueia o uso de determinados elementos de visualização de dados Customer Journey Analytics para fins de análise ou exportação.

Novamente, clique no link [!UICONTROL filtro] no painel à esquerda e em **[!UICONTROL Governança de dados]**, clique em **[!UICONTROL Políticas]**:

![](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão ativadas.

## Como as políticas ativadas afetam as visualizações de dados

Se as políticas **[!UICONTROL Forçar análise]** ou **[!UICONTROL Forçar download]** estiverem ativadas, os componentes do esquema que têm determinados rótulos de dados (como C8 ou C12) associados a eles não poderão ser adicionados às visualizações de dados.

Esses componentes estão esmaecidos na lista [!UICONTROL Campos de esquema] no painel à esquerda:

![](assets/component-greyed.png)

Também não é possível salvar uma visualização de dados que tenha campos bloqueados.

>[!MORELIKETHIS]
>[Baixar dados sigilosos](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[O que são os rótulos restritos no Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=pt-BR)


