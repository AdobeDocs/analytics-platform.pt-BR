---
title: Suporte CJA para Governança de dados do Adobe Experience Platform
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# Suporte CJA para Governança de dados do Adobe Experience Platform

A integração entre o CJA e o [Governança de dados do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) permite a rotulagem de dados sensíveis do CJA e a aplicação de políticas de privacidade.

Os rótulos e as políticas de privacidade que foram criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do CJA. Esses rótulos param ou avisam os usuários que criam métricas e/ou dimensões a partir de campos confidenciais.

Além disso, quando os dados são exportados do CJA (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para notificar os usuários que um relatório contém informações confidenciais que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os Data Stewards na organização podem definir políticas para restringir o uso. Como resultado, os usuários do CJA podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos Data Stewards.

## Rotulagem e políticas no Adobe Experience Platform

Ao criar um conjunto de dados no Experience Platform, você pode criar [rótulos de uso de dados](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) para alguns ou todos os elementos no conjunto de dados. Até agora, esses rótulos não eram expostos no CJA. Com esta versão, você pode exibir esses rótulos no CJA. De especial interesse para o CJA é o rótulo C8, que diz &quot;Os dados não podem ser usados para medir os sites ou aplicativos de sua organização&quot;.

Rotular em si não significa que esses rótulos de uso de dados sejam aplicados. É para isso que as políticas são usadas. Você cria suas políticas por meio da [API do serviço de política](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) em Experience Platform.

As políticas têm dois componentes: o rótulo de dados e uma ação de marketing que os consumidores de dados podem realizar no contexto de políticas restritas de uso de dados. No contexto do CJA, dois Adobe definidos [ações de marketing](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) são importantes:

* Analytics - uso de dados para fins de análise, como medição, análise e relatórios sobre o uso pelo consumidor dos sites ou aplicativos de sua organização.

* Exportar esses dados do ambiente Adobe, como exportar dados para terceiros.

Você vincula rótulos e ações de marketing a uma política e depois ativa a política. A política pega o rótulo e a ação de marketing e diz: aplique essa restrição. No CJA surgem duas políticas Adobe definidas:

* Política do Analytics
* Baixar política

## Exibir rótulos de dados em visualizações de dados do CJA

Os rótulos de dados criados no Experience Platform são exibidos em três locais na interface do usuário de visualizações de dados:

| Localização | Descrição |
| --- | --- |
| Botão Info em um campo de schema | Clicar nesse botão indica quais rótulos de uso de dados se aplicam atualmente a um campo:<p>![](assets/data-label-left.png) |
| Painel direito em [Configurações do componente](/help/data-views/component-settings/overview.md) | Todos os rótulos de uso de dados estão listados aqui:<p>![](assets/data-label-right.png) |
| Adicionar rótulos de dados como uma coluna | É possível adicionar Rótulos de dados como uma coluna às colunas Componentes incluídos nas visualizações de dados. Basta clicar no ícone do seletor de colunas e selecionar Rótulos de uso de dados:<p>![](assets/data-label-column.png) |

### Filtro em rótulos de Governança de dados no CJA

No editor de visualizações de dados, clique no ícone Filtro na trilha esquerda e filtre os componentes de visualizações de dados pelos rótulos de governança de dados:

![](assets/filter-labels.png)

### Filtro em políticas de governança de dados no CJA

É possível verificar se uma política está ativada e bloqueia o uso de determinados elementos de visualização de dados do CJA para fins de análise ou exportação.

Novamente, clique no ícone Filtro no painel à esquerda e, em Governança de dados, clique em Políticas:

![](assets/filter-policies.png)

Se a política estiver ativada, esses campos de esquema que têm determinados rótulos de dados (como C8) associados a eles não poderão ser usados para fins de análise ou download (como enviar por email ou compartilhar pdfs) no CJA Workspace.

Observe que

* Não é permitido adicioná-los a visualizações de dados. Esses campos serão esmaecidos na lista de campos do Esquema do painel à esquerda.
* Não é possível salvar uma visualização de dados que tenha bloqueado campos nela.


