---
title: Rótulos e políticas
description: Saiba como os rótulos de dados e as políticas definidas na AEP afetam as visualizações de dados e os relatórios no CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 1e2c5d79059a4804416288188ea4740dd94ca33d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Rótulos e políticas

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

Ao criar um conjunto de dados no Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para alguns ou todos os elementos no conjunto de dados. Até agora, esses rótulos não eram expostos no CJA. Com esta versão, você pode visualizar esses rótulos e políticas no CJA.

De especial interesse para o CJA são esses rótulos:

* O `C8` rótulo - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análises nos sites ou aplicativos de sua organização.

* O `C12` rótulo - **[!UICONTROL Nenhuma exportação de dados gerais]**. Campos de esquema rotulados dessa maneira não podem ser exportados ou baixados do CJA (por meio de relatórios, exportação, API, etc.)

Rotular em si não significa que esses rótulos de uso de dados sejam aplicados. É para isso que as políticas são usadas. Você cria suas políticas por meio da [API do serviço de política](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) em Experience Platform.

Duas políticas definidas pelo Adobe são exibidas no CJA e afetam os relatórios e o download/compartilhamento:

* **[!UICONTROL Impor o Analytics]** política
* **[!UICONTROL Impor download]** política

## Exibir rótulos de dados em visualizações de dados do CJA

Os rótulos de dados criados no Experience Platform são mostrados em três locais na interface do usuário de visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Info em um campo de schema | Clicar nesse botão indica o que [!UICONTROL Rótulos de uso de dados] aplica-se atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Qualquer [!UICONTROL Rótulos de uso de dados] estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | Você pode adicionar [!UICONTROL Rótulos de uso de dados] como uma coluna para a [!UICONTROL Componentes incluídos] nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar **[!UICONTROL Rótulos de uso de dados]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtrar em rótulos de Governança de dados em visualizações de dados

No editor de visualizações de dados, clique no ícone Filtro na trilha esquerda e filtre os componentes de visualizações de dados por **[!UICONTROL Governança de dados]** e tipo de **[!UICONTROL Rótulo]**:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

## Filtrar as políticas de governança de dados nas visualizações de dados

É possível verificar se uma política está ativada e bloqueia o uso de determinados elementos de visualização de dados do CJA para fins de análise ou exportação.

Novamente, clique no ícone Filtro no painel à esquerda e em **[!UICONTROL Governança de dados]**, clique em **[!UICONTROL Políticas]**:

![](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão habilitadas.

## Como as políticas ativadas afetam as visualizações de dados

Se a variável **[!UICONTROL Impor o Analytics]** ou **[!UICONTROL Impor download]** políticas estiverem ativadas, os componentes do esquema que têm determinados rótulos de dados (como C8 ou C12) associados a eles não poderão ser adicionados às visualizações de dados.

Esses componentes estão esmaecidos no painel esquerdo [!UICONTROL Campos de esquema] lista:

![](assets/component-greyed.png)

Também não é possível salvar uma visualização de dados que tenha bloqueado campos nela.

>[!MORELIKETHIS]
>[Baixar dados confidenciais](/help/analysis-workspace/curate-share/download-send.md)
