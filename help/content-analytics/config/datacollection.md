---
title: Coleção de dados do Content Analytics
description: Uma visão geral de como os dados são coletados no Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
hide: true
hidefromtoc: true
role: Admin
source-git-commit: d835411beba3d40f67d2f93ee76aa5eda6f45041
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---


# Coleção de dados do Content Analytics

Este artigo explica em detalhes como o Analytics de conteúdo coleta dados


## Definições

As seguintes definições são usadas no contexto deste artigo:

* **Experiência**: uma experiência é definida como o conteúdo de texto em uma página da Web inteira. Para a coleta de dados, o Content Analytics registra a Experience ID. O Content Analytics não registra o texto na página.
* **Ativo**: uma imagem. O Content Analytics registra o URL do ativo.
* **URL relevante**: a URL base mais quaisquer parâmetros que direcionem o conteúdo na página.
* **Experience ID**: uma combinação exclusiva de URL relevante e versão de experiência.
   * Você especifica, como parte da [configuração](configuration.md), quais parâmetros são relevantes para qualquer URL completa.
   * Você pode definir o [identificador de versão](manual.md#versioning) que é usado. Para a coleta de dados, a versão não é considerada. Somente o url relevante é coletado.

## Funcionalidade

A biblioteca do Content Analytics coleta dados quando:

* O Content Analytics está incluído na biblioteca de tags carregada na página.
* A URL da página está configurada na [extensão do Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte da biblioteca de marcas incluída.


### Evento do Content Analytics

Um evento do Content Analytics consiste em:

* Campos padrão
   * Carimbo de data e hora
   * Identidade
* Visualizações de experiência (se houver e se configurado)
* Cliques de experiência (se houver e se estiver configurado)
* Exibições de ativos (se houver e se configurado)
* Cliques no ativo (se houver e se estiver configurado)

#### Exibições ou cliques registrados

Uma exibição de ativo é registrada quando:

* O ativo não foi excluído de acordo com a configuração de extensão do ACA.
* O ativo é de 75% na visualização.
* Esse ativo ainda não foi registrado para esta página.

Um clique de ativo é registrado quando:

* O ativo foi visualizado.
* O ativo não foi excluído de acordo com a configuração de extensão do ACA.
* Um clique diretamente no ativo, que é um link, que leva a outra página.

Uma visualização de experiência é registrada quando:

* As experiências são ativadas na configuração do Content Analytics.

Um clique de experiência é registrado quando:

* Qualquer clique ocorre em um link na página para a qual as experiências estão habilitadas.


#### Eventos enviados

Os eventos Content Analytics são enviados quando as duas condições a seguir ocorrem:

* O conteúdo é enviado, o que ocorre quando:

   * Uma exibição ou um clique de ativo é registrado.
   * Uma visualização de experiência ou clique é gravado.

* Um acionador para enviar um evento é acionado, o que ocorre quando:

   * O Web SDK ou o AppMeasurement envia um evento.
   * A visibilidade muda para oculta, por exemplo:
      * Descarregamentos de página
      * Alternar guia
      * Minimizar navegador
      * Fechar navegador
      * Tela de bloqueio
   * O URL muda, o que resulta em um URL relevante modificado.
   * Uma exibição de ativo excede o limite de lote de 32.


## Esquemas

Os dados do Content Analytics são coletados em conjuntos de dados no Experience Platform, com base em esquemas específicos do Content Analytics. Os esquemas de referência estão disponíveis publicamente e são usados em uma implementação padrão do Content Analytics.

* [Esquema de ativo digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiência digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema do conteúdo do evento de experiência](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
