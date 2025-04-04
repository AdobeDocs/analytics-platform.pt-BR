---
title: Coleção de dados do Content Analytics
description: Uma visão geral de como os dados são coletados no Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: 02d24416bd1f56417005dfa1b693964073fb8a59
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 1%

---

# Coleção de dados do Content Analytics

{{release-limited-testing}}

Este artigo explica em detalhes como o Analytics de conteúdo coleta dados


## Definições

As seguintes definições são usadas no contexto deste artigo:

* **Experiência**: uma experiência é definida como o conteúdo de texto em uma página da Web inteira. Para a coleta de dados, o Content Analytics registra a Experience ID, que se baseia no url da página. Posteriormente, o texto na página é capturado por meio do serviço de recuperação.
* **Experience ID**: uma combinação exclusiva de URL relevante (URL base mais quaisquer parâmetros que direcionem o conteúdo da página) e [versão da experiência](manual.md#versioning).
   * Você especifica, como parte da [configuração](configuration.md), quais parâmetros são relevantes para qualquer URL completa.
   * Você pode definir o [identificador de versão](manual.md#versioning) que é usado.
* **Ativo**: uma imagem. O Content Analytics registra o URL do ativo.
* **ID do ativo**: a URL do ativo.
* **URL relevante**: a URL base mais quaisquer parâmetros que direcionem o conteúdo na página.


## Funcionalidade

A biblioteca do Content Analytics coleta dados quando:

* O Content Analytics está incluído na biblioteca de tags carregada na página.
* A URL da página está configurada na [extensão do Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte da biblioteca de marcas incluída.


## Evento do Content Analytics

Um evento do Content Analytics consiste em:

* Campos padrão
   * Carimbo de data e hora
   * Identidade
* Visualizações de experiência (se houver e se configurado)
* Cliques de experiência (se houver e se estiver configurado)
* Exibições de ativos (se houver e se configurado)
* Cliques no ativo (se houver e se estiver configurado)


Os eventos do Content Analytics são coletados como uma sequência de:

1. [Uma exibição gravada ou clique](#recorded-view-or-click).
1. [Um evento (comportamental) regular ou específico](#regular-or-specific-behaviorial-event).

A Content Analytics coleta dados dessa maneira para refletir essa sequência, em vez de coletar uma exibição ou clicar separadamente da coleta do evento imediatamente após essa exibição ou clique. Essa maneira de coletar dados de análise de conteúdo também reduz a quantidade de dados coletados.

### Exibição gravada ou clique

Uma exibição de ativo é registrada quando:

* O ativo não foi excluído de acordo com a configuração de extensão do Content Analytics.
* O ativo é de 75% na visualização.
* Esse ativo ainda não foi registrado para esta página.

Um clique de ativo é registrado quando:

* O ativo foi visualizado.
* O ativo não foi excluído de acordo com a configuração de extensão do Content Analytics.
* Um clique diretamente no ativo, que é um link, que leva a outra página.

Uma visualização de experiência é registrada quando:

* As experiências são ativadas na configuração do Content Analytics.

Um clique de experiência é registrado quando:

* Qualquer clique ocorre em um link na página para a qual as experiências estão habilitadas.


### Evento regular ou específico (comportamental)

Os acionadores para acionar um evento regular ou específico (comportamental) no contexto do Content Analytics são:

* O Web SDK ou o AppMeasurement envia um evento.
* A visibilidade muda para oculta, por exemplo:
   * Descarregamentos de página
   * Alternar guia
   * Minimizar navegador
   * Fechar navegador
   * Tela de bloqueio
* O URL muda, o que resulta em um URL relevante modificado.
* As exibições de ativos registradas e prontas para serem enviadas excedem o número de 32.


## Esquemas

Os dados do Content Analytics são coletados em conjuntos de dados no Experience Platform, com base em esquemas específicos do Content Analytics. Os esquemas de referência estão disponíveis publicamente:

* [Esquema de ativo digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiência digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema do conteúdo do evento de experiência](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
