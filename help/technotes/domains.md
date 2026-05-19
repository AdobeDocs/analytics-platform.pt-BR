---
title: Domínios usados pelo Customer Journey Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
TQID: https://experienceleague.adobe.com/d-nNfumskelDKrgCPQpyoZIagJrGcniXyQgACaHh5tA
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0145475e18cfbc3ae3a83e5e3838cdec02b57bda
workflow-type: tm+mt
source-wordcount: 163
ht-degree: 16%

---

# Domínios usados pelo Customer Journey Analytics

Algumas configurações de firewall bloqueiam domínios dos quais a Customer Journey Analytics depende para sua interface de produto. Você pode usar essa lista de domínios para alterar as configurações de rede de sua organização para permitir o acesso ao produto de dentro da organização. A Adobe recomenda permitir esses domínios por meio do firewall da sua organização para obter uma experiência ideal.

| Tecnologia | Domínio |
| --- | --- |
| Domínios do Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft® Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft® Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domínios do CX Enterprise

Além dos domínios acima, o CX Enterprise conta com vários domínios para coleta de dados e exportação de relatórios. Consulte [Domínios usados pelo CX Enterprise](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/domains) para obter esta lista de domínios.

>[!MORELIKETHIS]
>
>[Endereços IP usados pelo Customer Journey Analytics](ip-addresses.md)
>
>[Domínios usados pelo CX Enterprise](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/domains)
