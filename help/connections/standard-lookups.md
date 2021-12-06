---
title: Adicionar pesquisas padrão aos seus conjuntos de dados
description: Use pesquisas padrão para aumentar os relatórios com dimensões úteis no Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: 067502a0d69bd0b085ecb5e6cbd3ae062f33daef
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 28%

---

# Adicionar pesquisas padrão aos seus conjuntos de dados

>[!IMPORTANT]
>As Pesquisas padrão só estão disponíveis para fontes de dados do Conector de dados do Analytics no CJA. Você só pode usá-los se usar a variável [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) ou as APIs de coleta de dados do Experience Platform.

As pesquisas padrão (também conhecidas como pesquisas fornecidas por Adobe) aprimoram a capacidade do Customer Journey Analytics de relatar em algumas dimensões/atributos que não são úteis por si só, mas são úteis quando unidas a outros dados. Exemplos incluem atributos de dispositivos móveis e atributos de dimensões de SO e navegador, como números de versão do navegador. Uma &quot;Pesquisa padrão&quot; é semelhante a um conjunto de dados de pesquisa. As pesquisas padrão são aplicáveis em organizações de Experience Cloud. Elas são automaticamente aplicadas a todos os conjuntos de dados de evento que contêm determinados campos de esquema XDM (veja abaixo os campos específicos). Existe um conjunto de dados de pesquisa padrão para cada localização de esquema que o Adobe está classificando.

No Adobe Analytics tradicional, essas dimensões são exibidas sozinhas, enquanto no CJA, é necessário incluir essas dimensões ativamente ao criar visualizações de dados. No workflow Conexões , você seleciona um conjunto de dados que é sinalizado como um com uma chave para pesquisa padrão. A interface do usuário de Exibições de dados sabe automaticamente incluir todas as dimensões de pesquisa padrão, conforme disponíveis para relatórios. Os arquivos de pesquisa são automaticamente mantidos atualizados e disponíveis em todas as regiões e para todas as contas. Eles são armazenados em organizações específicas da região associadas ao cliente.

## Usar pesquisas padrão com conjuntos de dados do Adobe Data Connector

Os conjuntos de dados de pesquisa padrão são aplicados automaticamente no momento do relatório. Se você usar o Conector de dados do Analytics e trazer uma dimensão para a qual o Adobe fornece uma pesquisa padrão, nós aplicamos automaticamente essa pesquisa padrão. Se um conjunto de dados de evento contiver campos XDM, poderemos aplicar pesquisas padrão a ele.

### Campos de pesquisa padrão disponíveis

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Relatório sobre dimensões de pesquisa padrão

Para criar relatórios sobre as dimensões de pesquisa padrão, é necessário adicioná-las ao criar uma visualização de dados no Customer Journey Analytics:

![](assets/global-lookup.png)

Você poderá ver os dados de pesquisa no Workspace:

![](assets/gl-reporting.png)
