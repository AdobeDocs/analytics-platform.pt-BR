---
title: AAID, ECID, AACUSTOMID e o conector de origem do Analytics
description: Saiba como o Conector de origem do Analytics lida com campos de identidade do Adobe Analytics.
source-git-commit: 348f4e8596146f7ff4234535fa76a54f7be33171
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 9%

---


# AAID, ECID, AACUSTOMID e o conector de origem do Analytics

Os dados do Adobe Analytics contêm vários campos de identidade. Três importantes campos de identidade recebem tratamento especial pela [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR): AAID, ECID, AACUSTOMID.

## AAID

A Adobe Analytics ID (AAID) é o principal identificador de dispositivo no Adobe Analytics e tem certeza de que existe em cada evento transmitido pelo Conector de origem do Analytics. Às vezes, o AAID é chamado de &quot;ID do Analytics herdada&quot; ou `s\_vi cookie id`. No entanto, um AAID é criado mesmo se a variável `s\_vi` cookie não está presente. O AAID é representado pelo `_post\_visid\_high/post\_visid\_low_` colunas em [Feeds de dados do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR#columns%2C-descriptions%2C-and-data-types).

No Conector de origem do Analytics, o AAID é transformado em `HEX(post_visid_high) + "-" + HEX(host_visid_low)`. O campo AAID em um determinado evento contém uma única identidade que pode ser um dos vários tipos diferentes, conforme descrito em [Ordem de operação das IDs do Analytics](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Em um conjunto de relatórios inteiro, o AAID pode conter uma combinação de tipos entre eventos. O tipo para cada ocorrência é indicado na variável `_[post\_]visid\_type_` nos feeds de dados do Analytics.) Consulte também: [Referência da coluna de dados](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=pt-BR).

## ECID

A ECID (Experience Cloud ID), também conhecida como MCID (ID do Marketing Cloud), é um campo de identificador de dispositivo separado, preenchido no Adobe Analytics quando o Analytics é implementado usando o [Serviço de identidade do Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=pt-BR). A ECID é representada pela `_mcvisid_` nos feeds de dados do Adobe Analytics.

Se uma ECID existir em um evento, a AAID poderá se basear na ECID, dependendo se o Analytics [período de carência](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=pt-BR) está configurado. Consulte também: [Solicitações do Analytics e do Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID é um campo de identificador separado, preenchido no Adobe Analytics com base no uso da variável `s.VisitorID` na implementação do Analytics. O AACUSTOMID é representado pela variável `_cust_visid_` nos feeds de dados do Adobe Analytics. Se AACUSTOMID estiver presente, a AAID será baseada em AACUSTOMID. (AACUSTOMID agrupa todos os outros identificadores, conforme definido pela ordem de operações mencionada acima.)

## Como o Conector de origem do Analytics trata essas identidades

O Conector de origem do Analytics transmite essas identidades para a Adobe Experience Platform no formato XDM como:

* `endUserIDs.\_experience.aaid.id`
* `endUserIDs.\_experience.mcid.id`
* `endUserIDs.\_experience.aacustomid.id`

Esses campos não são marcados como identidades. Em vez disso, as mesmas identidades são copiadas para o **_identityMap_** como pares de valores-chave, da seguinte maneira:

* `{ “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_**} ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_** } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }`

Dentro do identityMap:

* Se a ECID estiver presente, ela será marcada como a identidade primária do evento. Observe que, nesse caso, o AAID pode se basear na ECID de acordo com a discussão acima.
Caso contrário, AAID é marcado como a identidade primária do evento.
* AACUSTOMID nunca é marcada como a ID primária do evento. No entanto, se AACUSTOMID estiver presente, o AAID é baseado no AACUSTOMID de acordo com a discussão acima.

No que diz respeito ao CJA, a definição de ID primária só é importante se o usuário final decidir usar a ID primária como a ID de pessoa. Mas não é obrigatório fazê-lo. O usuário pode escolher alguma outra coluna de identidade como a ID de pessoa.

