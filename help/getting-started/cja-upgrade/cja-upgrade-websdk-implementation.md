---
title: Entenda as opções de implementação do SDK da web ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre as opções de implementação do SDK da web ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 94a2bf2f-ad84-4f35-af8f-b8a5d9e5c607
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 80%

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

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-no-selection"
>title="Implementar o SDK da web para a propriedade fornecida"
>abstract="Selecione o tipo de implementação desejado no guia de atualização para obter instruções mais detalhadas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-websdk-third-party"
>title="Adicionar a biblioteca de SDKs da web ao seu sistema de gerenciamento de tags de terceiros"
>abstract="Trabalhe com o administrador no sistema de gerenciamento de tags para adicionar a biblioteca de SDK da Web ao seu site.<br><br>O tempo de conclusão desta tarefa depende muito da capacidade de resposta do indivíduo responsável pelo sistema de gerenciamento de tags. A adição da biblioteca Web SDK pode ser fornecida com a lógica de implementação associada e implantada durante os ciclos de lançamento padrão de sua organização."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

O processo recomendado de atualização do Adobe Analytics para o Customer Journey Analytics é uma nova implementação do SDK da web da Experience Platform, que é o método de coleta de dados preferido para o Customer Journey Analytics.

Há três maneiras possíveis de usar o SDK da web da Adobe Experience Platform:

* [Extensão de tag do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/extension): a Adobe recomenda usar este método. Instale um carregador de tags no site e use a IU de coleta de dados da Adobe Experience Platform para configurar a implementação.

* [Biblioteca de JavaScript do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/library): referencie um arquivo da biblioteca hospedado em uma CDN ou hospede o arquivo da biblioteca na sua própria infraestrutura. Faça chamadas para a biblioteca dentro do código do seu site.

* [NPM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/npm): instale o SDK da web no site por meio do gerenciador de pacotes NPM.

Para mais informações, consulte [Visão geral da instalação do SDK da web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/overview) no Guia do SDK da web da Experience Platform.
