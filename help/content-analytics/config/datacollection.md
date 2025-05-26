---
title: Coleta de dados da análise de conteúdo
description: Uma visão geral de como os dados são coletados na análise de conteúdo
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
source-git-commit: c10d88c27d4a3c92e02179da4a73a6a499d2a8c2
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 77%

---

# Coleta de dados da análise de conteúdo

Este artigo explica em detalhes como a análise de conteúdo coleta dados

## Definições

As seguintes definições são usadas no contexto deste artigo:

* **Experiência**: uma experiência é definida como o conteúdo de texto em uma página da web inteira. Para a coleta de dados, a análise de conteúdo registra a ID da experiência, que é baseada no URL da página. Mais tarde, o texto na página é capturado por meio do serviço de recuperação.
* **ID de experiência**: uma combinação exclusiva do URL relevante (URL de base e quaisquer parâmetros que direcionam o conteúdo na página) e da [versão da experiência](manual.md#versioning).
   * Você especifica, como parte da [configuração](configuration.md), quais parâmetros são relevantes para qualquer URL completo.
   * Você define um [identificador de versão](manual.md#versioning) que será usado para coletar adequadamente as alterações em suas experiências.
* **Ativo**: uma imagem. A análise de conteúdo registra o URL do ativo.
* **ID do ativo**: o URL do ativo.
* **URL relevante**: o URL de base e quaisquer parâmetros que direcionem o conteúdo na página.


## Funcionalidade

O Content Analytics exige que o Experience Platform Edge Network Web SDK colete dados de conteúdo do evento. Essa coleta de dados de evento é combinada com a coleta de dados de evento comportamentais (existente) por meio de mecanismos como o Experience Platform Edge Network (Web SDK, API do servidor) ou o conector de origem do Analytics (por exemplo, usando o AppMeasurement).

A biblioteca da análise de conteúdo coleta dados quando:

* A análise de conteúdo é incluída na biblioteca de tags carregada na página.
* O URL da página é configurado na extensão de [análise de conteúdo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, que é parte da biblioteca de tags incluída.


## Evento de análise de conteúdo

Um evento de análise de conteúdo consiste em:

* Campos padrão
   * Carimbo de data e hora
   * Identidade
* Visualizações de experiência (se houver e se configuradas)
* Cliques de experiência (se houver e se configurados)
* Visualizações de ativos (se houver e se configuradas)
* Cliques no ativo (se houver e se configurados)

Os eventos da análise de conteúdo são coletados como uma sequência de:

1. [Uma visualização gravada ou clique](#recorded-view-or-click).
1. [Um gatilho para enviar um evento do Content Analytics](#trigger-to-send-a-content-analytics-event).

A análise de conteúdo coleta dados dessa maneira para refletir essa sequência, em vez de coletar uma visualização ou clique separadamente da coleta do evento imediatamente após essa visualização ou clique. Essa maneira de coletar dados de análise de conteúdo também reduz a quantidade de dados coletados.

### Visualização gravada ou clique

Uma visualização de ativo é registrada quando:

* O ativo não foi excluído pela configuração da extensão de análise de conteúdo.
* O ativo está 75% visível.
* Esse ativo ainda não foi registrado para esta página.

Um clique de ativo é registrado quando:

* O ativo foi visualizado.
* O ativo não foi excluído pela configuração da extensão de análise de conteúdo.
* Um clique direto no ativo, que é um link, direciona para outra página.

Uma visualização de experiência é registrada quando:

* As experiências são habilitadas na configuração da análise de conteúdo.

Um clique de experiência é registrado quando:

* Qualquer clique ocorre em um link na página para a qual as experiências estão habilitadas.


### Acionar para enviar um evento do Content Analytics

Para reduzir o número de chamadas que saem da página, o Content Analytics coleta informações, mas não as envia imediatamente. As informações de interação de conteúdo são coletadas e um evento contendo essas informações só é enviado quando um dos seguintes acionadores ocorre:

* O Web SDK ou o AppMeasurement envia um evento. O carimbo de data e hora deste evento é
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
>Os eventos adicionais do Content Analytics provavelmente afetam qualquer definição de taxa de rejeição baseada no número de eventos em uma sessão ou página.
>


## Esquemas

Os dados da análise de conteúdo são coletados em conjuntos de dados na Experience Platform, com base em esquemas específicos da análise de conteúdo. Os esquemas de referência estão disponíveis publicamente:

* [Esquema de ativo digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiência digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de conteúdo do evento de experiência](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
