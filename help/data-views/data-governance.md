---
title: Suporte CJA para Governança de dados do Adobe Experience Platform
description: Saiba como os rótulos de dados e as políticas definidas na AEP afetam os relatórios no CJA.
mini-toc-levels: 3
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 2dde88ea6c3bb806b66cd4bc8fb8b10bd28084d0
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# Rótulos e políticas

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

Ao criar um conjunto de dados no Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para alguns ou todos os elementos no conjunto de dados. Até agora, esses rótulos não eram expostos no CJA. Com esta versão, você pode exibir esses rótulos no CJA. De especial interesse para o CJA são esses rótulos:

* O `C8` rótulo - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análises nos sites ou aplicativos de sua organização.

* O `C12` rótulo - **[!UICONTROL Nenhuma exportação de dados gerais]**. Campos de esquema rotulados dessa maneira não podem ser exportados ou baixados do CJA (por meio de relatórios, exportação, API, etc.)

Rotular em si não significa que esses rótulos de uso de dados sejam aplicados. É para isso que as políticas são usadas. Você cria suas políticas por meio da [API do serviço de política](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) em Experience Platform.

Duas políticas definidas pelo Adobe são exibidas no CJA e afetam os relatórios e o download/compartilhamento:

* [!UICONTROL Impor o Analytics] política
* [!UICONTROL Impor download] política

## Exibir rótulos de dados em visualizações de dados do CJA

Os rótulos de dados criados no Experience Platform são mostrados em três locais na interface do usuário de visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Info em um campo de schema | Clicar nesse botão indica quais rótulos de uso de dados se aplicam atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os rótulos de uso de dados estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | É possível adicionar Rótulos de dados como uma coluna às colunas Componentes incluídos nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar Rótulos de uso de dados:<p>![](assets/data-label-column.png) |

## Filtrar em rótulos de Governança de dados em visualizações de dados

No editor de visualizações de dados, clique no ícone Filtro na trilha esquerda e filtre os componentes das visualizações de dados por rótulos de governança de dados:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

## Filtrar as políticas de governança de dados nas visualizações de dados

É possível verificar se uma política está ativada e bloqueia o uso de determinados elementos de visualização de dados do CJA para fins de análise ou exportação.

Novamente, clique no ícone Filtro no painel à esquerda e, em Governança de dados, clique em Políticas:

![](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão ativadas _para esta visualização de dados?_

## Como a função [!UICONTROL Impor o Analytics] afeta projetos do Workspace

Se essa política estiver ativada, os campos do esquema que têm determinados rótulos de dados (como C8) associados a eles não poderão ser usados para fins de análise no CJA Workspace.

Para relatórios, isso significa que

* Não é possível adicionar esses campos às visualizações de dados, e eles ficam esmaecidos no painel esquerdo [!UICONTROL Campos de esquema] lista.
* Não é possível salvar uma visualização de dados que tenha bloqueado campos nela.

Se você tentar executar a análise do Workspace em visualizações de dados que contêm itens proibidos para o Analytics, você receberá um aviso semelhante a este:

![](assets/policy-enforce.png)

Em componentes individuais, a mensagem seria semelhante a esta:

![](assets/policy-enforce2.png)

## Como a função [!UICONTROL Impor download] afeta projetos do Workspace

Se essa política estiver ativada, qualquer exportação ou download (como enviar por email ou compartilhar pdfs) de projetos do Workspace fará hash nos campos confidenciais. Ainda é possível fazer a análise nesses campos no Workspace, mas se você tentar enviar um email ou compartilhar um projeto de outra forma, os campos bloqueados serão exibidos como itens com hash no arquivo .pdf .

Adicione uma captura de tela aqui.

## Exibir rótulos no Report Builder

Consulte _esta seção_ para obter mais informações. (link para o médico de Christine)
