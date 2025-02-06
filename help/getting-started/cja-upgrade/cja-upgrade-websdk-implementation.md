---
title: Entenda as opções de implementação do Web SDK ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre as opções de implementação do Web SDK ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 971600fcc7d8a5aac4ad39812ab4a7af69d45ccc
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Entenda as opções de implementação do Web SDK ao atualizar para o Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Biblioteca JavaScript do Web SDK (alloy.js)"
>abstract="Inclua a biblioteca do Web SDK (alloy.js) em cada página do seu site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extensão de tag do Web SDK"
>abstract="(Recomendado) Se você ainda não estiver usando tags, instale o carregador de tags no site. Se você já estiver usando tags, poderá adicionar a extensão Web SDK à propriedade da tag. Essa opção inclui implementações que usam tags na Coleção de dados da Adobe Experience Platform e em sistemas de gerenciamento de tags de terceiros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Pacote NPM"
>abstract="Use a API de coleção de dados para enviar dados diretamente para um fluxo de dados. Há suporte para os tipos não autenticados (cliente para servidor) e autenticados (servidor para servidor)."

<!-- markdownlint-enable MD034 -->

O processo recomendado de atualização do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido para o Customer Journey Analytics.

Há três maneiras compatíveis de usar o Adobe Experience Platform Web SDK:

* [Extensão de tag do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): a Adobe recomenda o uso desse método. Instale um carregador de tags no site e use a interface da Coleção de dados da Adobe Experience Platform para configurar a implementação.

* [Biblioteca JavaScript do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): faça referência a um arquivo de biblioteca hospedado em CDN ou hospede o arquivo de biblioteca usando sua própria infraestrutura. Faça chamadas para a biblioteca dentro do código do site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): instale o Web SDK no site usando o gerenciador de pacotes NPM.

Para obter mais informações, consulte [visão geral da instalação do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) no Experience Platform Web SDK Guide.



