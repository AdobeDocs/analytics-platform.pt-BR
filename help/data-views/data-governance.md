---
title: Rótulos e políticas
description: Saiba como as políticas e os rótulos de dados definidos na Adobe Experience Platform afetam as visualizações de dados e os relatórios no Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 45%

---

# Rótulos e políticas

Ao criar um conjunto de dados no Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) para alguns ou todos os elementos no conjunto de dados. É possível visualizar esses rótulos e políticas no Customer Journey Analytics.

Os rótulos seguintes são de especial interesse para o Customer Journey Analytics:

* O rótulo `C8` - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análise nos sites ou aplicativos da sua organização.

* A variável `C12` rótulo - **[!UICONTROL Sem exportação de dados gerais]**. Os campos de esquema rotulados dessa maneira não podem ser exportados nem baixados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.)

>[!NOTE]
>
>Os rótulos de uso de dados não são propagados automaticamente para os conjuntos de dados compilados. No entanto, eles podem ser adicionados manualmente.

A rotulação por si só não significa que esses rótulos de uso de dados serão aplicados. É para isso que as políticas são usadas. Você pode criar suas políticas usando o [IU DO EXPERIENCE PLATFORM](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) ou por meio da [API de serviço de política](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) em Experience Platform.

Duas políticas definidas por Adobe estão disponíveis em Experience Platform que podem aparecer em Customer Journey Analytics e afetar os relatórios e a exportação de dados:

* **[!UICONTROL Restringir análise de uso e medição baseada em usuário]** política, usando o `C8` rótulo e
* **[!UICONTROL Restringir exportação de dados]** política, usando o `C12` rótulo.

## Exibir rótulos de dados em visualizações de dados do Customer Journey Analytics

Os rótulos de dados que você ou outras pessoas criaram no Experience Platform são mostrados em três locais na interface das visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Informação em um campo do esquema | Clicar nesse botão indica quais [!UICONTROL rótulos de uso de dados] aplicam-se atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os [!UICONTROL rótulos de uso de dados] estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | Você pode adicionar [!UICONTROL rótulos de uso de dados] como uma coluna nas colunas [!UICONTROL Componentes incluídos] nas visualizações de dados. Basta selecionar o ícone do seletor de colunas e **[!UICONTROL Rótulos de uso de dados]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrar por rótulos de governança de dados nas visualizações de dados

No editor de visualizações de dados, selecione a variável [!UICONTROL filtro] ícone no painel esquerdo e filtrar os componentes de visualizações de dados por **[!UICONTROL Governança de dados]** e tipo de **[!UICONTROL Rótulo]**:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

## Filtrar as políticas de governança de dados nas visualizações de dados

Você pode verificar se uma política (por exemplo, uma política que você criou, denominada **[!UICONTROL Forçar análise]**) está ativada. E se essa política bloqueia o uso de determinados elementos de visualização de dados do Customer Journey Analytics para análise ou exportação de dados.

Novamente, selecione o [!UICONTROL filtro] no painel à esquerda e em **[!UICONTROL Governança de dados]**, selecione **[!UICONTROL Políticas]**:

![Filtrar componentes incluídos por lista mostrando a opção Restringir análise de uso e medição baseada em usuário selecionada](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão ativadas.

## Como as políticas ativadas afetam as visualizações de dados

Se uma ou mais políticas forem ativadas com rótulos C8 ou C12, os componentes do esquema que têm determinados rótulos de dados aplicados não poderão ser adicionados às visualizações de dados.

Esses componentes estão esmaecidos no painel esquerdo [!UICONTROL Campos de esquema] lista:

![Componentes esmaecidos e a mensagem de Políticas indicando que políticas foram aplicadas a este campo restringindo o uso dos dados](assets/component-greyed.png)

Também não é possível salvar uma visualização de dados que tenha campos bloqueados.

Tenha cuidado ao tentar aplicar rótulos de acesso e governança de dados (por meio de políticas) em campos ou grupos de campos no Experience Platform, para os quais você já tem componentes definidos na visualização de dados. Você poderá ver esta caixa de diálogo.

![Violação](assets/violation.png)

Primeiro, é necessário resolver a violação (por exemplo, remover os componentes da visualização de dados).


>[!MORELIKETHIS]
>
>[Baixar dados sigilosos](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[O que são os rótulos restritos no Report Builder?](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


