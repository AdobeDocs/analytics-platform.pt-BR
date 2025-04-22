---
title: Configure o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 19%

---

# Configure o Content Analytics

A configuração do Content Analytics consiste nas seguintes etapas:

![Configuração do Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Use o assistente de [configuração guiada](guided.md) do Content Analytics para orientá-lo em todas as etapas necessárias para definir os pré-requisitos de uma configuração do Content Analytics. Você pode salvar suas configurações a qualquer momento e retornar posteriormente.
1. Quando estiver familiarizado com os valores de configuração, você poderá implementá-los. Essa implementação cria todos os artefatos necessários com base no que você configurou no assistente.
1. Somente quando você [publica manualmente](manual.md) a propriedade Tags, sua configuração do Content Analytics é efetivamente implantada e a coleta de dados é iniciada.

1. Você só pode fazer pequenas alterações em uma configuração implementada usando o assistente de [configuração guiada](guided.md). Por exemplo, altere a [visualização de dados](/help/data-views/data-views.md).
1. Você pode fazer outras alterações em uma configuração implementada usando a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associadas.
1. Somente quando você [republica manualmente](manual.md) a propriedade Tags, as modificações de configuração são efetivamente implantadas e a coleta de dados, com base em suas alterações, é iniciada.


## Pré-requisitos

Antes de configurar o Content Analytics, verifique se os seguintes pré-requisitos foram atendidos:

* Você incluiu na lista de permissões o Agente do usuário e o endereço IP do serviço de recursos usado no Content Analytics. A sequência de agente do usuário a ser configurada é: <code>AdobeFeaturization/1.0</code>.
* Se você implementou o [Web SDK usando o JavaScript](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/install/library){target="_blank"} para coleta de dados comportamentais regulares, verifique se está usando o nome padrão <code>alloy</code> para a biblioteca do JavaScript.
* Você tem uma função de Administrador de produto do Customer Journey Analytics, com as permissões adicionais para gerenciar conexões e visualizações de dados.
* Se você considerar coletar experiências do Content Analytics, certifique-se de configurar e atualizar o [controle de versão do Content Analytics](manual.md#versioning) com base nas alterações das suas páginas da Web.
* Você deve ter [permissões para a coleta de dados](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Permissões do Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Permissões da Coleção de Dados do Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Você considerou cuidadosamente as seguintes opções de configuração:

   * Seu site é adequado para relatórios de experiência. O relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
      * As páginas do site devem ser reproduzíveis usando o URL da página.
      * O conteúdo de texto visto por qualquer usuário pode ser reproduzido usando o URL da página e não depende de cookies ou outros mecanismos de personalização.
   * Você tem uma compreensão clara de quais páginas deseja capturar a análise e os insights do engajamento de conteúdo.
   * Você tem uma compreensão clara sobre quais (tipos de) ativos deseja capturar a análise e os insights do envolvimento de conteúdo.


## Controle de acesso

>[!IMPORTANT]
>
>Não há nenhuma permissão do Content Analytics que você possa configurar para ativar ou desativar o acesso ao Content Analytics para usuários individuais ou grupos de usuários.
>

Para fornecer a um usuário ou grupo de usuários acesso ao Content Analytics, você deve fornecer ao usuário ou grupo de usuários acesso a uma ou mais [visualizações de dados configuradas para o Content Analytics](guided.md#data-view).

Esse acesso implica:

1. A visualização de dados habilitada para o Content Analytics é incluída como parte das permissões de Visualização de dados para um perfil de produto específico do Customer Journey Analytics.
1. Esse perfil de produto específico do Customer Journey Analytics é um dos perfis de produto atribuídos ao usuário ou grupo de usuários.

>[!MORELIKETHIS]
>
>* [Configuração guiada](guided.md)
>* [Configuração manual](manual.md)
>* [Controle de acesso](/help/technotes/access-control.md)
>
