---
title: Configuração manual da Análise de conteúdo
description: Como configurar a Análise de conteúdo manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 67%

---

# Configuração manual da Análise de conteúdo

Este artigo detalha as ações manuais necessárias para iniciar ou interromper a coleção de dados de uma configuração da Análise de conteúdo ou para editar sua implementação da Análise de conteúdo.

As opções de configuração disponíveis são as seguintes:

## Iniciar coleção de dados

Para iniciar a coleção de dados para uma configuração implementada da Análise de conteúdo:

1. Siga o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"}. Publique com sucesso a biblioteca da propriedade Tags que contém a configuração da Análise de conteúdo.

1. [Instale](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/environments/environments#installation) o código incorporado no elemento `<head>` das páginas no seu ambiente de desenvolvimento, preparação ou publicação, sujeito à Análise de conteúdo.


## Parar coleção de dados

Para parar a coleção de dados de uma configuração implementada da Análise de conteúdo:

1. Remova o [código incorporado](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/environments/environments) no elemento `<head>` das páginas no seu ambiente de desenvolvimento, preparação ou produção, sujeito à Análise de conteúdo.
1. [Exclua](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview) a propriedade Tags associada da configuração da Análise de conteúdo.



## Modificar coleção de dados

Você pode fazer algumas pequenas alterações em uma configuração implementada usando o [assistente de configuração guiada](guided.md). Por exemplo, altere a visualização de dados ou habilite/desabilite experiências.

Use a [extensão de Análise de conteúdo da Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associada à configuração da Análise de conteúdo para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifique se a sandbox e a sequência de dados configuradas na extensão de Análise de conteúdo da Adobe já estão configuradas para a Análise de conteúdo usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Verifique também se as atualizações de sandbox ou sequências de dados não interferem em outra configuração da Análise de conteúdo que esteja configurada para usar a mesma sandbox ou sequências de dados.
  >

* [Captura e definição de experiência](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Você pode habilitar ou desabilitar experiências e editar as combinações de expressões regulares e parâmetros de consulta para determinar como o conteúdo é renderizado no seu site.

* [Segmentação de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  É possível editar expressões regulares para modificar como segmentar páginas e ativos.


Depois de fazer alterações na extensão de Análise de conteúdo da Adobe, use o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"} para iniciar a coleção de dados com base nas alterações feitas.



>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>&#x200B;>[Visão geral da publicação de tags de coleção de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview)
>


## Controle de versão

Se quiser coletar experiências da Análise de conteúdo, considere implementar o controle de versão para garantir que novas experiências (alterações na sua página da web) sejam coletadas corretamente.

Para implementar o controle de versão, adicione uma função global `adobe.getContentExperienceVersion` nas páginas que você considera experiências que deseja analisar.

A função `adobe.getContentExperienceVersion` deve retornar uma string como valor, que pode ser qualquer item que você escolher, para identificar a versão. A versão está anexada ao [URL da Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Se a função não estiver presente ou nenhum valor for retornado pela função, o valor `NoVersion` será usado como padrão.

### Exemplo

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

## Identidades

O Content Analytics lida com identidades da seguinte maneira:

* A ECID é preenchida automaticamente na parte `identityMap` do esquema do Content Analytics.
* Se você precisar de outros valores de identidade no `identityMap`, será necessário definir esses valores no retorno de chamada `onBeforeEventSend` na extensão do Web SDK.
* A compilação em campo não é compatível porque o esquema é de propriedade do sistema. Portanto, não é possível adicionar outro campo ao esquema para oferecer suporte à compilação em campo


Para garantir que os dados de identidade da Content Analytics e do Adobe Experience Platform Web SDK sejam compilados corretamente no nível do campo, é necessário fazer modificações no Web SDK [em antes do retorno de chamada do evento &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} ser enviado.

1. Navegue até a propriedade **[!UICONTROL Tags]**, que contém a extensão do Adobe Experience Platform Web SDK e a extensão do Adobe Content Analytics.
1. Selecione ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensões]**.
1. Selecione a extensão **[!UICONTROL Adobe Experience Platform Web SDK]**.
1. Selecione **[!UICONTROL Configurar]**.
1. Na seção **[!UICONTROL Instâncias do SDK]**, role para baixo até **[!UICONTROL Coleta de dados]** - **[!UICONTROL Ativada antes do retorno de chamada do envio de evento]**.

   ![Ativado antes do retorno de chamada do envio do evento](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Selecione **[!UICONTROL &lt;/> Fornecer em antes do evento enviar o código de retorno de chamada]**.
1. Adicione o seguinte código:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![Ativado antes do retorno de chamada do envio do evento](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Selecione **[!UICONTROL Salvar]** para salvar o código.
1. Selecione **[!UICONTROL Salvar]** para salvar a extensão.
1. [Publique](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview) as atualizações para sua propriedade de marcas.





