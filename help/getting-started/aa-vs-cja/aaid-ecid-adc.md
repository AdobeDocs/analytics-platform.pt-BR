---
title: AAID, ECID, AACUSTOMID e o conector de origem do Analytics
description: Saiba como o conector de origem do Analytics lida com campos de identidade do Adobe Analytics.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 73%

---

# AAID, ECID, AACUSTOMID e o conector de origem do Analytics

Os dados do Adobe Analytics contêm vários campos de identidade. Três importantes campos de identidade recebem tratamento especial pela [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR): AAID, ECID, AACUSTOMID.

## AAID

A Adobe Analytics ID (AAID) é o principal identificador de dispositivo no Adobe Analytics e sua presença está garantida em cada evento transmitido pelo conector de origem do Analytics. Às vezes, a AAID é chamada de “ID do Analytics legada” ou id do cookie `s_vi`. No entanto, uma AAID é criada mesmo se o cookie `s_vi` não está presente. A AAID é representada pelas colunas `post_visid_high/post_visid_low` em [Feeds de dados do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR#columns%2C-descriptions%2C-and-data-types).

No conector de origem do Analytics, a AAID é transformada em `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. O campo AAID em um determinado evento contém uma única identidade que pode ser um dos vários tipos diferentes, conforme descrito em [Ordem de operação das IDs do Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=pt-BR%5B%5D). (Em um conjunto de relatórios inteiro, a AAID pode conter uma combinação de tipos entre eventos. O tipo para cada evento é indicado na variável `post_visid_type` nos feeds de dados do Analytics.) Consulte também: [Referência da coluna de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR).

## ECID

A ECID (Experience Cloud ID), também conhecida como MCID (ID do Marketing Cloud), é um campo de identificador de dispositivo separado, preenchido no Adobe Analytics quando o Analytics é implementado usando o [Serviço de identidade da Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=pt-BR). A ECID é representada pela coluna `mcvisid` nos feeds de dados do Adobe Analytics.

Se uma ECID existir em um evento, a AAID poderá se basear na ECID, dependendo se o [período de carência](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=pt-BR) do Analytics está configurado. Consulte também: [Solicitações do Analytics e da Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=pt-BR).

## AACUSTOMID

AACUSTOMID é um campo de identificador separado, preenchido no Adobe Analytics com base no uso da variável `s.VisitorID` na implementação do Analytics. A AACUSTOMID é representada pela coluna `cust_visid` nos feeds de dados do Adobe Analytics. Se a AACUSTOMID estiver presente, a AAID será baseada na AACUSTOMID. (AACUSTOMID agrupa todos os outros identificadores, conforme definido pela ordem de operações mencionada acima.)

## Como o conector de origem do Analytics trata essas identidades

O conector de origem do Analytics transmite essas identidades para o Adobe Experience Platform no formato XDM como:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Esses campos não são marcados como identidades. Em vez disso, as mesmas identidades são copiadas para o **_identityMap_** do XDM como pares de valores-chave, da seguinte maneira:

* `{ "key": "AAID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "ECID", "value": [ { "id": "<identity>", "primary": <true or false> } ] }`
* `{ "key": "AACUSTOMID", "value": [ { "id": "<identity>", "primary": false } ] }`

Os itens entre colchetes angulares &lt;> representam locais onde os valores reais seriam exibidos.

No identityMap:

* Se a ECID estiver presente, ela será marcada como a identidade principal do evento. Observe que, nesse caso, a AAID pode se basear na ECID de acordo com a discussão acima.
Caso contrário, a AAID é marcada como a identidade principal do evento.
* AACUSTOMID nunca é marcada como a ID principal do evento. No entanto, se AACUSTOMID estiver presente, a AAID é baseado na AACUSTOMID de acordo com a discussão acima.

## Customer Journey Analytics e ID primária

No que diz respeito ao Customer Journey Analytics, a definição de ID principal só é importante se você decidir usar a ID principal como a ID de pessoa. Mas não é obrigatório fazer isso. Você pode escolher alguma outra coluna de identidade como a ID de pessoa.
