---
title: Domínios usados pelo Customer Journey Analytics
description: Se o firewall da sua organização bloquear endereços IP originados da Adobe, use esta lista para atualizar as configurações do firewall.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
source-git-commit: 8ffbca5dd83987a90d7b744d236e0556314000dd
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 20%

---

# Domínios usados pelo Customer Journey Analytics

Algumas configurações de firewall bloqueiam domínios dos quais o Customer Journey Analytics depende para sua interface de produto. Você pode usar essa lista de domínios para alterar as configurações de rede de sua organização para permitir o acesso ao produto de dentro da organização. A Adobe recomenda permitir esses domínios por meio do firewall da sua organização para obter uma experiência ideal.

| Tecnologia | Domínio |
| --- | --- |
| domínios Customer Journey Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Armazenamento Microsoft® Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| CDN do Microsoft® Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Domínios da Adobe Experience Cloud

Além dos domínios acima, o Adobe Experience Cloud depende de vários domínios para a coleta de dados e exportação de relatórios. Consulte [Domínios usados pelo Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/domains) para obter esta lista de domínios.

>[!MORELIKETHIS]
>
>[Endereços IP usados pelo Customer Journey Analytics](ip-addresses.md)
>
>[Domínios usados pelo Adobe Experience Cloud](https://experienceleague.adobe.com/pt-br/docs/core-services/interface/data-collection/domains)
