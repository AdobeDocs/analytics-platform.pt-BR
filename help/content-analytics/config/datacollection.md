---
title: Coleta de dados do Content Analytics
description: Uma visão geral de como os dados são coletados no Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: e8cba64e706a456861fd8392ce9260b7a1c4636b
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 100%

---

# Coleta de dados do Content Analytics

Este artigo explica em detalhes como o Content Analytics coleta dados

## Definições

As seguintes definições são usadas no contexto deste artigo:

* **Experiência**: uma experiência é definida como o conteúdo de texto em uma página da web inteira. Para a coleta de dados, o Content Analytics registra a ID da experiência, que é baseada no URL da página. Mais tarde, o texto na página é capturado por meio do serviço de recuperação.
* **ID de experiência**: uma combinação exclusiva do URL relevante (URL de base e quaisquer parâmetros que direcionam o conteúdo na página) e da [versão da experiência](manual.md#versioning).
   * Você especifica, como parte da [configuração](configuration.md), quais parâmetros são relevantes para qualquer URL completo.
   * Você define um [identificador de versão](manual.md#versioning) que será usado para coletar adequadamente as alterações em suas experiências.
* **Ativo**: uma imagem. O Content Analytics registra o URL do ativo.
* **ID do ativo**: o URL do ativo.
* **URL relevante**: o URL de base e quaisquer parâmetros que direcionem o conteúdo na página.


## Funcionalidade

O Content Analytics exige o SDK da web da Experience Platform Edge Network para a coleta de dados de evento de conteúdo. Essa coleta de dados de evento é combinada com a coleta de dados de evento comportamental (já existente) por meio de mecanismos como a Experience Platform Edge Network (SDK da web, API do servidor) ou o conector de origem do Analytics (por exemplo, com o AppMeasurement).

A biblioteca do Content Analytics coleta dados quando:

* O Content Analytics é incluído na biblioteca de tags carregada na página.
* O URL da página é configurado na extensão do [Content Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que é parte da biblioteca de tags incluída.


## Evento do Content Analytics

Um evento do Content Analytics consiste em:

* Campos padrão
   * Carimbo de data e hora
   * Identidade
* Visualizações de experiência (se houver e se configuradas)
* Cliques de experiência (se houver e se configurados)
* Visualizações de ativos (se houver e se configuradas)
* Cliques no ativo (se houver e se configurados)

Os eventos do Content Analytics são coletados como uma sequência de:

1. [Uma visualização gravada ou clique](#recorded-view-or-click).
1. [Um acionador para enviar um evento do Content Analytics](#trigger-to-send-a-content-analytics-event).

A análise de conteúdo coleta dados dessa maneira para refletir essa sequência, em vez de coletar uma visualização ou cliques separadamente da coleta do evento imediatamente após essa visualização ou clique. Essa forma de coletar dados de Análise de Conteúdo também reduz a quantidade de dados coletados.

### Visualização gravada ou clique

Uma visualização de ativo é registrada quando:

* O ativo não foi excluído pela configuração da extensão do Content Analytics.
* O ativo está 75% visível.
* Esse ativo ainda não foi registrado para esta página.

Um clique de ativo é registrado quando:

* O ativo foi visualizado.
* O ativo não foi excluído pela configuração da extensão do Content Analytics.
* Um clique direto no ativo, que é um link, direciona para outra página.

Uma visualização de experiência é registrada quando:

* As experiências são habilitadas na configuração do Content Analytics.

Um clique de experiência é registrado quando:

* Qualquer clique ocorre em um link na página para a qual as experiências estão habilitadas.


### Acionar para enviar um evento do Content Analytics

Para reduzir o número de chamadas que saem da página, o Content Analytics coleta informações, mas não as envia imediatamente. As informações de interação de conteúdo são coletadas e um evento contendo essas informações só é enviado quando ocorre um dos seguintes acionadores:

* O SDK da Web ou o AppMeasurement envia um evento.
* A visibilidade muda para oculta, por exemplo, ao:
   * Descarregar a página
   * Alternar a guia
   * Minimizar o navegador
   * Fechar o navegador
   * Bloquear a tela
* O URL muda, o que resulta em um URL relevante modificado.
* As visualizações de ativos registradas e prontas para envio excedem o total de 32.

>[!NOTE]
>
>Os eventos adicionais do Content Analytics provavelmente afetarão qualquer definição de taxa de rejeição baseada no número de eventos em uma sessão ou página.
>


## Esquemas

Os dados do Content Analytics são coletados em conjuntos de dados na Experience Platform, com base em esquemas específicos do Content Analytics. Os esquemas de referência estão disponíveis publicamente:

* [Esquema de ativo digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiência digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de conteúdo do evento de experiência](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
