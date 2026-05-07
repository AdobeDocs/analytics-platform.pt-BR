---
title: Configure o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: beb2e35354d3da1fe6d22f4221e30ff0ccde3138
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 77%

---

# Configure o Content Analytics

Este artigo documenta, em alto nível, como configurar o Content Analytics.

Antes de configurar o Content Analytics, verifique se os [pré-requisitos](#prerequisites) foram atendidos, se você tem o [controle de acesso](#access-control) necessário e se tem conhecimento das [limitações](#limitations).


Etapas de alto nível

![Configuração do Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Use o [assistente de configuração guiada](guided.md) do Content Analytics para guiar você por todas as etapas necessárias para definir os pré-requisitos de configuração do Content Analytics. Você pode salvar as configurações a qualquer momento e retornar mais tarde.
1. Após definir os valores de configuração desejados, você pode implementá-los. Esta implementação cria todos os artefatos necessários, com base no que você configurou no assistente.
1. Somente quando você [publica manualmente](manual.md) a propriedade Tags é que sua configuração do Content Analytics é efetivamente implantada e a coleta de dados é iniciada.

1. Só é possível fazer algumas pequenas alterações em uma configuração implementada usando o assistente de [configuração guiada](guided.md). Por exemplo, alterar a [visualização de dados](/help/data-views/data-views.md).
1. Você pode fazer outras alterações em uma configuração implementada usando a extensão Adobe Content Analytics na propriedade Tags associada para [web](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview) ou [mobile](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).
1. As modificações de configuração são efetivamente implantadas e a coleta de dados só é iniciada quando você republica manualmente a propriedade Tags.


## Pré-requisitos

Antes de configurar o Content Analytics, verifique se os seguintes pré-requisitos foram atendidos:

### Web

* Você incluiu na lista de permissões o agente de usuário e o endereço IP do serviço de recursos usado no Content Analytics. A string de agente do usuário a ser configurada é: <code>AdobeFeaturization/1.0</code>.
* Se você implementou o [SDK da web usando o JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library){target="_blank"} para coleta regular de dados comportamentais, verifique se está usando o nome padrão <code>alloy</code> para a biblioteca do JavaScript.
* Você tem uma função de admin de produto do Customer Journey Analytics, com permissões adicionais para gerenciar conexões e visualizações de dados.
* Se decidir coletar experiências do Content Analytics, certifique-se de configurar e atualizar o controle de versão do Content Analytics com base nas alterações nas suas páginas da Web.
* Você deve ter [permissões para a coleta de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"} permissões.
   * [Permissões de Coleção de dados do Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.
* Você considerou cuidadosamente as seguintes opções de configuração:

   * Seu site é adequado para relatórios de experiência. Criar um relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
      * As páginas do site devem ser reproduzíveis usando o URL da página.
      * O conteúdo de texto visualizado por qualquer usuário possa ser reproduzido usando o URL da página e não dependa de cookies ou outros mecanismos de personalização.
   * Você tem uma compreensão clara de quais páginas deseja capturar para análise e insights de envolvimento de conteúdo.
   * Você tem uma compreensão clara sobre quais (tipos de) ativos deseja capturar a análise e os insights do engajamento com o conteúdo.

### Dispositivo móvel

* Verifique se as extensões do [Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) e do [Experience Platform Identity for Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) estão habilitadas para o aplicativo móvel.
* Você tem uma função de admin de produto do Customer Journey Analytics, com permissões adicionais para gerenciar conexões e visualizações de dados.
* Você deve ter [permissões para a coleta de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"} permissões.
   * [Permissões de Coleção de dados do Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}.



## Controle de acesso

>[!IMPORTANT]
>
>Não há nenhuma permissão do Content Analytics que você possa configurar para habilitar ou desabilitar o acesso do Content Analytics para usuários individuais ou grupos de usuários.
>

Para fornecer a um usuário ou grupo de usuários acesso ao Content Analytics, você deve fornecer ao usuário ou grupo de usuários o acesso a uma ou mais [visualizações de dados configuradas para o Content Analytics](guided.md#data-view).

Esse acesso exige que:

1. A visualização de dados habilitada para o Content Analytics esteja incluída como parte das permissões de visualização de dados de um perfil de produto específico do Customer Journey Analytics.
1. Esse perfil específico de produto do Customer Journey Analytics seja um dos perfis de produto atribuídos ao usuário ou grupo de usuários.

## Limitações

O esquema usado para os dados de evento do Content Analytics pertence ao sistema. Um esquema de propriedade do sistema não pode ser modificado, o que implica:

* Não ser possível incluir grupos de campos para o suporte de funcionalidades como geolocalização, detecção de bots ou pesquisa de dispositivo.
* Não é possível adicionar um identificador específico para oferecer suporte à [compilação com base em campo](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Configuração guiada](guided.md)
>* [Configuração manual](manual.md)
>* [Controle de acesso](/help/technotes/access-control.md)
>
