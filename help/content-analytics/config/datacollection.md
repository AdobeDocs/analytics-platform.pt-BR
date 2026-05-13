---
title: Coleta de dados do Content Analytics
description: Saiba como os dados são coletados no Content Analytics.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 584587e6-45fd-4fc3-a7a6-6685481ddee7
TQID: https://experienceleague.adobe.com/B2j6BrXAHMu-3LKI61LbK01i-UdpMlELsqYSfAWYDCo
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 1093
ht-degree: 52%

---


# Coleta de dados do Content Analytics

Este artigo explica em detalhes como o Content Analytics coleta dados

## Definições

As seguintes definições são usadas no contexto deste artigo:

* **Experiência**:
   * Para o canal **web**, uma experiência é definida como o conteúdo de texto em uma página da Web inteira. Para a coleta de dados, o Content Analytics registra a Experience ID, que se baseia no URL da página. Mais tarde, o texto na página é capturado por meio do serviço de recuperação.
   * Para o canal **mobile**, uma experiência é definida e rastreada no aplicativo móvel usando a extensão Content Analytics para o Adobe Experience Platform Mobile SDK.
* **Experience ID**:
   * Para o canal Web, a ID da experiência é uma combinação exclusiva de URL relevante (URL base mais quaisquer parâmetros que direcionam o conteúdo na página) e [versão da experiência](manual.md#versioning).
      * Você especifica, como parte da [configuração](configuration.md), quais parâmetros são relevantes para qualquer URL completo.
      * Você define um [identificador de versão](manual.md#versioning) que será usado para coletar adequadamente as alterações em suas experiências.
   * Para o canal **mobile**, a ID da experiência é o valor de retorno do uso da chamada de API `registerExperience`.
* **Ativo**: uma imagem. O Content Analytics registra o URL do ativo.
* **ID do ativo**: o URL do ativo.
* **URL relevante**: o URL de base e quaisquer parâmetros que direcionem o conteúdo na página.


## Funcionalidade

O Content Analytics exige o Experience Platform Edge Network Web SDK (para o canal da Web) e o Experience Platform Edge Network Mobile SDK (para o canal móvel) para coletar dados do evento de conteúdo. Esses dados de evento são combinados com dados comportamentais existentes usando o Experience Platform Edge Network (Web SDK, Mobile SDK ou Server API) ou um conector de origem do Analytics, como o Adobe AppMeasurement.

A biblioteca do Content Analytics coleta dados quando:

* O Content Analytics está incluído na biblioteca de tags carregada na página ou usada no aplicativo móvel.
* A URL da página e a URL do ativo estão configuradas na [extensão da Web do Content Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview){target="_blank"}, parte da biblioteca de marcas incluída.
* A URL do ativo, a localização do ativo ou a localização da experiência não são excluídas na [extensão móvel do Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/).


## Evento do Content Analytics

Esta seção detalha as especificidades dos eventos do Content Analytics na Web. Consulte [Rastreamento de experiência](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/experience-tracking/) para obter detalhes sobre eventos do Content Analytics para dispositivos móveis.
Um evento do Content Analytics consiste em:

* Campos padrão
   * Carimbo de data e hora
   * Identidade
* Visualizações de experiência (se houver e se configuradas)
* Cliques de experiência (se houver e se configurados)
* Visualizações de ativos (se houver e se configuradas)
* Cliques no ativo (se houver e se configurados)

Os eventos do Content Analytics são coletados como uma sequência de:

1. Um [modo de exibição gravado ou clique](#recorded-view-or-click).
1. Um [acionador para enviar um evento Content Analytics](#trigger-to-send-a-content-analytics-event).

A análise de conteúdo coleta dados dessa maneira para refletir essa sequência, em vez de coletar uma visualização ou cliques separadamente da coleta do evento imediatamente após essa visualização ou clique. Essa forma de coletar dados de Análise de Conteúdo também reduz a quantidade de dados coletados.

### Visualização gravada ou clique

Uma visualização de ativo é registrada quando:

* O ativo não foi excluído pela configuração da extensão do Content Analytics.
* O ativo está 75% visível.
* Esse ativo ainda não foi registrado para esta página.

Um clique de ativo é registrado quando:

* O ativo foi visualizado.
* O ativo não foi excluído pela configuração da extensão do Content Analytics.
* Um clique diretamente no ativo, que é um link, abre outra página.

Uma visualização de experiência é registrada quando:

* As experiências são habilitadas na configuração do Content Analytics.

Um clique de experiência é registrado quando:

* Qualquer clique em um link ativado aciona uma experiência.


### Acionar para enviar um evento do Content Analytics

Para reduzir o número de solicitações de rede enviadas da página, a Content Analytics coleta informações, mas não as envia imediatamente. As informações de interação de conteúdo são coletadas e um evento contendo essas informações só é enviado quando ocorre um dos seguintes acionadores:

* O Web SDK ou o Adobe AppMeasurement enviam um evento.
* A visibilidade muda para oculta, por exemplo, ao:
   * Descarregar a página
   * Alternar a guia
   * Minimizar o navegador
   * Fechar o navegador
   * Bloquear a tela
* O URL muda, o que resulta em um URL relevante modificado.
* As exibições de ativos registradas e prontas para serem enviadas excedem 32.

>[!NOTE]
>
>Os eventos adicionais do Content Analytics provavelmente afetarão qualquer definição de taxa de rejeição baseada no número de eventos em uma sessão ou página.
>

## Identidades

Esta seção explica como o Content Analytics lida com identidades.

### Web

O Content Analytics trata as identidades do canal da Web da seguinte maneira:

* A ECID é preenchida automaticamente na parte `identityMap` do esquema do Content Analytics.
* Se precisar de outros valores de identidade no `identityMap`, será necessário definir esses valores no retorno de chamada `onBeforeEventSend` da extensão do SDK da web.
* A compilação baseada em campo não é compatível porque o esquema é de propriedade do sistema. Portanto, não é possível adicionar outro campo ao esquema para oferecer suporte à compilação baseada em campo


Para garantir que os dados de identidade da Content Analytics e os dados de identidade da Web SDK sejam compilados corretamente no nível do campo, modifique o Web SDK [em antes de enviar o retorno de chamada](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/onbeforeeventsend){target="_blank"} do evento.

1. Navegue até a propriedade **[!UICONTROL Tags]**, que contém as extensões do SDK da web da Adobe Experience Platform e do Adobe Content Analytics.
1. Selecione **[!UICONTROL Extensões]** de ![Plug](/help/assets/icons/Plug.svg).
1. Selecione a extensão **[!UICONTROL SDK da web da Adobe Experience Platform]**.
1. Selecione **[!UICONTROL Configurar]**.
1. Na seção **[!UICONTROL Instâncias do SDK]**, role para baixo até **[!UICONTROL Coleta de dados]** — **[!UICONTROL Retorno de chamada “Antes do evento de envio”]**.

   ![Retorno de chamada “antes do evento de envio”](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Selecione **[!UICONTROL &lt;/> Fornecer o código do retorno de chamada &quot;antes do evento de envio&quot;]**.
1. Adicione o seguinte código:

   ```JavaScript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Retorno de chamada antes do evento de envio](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Selecione **[!UICONTROL Salvar]** para salvar o código.
1. Selecione **[!UICONTROL Salvar]** para salvar a extensão.
1. [Publique](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview) as atualizações para a propriedade de tags.


### Dispositivo móvel

Consulte a [Identidade da extensão do Serviço da Experience Cloud ID](https://developer.adobe.com/client-sdks/home/base/mobile-core/identity/) e a [Identidade da extensão móvel do Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) para obter mais informações sobre como trabalhar com identidades no aplicativo móvel.

Assim que a identidade for alterada no aplicativo móvel, o [lote](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/#batching-settings) atual de dados do Content Analytics será redefinido para iniciar uma nova coleção de dados do Content Analytics para a nova identidade.

## Esquemas

A Experience Platform coleta dados do Content Analytics em conjuntos de dados com base em esquemas específicos do Content Analytics. Os esquemas de referência estão disponíveis publicamente:

* [Esquema de ativo digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-asset.schema.json)
* [Esquema de experiência digital](https://github.com/adobe/xdm/blob/master/components/classes/digital-experience.schema.json)
* [Esquema de conteúdo do evento de experiência](https://github.com/adobe/xdm/blob/master/components/fieldgroups/experience-event/experienceevent-content.schema.json)
