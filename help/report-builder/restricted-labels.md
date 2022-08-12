---
title: O que são rótulos restritos no Report Builder
description: Descreve rótulos restritos no Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 0e626b4072c68a69ae94dbfdfb53169aa34ca8ac
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%

---


# Etiquetas restritas no Report Builder

Geralmente, as configurações relacionadas ao controle de dados no Customer Journey Analytics são herdadas do Adobe Experience Platform. A integração entre o CJA e a Governança de dados da Adobe Experience Platform permite a rotulagem de dados confidenciais do CJA e a aplicação de políticas de privacidade.

Os rótulos e as políticas de privacidade que foram criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do CJA. Esses rótulos param ou avisam os usuários que criam métricas e/ou dimensões a partir de campos confidenciais. Para obter informações sobre conjuntos de dados, consulte [Visão geral dos conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

Além disso, quando os dados são exportados do CJA (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para notificar os usuários que um relatório contém informações confidenciais que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os Data Stewards na organização podem definir políticas para restringir o uso. Como resultado, os usuários do CJA podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos Data Stewards.

Para obter mais informações, consulte [Customer Journey Analytics e Governança de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Exibição de dados restritos no Report Builder

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

Duas políticas definidas pelo Adobe são exibidas no CJA que afetam os relatórios, o download e o compartilhamento:

* Impor a política do Analytics
* Impor política de download

Os componentes afetados por essas políticas ficam esmaecidos. Quando você passa o mouse sobre um componente que tem uma política aplicada, uma nota é exibida para indicar o seguinte: **Foram aplicadas políticas a este campo para proibir o uso desses dados.** Para obter mais informações, consulte [Rótulos e políticas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## Atualização de relatórios contendo dados restritos

Nos casos em que um usuário criou um relatório Report Builder com elementos de dados restritos posteriormente, quando o relatório é atualizado, uma mensagem de erro é exibida.

![](assets/error-restricted-data.png)
