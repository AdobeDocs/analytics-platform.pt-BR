---
title: Suporte CJA para Governança de dados do Adobe Experience Platform
description: Saiba como os rótulos de dados e as políticas definidas na AEP afetam os relatórios no CJA.
mini-toc-levels: 3
source-git-commit: 82060862c64aae10ea6dd375a8cd65d67ee21704
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---


# Suporte CJA para Governança de dados do Adobe Experience Platform

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

A integração entre o CJA e o [Governança de dados do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) permite a rotulagem de dados sensíveis do CJA e a aplicação de políticas de privacidade.

Os rótulos e as políticas de privacidade que foram criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do CJA. Esses rótulos param ou avisam os usuários que criam métricas e/ou dimensões a partir de campos confidenciais.

Além disso, quando os dados são exportados do CJA (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para notificar os usuários que um relatório contém informações confidenciais que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os Data Stewards na organização podem definir políticas para restringir o uso. Como resultado, os usuários do CJA podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos Data Stewards.

## Rotulagem e políticas no Adobe Experience Platform

Ao criar um conjunto de dados no Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para alguns ou todos os elementos no conjunto de dados. Até agora, esses rótulos não eram expostos no CJA. Com esta versão, você pode exibir esses rótulos no CJA. De especial interesse para o CJA são esses rótulos:

* O `C8` rótulo - **[!UICONTROL Sem medição]**. Esse rótulo significa que os dados não podem ser usados para análises nos sites ou aplicativos de sua organização.

* O `C12` rótulo - **[!UICONTROL Nenhuma exportação de dados gerais]**. Campos de esquema rotulados dessa maneira não podem ser exportados ou baixados do CJA (por meio de relatórios, exportação, API, etc.)

Rotular em si não significa que esses rótulos de uso de dados sejam aplicados. É para isso que as políticas são usadas. Você cria suas políticas por meio da [API do serviço de política](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) em Experience Platform.

As políticas têm dois componentes: o rótulo de dados e uma ação de marketing que os consumidores de dados podem realizar no contexto de políticas restritas de uso de dados. No contexto do CJA, dois Adobe definidos [ações de marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) são importantes:

* Analytics - uso de dados para fins de análise, como medição, análise e relatórios sobre o uso pelo consumidor dos sites ou aplicativos de sua organização.

* Exportar dados para terceiros - ou seja, fora do ambiente Adobe.

Você vincula rótulos e ações de marketing a uma política e depois ativa a política. A política pega o rótulo e a ação de marketing e diz: aplique essa restrição. Duas políticas definidas pelo Adobe são exibidas no CJA e afetam os relatórios e o download/compartilhamento:

* Impor a política do Analytics
* Impor política de download


### Exibir rótulos de dados em visualizações de dados do CJA

Os rótulos de dados criados no Experience Platform são mostrados em três locais na interface do usuário de visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Info em um campo de schema | Clicar nesse botão indica quais rótulos de uso de dados se aplicam atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os rótulos de uso de dados estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | É possível adicionar Rótulos de dados como uma coluna às colunas Componentes incluídos nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar Rótulos de uso de dados:<p>![](assets/data-label-column.png) |

### Filtrar em rótulos de Governança de dados em visualizações de dados

No editor de visualizações de dados, clique no ícone Filtro na trilha esquerda e filtre os componentes das visualizações de dados por rótulos de governança de dados:

![](assets/filter-labels.png)

Clique em **[!UICONTROL Aplicar]** para ver quais componentes têm rótulos anexados a eles.

### Filtrar as políticas de governança de dados nas visualizações de dados

É possível verificar se uma política está ativada e bloqueia o uso de determinados elementos de visualização de dados do CJA para fins de análise ou exportação.

Novamente, clique no ícone Filtro no painel à esquerda e, em Governança de dados, clique em Políticas:

![](assets/filter-policies.png)

Clique em **[!UICONTROL Aplicar]** para ver quais políticas estão ativadas _para esta visualização de dados?_

### Como a função [!UICONTROL Impor o Analytics] afeta projetos do Workspace

Se essa política estiver ativada, os campos do esquema que têm determinados rótulos de dados (como C8) associados a eles não poderão ser usados para fins de análise no CJA Workspace.

Para relatórios, isso significa que

* Não é possível adicionar esses campos às visualizações de dados, e eles ficam esmaecidos no painel esquerdo [!UICONTROL Campos de esquema] lista.
* Não é possível salvar uma visualização de dados que tenha bloqueado campos nela.

Se você tentar executar a análise do Workspace em visualizações de dados que contêm itens proibidos para o Analytics, você receberá um aviso semelhante a este:

![](assets/policy-enforce.png)

Em componentes individuais, a mensagem seria semelhante a esta:

![](assets/policy-enforce2.png)

### Como a função [!UICONTROL Impor download] afeta projetos do Workspace

Se essa política estiver ativada, qualquer download (como enviar por email ou compartilhar pdfs) de projetos do Workspace fará hash nos campos confidenciais. Ainda é possível fazer a análise nesses campos no Workspace, mas se você tentar enviar um email ou compartilhar um projeto de outra forma, os campos bloqueados serão exibidos como itens com hash no arquivo .pdf .

Adicione uma captura de tela aqui.

### Exibir rótulos no Report Builder

Consulte _esta seção_ para obter mais informações. (link para o médico de Christine)
