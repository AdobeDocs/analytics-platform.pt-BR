---
title: O que são os rótulos restritos no Report Builder
description: Descreve os rótulos restritos no Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 22b06eaf9f224188699aa241de1d1daad8a14619
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 44%

---

# Rótulos restritos no Report Builder

Geralmente, as configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas do Experience Platform. A integração entre o Customer Journey Analytics e a Governança de dados da Experience Platform permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Esses rótulos interrompem ou avisam os usuários que criam métricas e dimensões a partir de campos sigilosos. Para obter informações sobre conjuntos de dados, consulte [Visão geral sobre conjuntos de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/catalog/datasets/overview)

Além disso, quando dados são exportados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para informar aos usuários que um relatório contém informações sigilosas que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade. Os administradores de dados da sua organização podem definir políticas de restrição de uso. Como resultado, os usuários do Customer Journey Analytics podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos administradores de dados.

Para obter mais informações, consulte [Customer Journey Analytics e governança de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Exibir dados restritos

Duas políticas definidas pela Adobe são exibidas no Customer Journey Analytics e afetam os relatórios, downloads e compartilhamento:

* Política Forçar análise
* Política Forçar download

Os componentes sujeitos a essas políticas estão esmaecidos e têm um ícone ![InfoOutline](/help/assets/icons/InfoOutline.svg). Quando você passa o mouse sobre o ícone de informações, uma nota é exibida para indicar o seguinte: **[!UICONTROL Foram aplicadas políticas a este campo que proíbem o uso destes dados]**.

Para obter mais informações, consulte [Rótulos e políticas](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dataviews/data-governance).


![A nota de política indicando uso proibido de dados.](assets/restricted-label.png){zoomable="yes"}


## Atualizar relatórios que contêm dados restritos

Nos casos em que um usuário criou um relatório do Report Builder com elementos de dados restritos posteriormente, quando o relatório for atualizado uma mensagem de erro será exibida.

![A mensagem de erro exibida após os elementos de dados serem restritos posteriormente.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
