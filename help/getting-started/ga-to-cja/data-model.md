---
title: Como o modelo de dados do GA4 é mapeado para o Customer Journey Analytics
description: Entenda como o modelo de dados baseado em eventos do GA4 traduz para esquemas XDM e conjuntos de dados na Customer Journey Analytics.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: a5f9e2c7-3b1d-4a8e-b6f0-2c9d7e4a5180
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 692
ht-degree: 0%

---


# Como o modelo de dados do GA4 é mapeado para o Customer Journey Analytics

GA4 e Customer Journey Analytics são plataformas baseadas em eventos, o que torna a conversão do modelo de dados entre elas mais direta do que era do Universal Analytics. Entender como os eventos e parâmetros do GA4 correspondem aos campos XDM e conjuntos de dados da Customer Journey Analytics facilita a interpretação de relatórios e a colaboração com a equipe de implementação.

## Modelo de dados do GA4 baseado em eventos

Toda interação em GA4 é um **evento**: uma ação nomeada com um conjunto opcional de **parâmetros** que fornecem contexto. Não há tipos de objetos separados para exibições de página, sessões ou metas — todos são eventos.

| Tipo de evento GA4 | Exemplos |
|---|---|
| Coletado automaticamente | `page_view`, `session_start`, `first_visit`, `scroll` |
| Medição aprimorada | `file_download`, `video_start`, `form_submit` |
| Recomendado | `purchase`, `add_to_cart`, `sign_up` |
| Personalizado | Qualquer nome de evento que você definir |

Cada evento pode transportar até 25 parâmetros. Por exemplo, um evento `purchase` normalmente inclui `transaction_id`, `value`, `currency` e `items` como parâmetros.

## Como o Customer Journey Analytics armazena dados

O Customer Journey Analytics obtém os dados do **Adobe Experience Platform**. Os dados na Platform são armazenados em **conjuntos de dados**, cada um em conformidade com um **esquema** criado usando o **Experience Data Model (XDM)**. O XDM é o padrão aberto da Adobe para representar dados de experiência do cliente.

Há três tipos de conjunto de dados usados no Customer Journey Analytics:

| Tipo de conjunto de dados do CJA | GA4 equivalente | O que ele contém |
|---|---|---|
| [!UICONTROL Conjunto de dados de evento] | Fluxo de eventos do GA4 | Interações de série temporal (exibições de página, cliques, compras) |
| [!UICONTROL Conjunto de dados de perfil] | Propriedades do usuário do GA4 | Atributos de nível de pessoa (campos de CRM, status de fidelidade, demografia) |
| [!UICONTROL Conjunto de dados de pesquisa] | Dimensões personalizadas do GA4 usadas como tabelas de referência | Dados de referência do valor principal (catálogo de produtos, nomes de campanha) |

O Customer Journey Analytics não tem eVars, propriedades ou eventos de sucesso. Todas as dimensões e métricas são originadas diretamente dos campos de esquema XDM. Não há limites para o número de valores de dimensões únicas.

## Eventos coletados automaticamente

O GA4 coleta automaticamente um conjunto de eventos por meio de sua SDK. A tabela a seguir mapeia esses eventos para seus equivalentes XDM ou Customer Journey Analytics.

| Evento GA4 coletado automaticamente | Equivalente XDM / Customer Journey Analytics |
|---|---|
| `page_view` | `xdm.web.webPageDetails.pageViews` (campo XDM padrão) |
| `session_start` | Início da sessão (automático, por definição de sessão de visualização de dados) |
| `first_visit` | Segmento [!UICONTROL Primeira sessão] |
| `scroll` | Evento personalizado (requer mapeamento de implementação explícito) |
| `click` | `xdm.web.webInteraction` campos (requer implementação) |
| `video_start` / `video_complete` | Campos de esquema da Coleção de mídia (com os serviços de streaming de mídia da Adobe) |
| `purchase` | `xdm.commerce.purchases`, `xdm.commerce.order` (esquema de comércio XDM padrão) |
| `add_to_cart` | `xdm.commerce.productListAdds` (esquema de comércio XDM padrão) |

>[!NOTE]
>
>Vários eventos de medição aprimorados do GA4 (como rolagem, download de arquivo ou vídeo) exigem mapeamento explícito para campos XDM ao implementar o usando o Web SDK. Eles não coletam automaticamente da mesma forma que o SDK do GA4 os trata.

## Eventos e parâmetros personalizados

No GA4, os eventos personalizados têm um nome e até 25 parâmetros. No Customer Journey Analytics, os eventos personalizados são mapeados para campos de esquema XDM personalizados definidos durante a implementação:

* O **nome do evento** torna-se um valor de campo em um campo XDM (normalmente [`xdm.eventType`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/classes/experienceevent)).
* Cada **parâmetro** torna-se um campo de esquema XDM separado. Qualquer campo XDM pode ser exposto como uma dimensão ou métrica ao [configurar uma visualização de dados](/help/data-views/component-settings/overview.md).

>[!NOTE]
>
>Os caminhos de campo XDM específicos para os eventos personalizados da sua organização são determinados durante a implementação do Web SDK. Trabalhe com a equipe de implementação para entender o mapeamento de campo específico antes de criar relatórios. Consulte [Arquiteto do esquema](../cja-upgrade/cja-upgrade-schema-architect.md) para obter mais informações.

## Propriedades do usuário

As propriedades do usuário do GA4 são atributos persistentes definidos em um usuário (por exemplo, `membership_tier` ou `account_type`). No Customer Journey Analytics, eles são mapeados para **Conjuntos de dados de perfil** na Platform.

Um conjunto de dados de Perfil é assimilado separadamente dos dados do evento e unido a ele no Customer Journey Analytics usando uma ID de pessoa compartilhada. As IDs de pessoa comuns usadas neste contexto incluem uma ID do cliente ou um hash de email. Depois de unidos, esses atributos de perfil ficam disponíveis como dimensões no Analysis Workspace junto com seus dados de nível de evento.

Essa abordagem oferece ao Customer Journey Analytics mais flexibilidade do que o modelo de propriedades de usuário do GA4: o GA4 limita você às propriedades de usuário definidas no SDK, enquanto os conjuntos de dados do Perfil do Customer Journey Analytics podem incluir qualquer atributo de qualquer sistema (CRM, plataforma de fidelidade, registros de suporte), desde que compartilhe um identificador unido.

Se sua organização ainda precisar trazer dados do GA para a Adobe Experience Platform, consulte [Assimilar dados históricos do Google Analytics](/help/use-cases/third-party/ga/backfill.md) e [Configurar transmissão de dados do Google Analytics](/help/use-cases/third-party/ga/streaming.md) para obter os guias de configuração voltados para o administrador.
