---
title: Configure o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 85%

---

# Configure o Content Analytics

Este artigo documenta, em um nível superior, como configurar o Content Analytics.

Antes de configurar o Content Analytics, verifique se os [pré-requisitos](#prerequisites) foram atendidos, se você tem o [controle de acesso](#access-control) necessário e se tem conhecimento das [limitações](#limitations).


Etapas de alto nível

![Configuração da análise de conteúdo](../assets/aca-configuration.svg){zoomable="yes"}

1. Use o [assistente de configuração guiada](guided.md) da análise de conteúdo para guiar você por todas as etapas necessárias para definir os pré-requisitos de configuração da análise de conteúdo. Você pode salvar as configurações a qualquer momento e retornar mais tarde.
1. Após definir os valores de configuração desejados, você pode implementá-los. Esta implementação cria todos os artefatos necessários, com base no que você configurou no assistente.
1. Para que sua configuração da análise de conteúdo seja efetivamente implantada e a coleta de dados seja iniciada, primeiro é necessário [publicar manualmente](manual.md) a propriedade de tags.

1. Só é possível fazer algumas pequenas alterações em uma configuração implementada usando o assistente de [configuração guiada](guided.md). Por exemplo, alterar a [visualização de dados](/help/data-views/data-views.md).
1. É possível fazer outras alterações em uma configuração implementada usando a [extensão de análise de conteúdo da Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade de tags associada.
1. Somente após [republicar manualmente](manual.md) a propriedade de tags, as modificações de configuração serão efetivamente implantadas e a coleção de dados, com base em suas alterações, será iniciada.


## Pré-requisitos

Antes de configurar a análise de conteúdo, verifique se os seguintes pré-requisitos foram atendidos:

* Você incluiu na lista de permissões o agente de usuário e o endereço IP do serviço de recursos usado na análise de conteúdo. A string de agente do usuário a ser configurada é: <code>AdobeFeaturization/1.0</code>.
* Se você implementou o [SDK da web usando o JavaScript](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/library){target="_blank"} para coleta regular de dados comportamentais, verifique se está usando o nome padrão <code>alloy</code> para a biblioteca do JavaScript.
* Você tem uma função de admin de produto do Customer Journey Analytics, com permissões adicionais para gerenciar conexões e visualizações de dados.
* Se você pretende coletar experiências da análise de conteúdo, configure e atualize o [controle de versão da análise de conteúdo](manual.md#versioning) com base nas alterações em suas páginas da web.
* Você deve ter [permissões para a coleta de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Permissões da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Permissões para coleta de dados da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Você considerou cuidadosamente as seguintes opções de configuração:

   * Seu site é adequado para relatórios de experiência. Criar um relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
      * As páginas do site devem ser reproduzíveis usando o URL da página.
      * O conteúdo de texto visualizado por qualquer usuário possa ser reproduzido usando o URL da página e não dependa de cookies ou outros mecanismos de personalização.
   * Você tem uma compreensão clara de quais páginas deseja capturar a análise e os insights do engajamento de conteúdo.
   * Você tem uma compreensão clara sobre quais (tipos de) ativos deseja capturar a análise e os insights do envolvimento de conteúdo.


## Controle de acesso

>[!IMPORTANT]
>
>Não há nenhuma permissão de análise de conteúdo que você possa configurar para habilitar ou desabilitar o acesso da análise de conteúdo para usuários individuais ou grupos de usuários.
>

Para fornecer a um usuário ou grupo de usuários acesso à análise de conteúdo, você deve fornecer ao usuário ou grupo de usuários o acesso a uma ou mais [visualizações de dados configuradas para a análise de conteúdo](guided.md#data-view).

Esse acesso exige que:

1. A visualização de dados habilitada para análise de conteúdo esteja incluída como parte das permissões de visualização de dados de um perfil de produto específico do Customer Journey Analytics.
1. Esse perfil específico de produto do Customer Journey Analytics seja um dos perfis de produto atribuídos ao usuário ou grupo de usuários.

## Limitações

O esquema usado para os dados de evento do Content Analytics pertence ao sistema. Um schema de propriedade do sistema não pode ser modificado, o que implica:

* Não é possível incluir grupos de campos para o suporte de funcionalidades como geolocalização, detecção de bot ou pesquisa de dispositivo.
* Não é possível adicionar um identificador específico para oferecer suporte à [compilação em campo](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Configuração guiada](guided.md)
>* [Configuração manual](manual.md)
>* [Controle de acesso](/help/technotes/access-control.md)
>
