---
title: Configurar o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: bb9b9850368796fe6cf2c4945ff3ef93b881b363
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Configurar o Content Analytics

{{release-limited-testing}}

A configuração do Content Analytics consiste nas seguintes etapas:

![Configuração do Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Use o assistente de [configuração guiada](guided.md) do Content Analytics para orientá-lo em todas as etapas necessárias para definir os pré-requisitos de uma configuração do Content Analytics. Você pode salvar suas configurações a qualquer momento e retornar posteriormente.
1. Quando estiver familiarizado com os valores de configuração, você poderá implementá-los. Essa implementação cria todos os artefatos necessários com base no que você configurou no assistente.
1. Somente quando você [publica manualmente](manual.md) a propriedade Tags, sua configuração do Content Analytics é efetivamente implantada e a coleta de dados é iniciada.

1. Você só pode fazer pequenas alterações em uma configuração implementada usando o assistente de [configuração guiada](guided.md). Por exemplo, altere a [Visualização de dados](/help/data-views/data-views.md).
1. Você pode fazer outras alterações em uma configuração implementada usando a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associadas.
1. Somente quando você [republica manualmente](manual.md) a propriedade Tags, as modificações de configuração são efetivamente implantadas e a coleta de dados, com base em suas alterações, é iniciada.


## Pré-requisitos

Antes de configurar o Content Analytics, verifique se os seguintes pré-requisitos foram atendidos:

* Você incluiu na lista de permissões o Agente do usuário e o endereço IP do serviço de recursos usado no Content Analytics. A sequência de agente do usuário a ser configurada é: <code>AdobeFeaturization/1.0</code>.
* Você tem uma função de Administrador de produto do Customer Journey Analytics, com as permissões adicionais para gerenciar conexões e visualizações de dados.
* Você deve ter [permissões para a coleta de dados](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}. Essas permissões consistem em:
   * [Permissões do Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Permissões da Coleção de Dados do Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank" }
* Você considerou cuidadosamente as seguintes opções de configuração importantes:

   * Seu site é adequado para relatórios de experiência. O relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
      * Você pode acessar o conteúdo do site somente por URLs públicos. O acesso ao site não requer tokens personalizados, cookies ou outros mecanismos não disponíveis por meio do URL.
      * As páginas do site podem ser reproduzidas usando o URL da página, e você entende quais parâmetros opcionais de URL geram experiências.
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
