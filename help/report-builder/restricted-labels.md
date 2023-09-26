---
title: O que são os rótulos restritos no Report Builder
description: Descreve os rótulos restritos no Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 49a35a256758b259dfb2133658bae617315774e4
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 57%

---

# Rótulos restritos no Report Builder

De modo geral, as configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas da Adobe Experience Platform. A integração entre o Customer Journey Analytics e o Adobe Experience Platform Data Governance permite rotular dados de Customer Journey Analytics confidenciais e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade que foram criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Esses rótulos interrompem ou avisam os usuários que criam métricas e/ou dimensões a partir de campos sigilosos. Para obter informações sobre conjuntos de dados, consulte [Visão geral sobre conjuntos de dados](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=pt-BR)

Além disso, quando os dados são exportados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para notificar os usuários que um relatório contém informações confidenciais que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade com mais facilidade. Os administradores de dados da sua organização podem definir políticas de restrição de uso. Como resultado, os usuários do Customer Journey Analytics podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos administradores de dados.

Para obter mais informações, consulte [Customer Journey Analytics e governança de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=pt-BR)

## Exibir dados restritos no Report Builder

Duas políticas definidas por Adobe são exibidas no Customer Journey Analytics e afetam os relatórios, downloads e compartilhamento:

* Política Forçar análise
* Política Forçar download

Os componentes afetados por essas políticas ficam esmaecidos. Quando você passa o mouse sobre um componente que tem uma política aplicada, uma nota é exibida para indicar o seguinte: **Foram aplicadas políticas a este campo que proíbem o uso desses dados.** Para obter mais informações, consulte [Rótulos e políticas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=pt-BR).

![A nota de política indicando uso proibido de dados.](assets/rb-restricted-label.png)

## Atualizar relatórios com dados restritos

Nos casos em que um usuário criou um relatório do Report Builder com elementos de dados restritos posteriormente, quando o relatório for atualizado uma mensagem de erro será exibida.

![A mensagem de erro exibida depois que os elementos de dados são restritos.](assets/error-restricted-data.png)
