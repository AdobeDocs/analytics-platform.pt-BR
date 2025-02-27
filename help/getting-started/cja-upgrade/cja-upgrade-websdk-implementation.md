---
title: Entenda as opções de implementação do SDK da web ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre as opções de implementação do Web SDK ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 43%

---

# Entenda as opções de implementação do SDK da web ao atualizar para o Customer Journey Analytics {#web-sdk-implementation-options}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-js"
>title="Biblioteca JavaScript do SDK da web (alloy.js)"
>abstract="Inclua a biblioteca do SDK da web (alloy.js) em cada página do seu site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-tags"
>title="Extensão da tag do SDK da web"
>abstract="(Recomendado) Se você ainda não estiver usando tags, instale o carregador de tags no site. Se você já estiver usando tags, poderá adicionar a extensão do SDK da web à propriedade da tag. Essa opção inclui implementações que usam tags na coleção de dados da Adobe Experience Platform e em sistemas de gerenciamento de tags de terceiros."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-api"
>title="Pacote NPM"
>abstract="Use a API de coleção de dados para enviar dados diretamente para uma sequência de dados. Há suporte para os tipos não autenticados (cliente para servidor) e autenticados (servidor para servidor)."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

O processo recomendado para atualizar do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do Experience Platform Web SDK, que é o método de coleta de dados preferido do Customer Journey Analytics.

Há três maneiras compatíveis de usar o Adobe Experience Platform Web SDK:

* [Extensão de marca do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/extension): a Adobe recomenda usar esse método. Instale um carregador de tags no site e use a interface da Coleção de dados da Adobe Experience Platform para configurar a implementação.

* [Biblioteca JavaScript do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library): faça referência a um arquivo de biblioteca hospedado em CDN ou hospede o arquivo de biblioteca usando sua própria infraestrutura. Faça chamadas para a biblioteca dentro do código do site.

* [NPM](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/npm): instale o Web SDK no site usando o gerenciador de pacotes NPM.

Para obter mais informações, consulte [visão geral da instalação do Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/overview) no Guia do Experience Platform Web SDK.



