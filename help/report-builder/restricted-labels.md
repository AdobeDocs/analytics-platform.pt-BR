---
title: Rótulos Restritos No Report Builder
description: Saiba mais sobre rótulos restritos no Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 345
ht-degree: 36%

---

# Rótulos restritos no Report Builder

Geralmente, as configurações relacionadas à governança de dados no Customer Journey Analytics são herdadas do Experience Platform. A integração entre o Customer Journey Analytics e a Governança de dados da Experience Platform permite rotular dados sigilosos do Customer Journey Analytics e aplicar políticas de privacidade.

Os rótulos e políticas de privacidade criados em conjuntos de dados consumidos pelo Experience Platform podem ser exibidos no fluxo de trabalho de visualizações de dados do Customer Journey Analytics. Esses rótulos interrompem ou avisam os usuários que criam métricas e dimensões a partir de campos sigilosos. Para obter informações sobre conjuntos de dados, consulte [Visão geral sobre conjuntos de dados](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)

Além disso, quando dados são exportados do Customer Journey Analytics (por meio de relatórios, exportação, API etc.), avisos ou rótulos são adicionados para informar aos usuários que um relatório contém informações sigilosas que precisam ser tratadas de uma maneira específica.

Essa integração permite gerenciar a conformidade. Os administradores de dados da sua organização podem definir políticas de restrição de uso. Como resultado, os usuários do Customer Journey Analytics podem usar os dados com mais confiança, sabendo que estão em conformidade com as políticas definidas pelos administradores de dados.

Para obter mais informações, consulte [Customer Journey Analytics e governança de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)

## Exibir dados restritos

Duas políticas definidas pela Adobe são exibidas no Customer Journey Analytics e afetam os relatórios, downloads e compartilhamento:

* Política Forçar análise
* Política Forçar download

Os componentes sujeitos a essas políticas estão esmaecidos e têm um ícone ![InfoOutline](/help/assets/icons/InfoOutline.svg). Quando você passa o mouse sobre o ícone de informações, uma nota é exibida para indicar o seguinte: **[!UICONTROL Foram aplicadas políticas a este campo que proíbem o uso destes dados]**.

Para obter mais informações, consulte [Rótulos e políticas](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![A nota de política indicando uso proibido de dados.](assets/restricted-label.png){zoomable="yes"}


## Atualizar relatórios que contêm dados restritos

Nos casos em que um usuário criou um relatório do Report Builder com elementos de dados restritos posteriormente, quando o relatório for atualizado uma mensagem de erro será exibida.

![A mensagem de erro exibida após os elementos de dados serem restritos posteriormente.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
