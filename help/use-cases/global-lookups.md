---
title: Adicionar pesquisas globais aos seus conjuntos de dados
description: Use pesquisas globais para aumentar os relatórios com dimensões úteis no Customer Journey Analytics.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: ht
source-git-commit: 26ee2b61fb80b55a7982d90941ec121547423cfc
workflow-type: ht
source-wordcount: '312'
ht-degree: 100%

---

# Adicionar pesquisas globais aos seus conjuntos de dados

Pesquisas globais aprimoram a capacidade do Customer Journey Analytics de relatar algumas dimensões/atributos que não são úteis por si mesmos, mas são úteis quando unidos a outros dados. Exemplos incluem atributos de dispositivos móveis e atributos de dimensões de SO e navegador, como números de versão do navegador. Uma &quot;Pesquisa global&quot; é semelhante a um conjunto de dados de pesquisa. As pesquisas globais são aplicáveis em organizações da Experience Cloud. Elas são automaticamente aplicadas a todos os conjuntos de dados de evento que contêm determinados campos de esquema XDM (veja abaixo os campos específicos). Existe um conjunto de dados de pesquisa global para cada localização de esquema que a Adobe está classificando.

No Adobe Analytics tradicional, essas dimensões são exibidas sozinhas, enquanto no CJA, é necessário incluir essas dimensões ativamente ao criar visualizações de dados. No fluxo de trabalho Conexões, você seleciona um conjunto de dados que é sinalizado com uma chave para pesquisa global. A interface de Exibições de dados inclui automaticamente todas as dimensões de pesquisa globais disponíveis para relatórios. Os arquivos de pesquisa são automaticamente mantidos atualizados e disponíveis em todas as regiões e para todas as contas. Eles são armazenados em organizações específicas da região associadas ao cliente.

## Usar pesquisas globais com conjuntos de dados do Conector de dados da Adobe

Os conjuntos de dados de pesquisa global são aplicados automaticamente no momento do relatório. Se você estiver usando o Conector de dados do Analytics e trouxer uma dimensão para a qual a Adobe fornece uma pesquisa global, aplicaremos automaticamente essa pesquisa global. Se um conjunto de dados de evento contiver campos XDM, poderemos aplicar pesquisas globais a ele.

## Campos de pesquisa global disponíveis

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

## Relatório sobre dimensões de pesquisa global

Para relatar as dimensões de pesquisa global, é necessário adicioná-las ao criar uma visualização de dados no Customer Journey Analytics:

![](assets/global-lookup.png)

Você poderá ver os dados de pesquisa no Workspace:

![](assets/gl-reporting.png)
