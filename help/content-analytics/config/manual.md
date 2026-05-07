---
title: Configuração manual do Content Analytics
description: Como configurar o Content Analytics manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a593221a9eb81d747777aedb323fd44a32c470be
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 64%

---

# Configuração manual do Content Analytics

Este artigo detalha as ações manuais necessárias para iniciar ou interromper a coleção de dados de uma configuração do Content Analytics ou para editar sua implementação do Content Analytics.

As opções de configuração disponíveis são as seguintes:

## Iniciar coleção de dados

Para iniciar a coleção de dados para uma configuração implementada do Content Analytics:

1. Siga o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"}. A biblioteca foi publicada com sucesso para as propriedades de Tags que contêm sua configuração do Content Analytics.

1. Com base nos canais configurados:

   * Para **web**: [Instalar](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/environments/environments#installation) o código incorporado no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou publicação, sujeito ao Content Analytics.
   * Para **dispositivos móveis**: consulte o [guia de extensão do Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) específico da solução na [documentação do Experience Platform Mobile SDK](https://developer.adobe.com/client-sdks/home/) sobre como configurar e instrumentar seu aplicativo móvel para Content Analytics.

## Parar coleção de dados

Para interromper a coleta de dados de uma configuração Content Analytics implementada, com base nos canais configurados:

* Para **web**:

   1. Remova o [código incorporado](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/environments/environments) no elemento `<head>` das páginas no seu ambiente de desenvolvimento, preparação ou produção, sujeito à Análise de conteúdo.
   1. Exclua a propriedade de Tags da Web associada à sua configuração do Content Analytics.

* Para **celular**:

   1. Remova a [extensão do Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) do seu aplicativo.
   1. Exclua a propriedade de Tags móveis associada à sua configuração do Content Analytics.

Siga o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"} para aplicar as alterações.


## Modificar coleção de dados

Você pode fazer algumas pequenas alterações em uma configuração implementada usando o [assistente de configuração guiada](guided.md). Por exemplo, altere a visualização de dados ou habilite/desabilite experiências.


### Web

Você usa a [extensão da Web do Adobe Content Analytics](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associada à sua configuração do Content Analytics para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifique se a sandbox e a sequência de dados configuradas na extensão do Adobe Content Analytics já estão configuradas para o Content Analytics usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Verifique também se as atualizações de sandbox ou sequências de dados não interferem em outra configuração do Content Analytics que esteja configurada para usar a mesma sandbox ou sequências de dados.
  >

* [Captura e definição de experiência](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Você pode habilitar ou desabilitar experiências e editar as combinações de expressões regulares e parâmetros de consulta para determinar como o conteúdo é renderizado no seu site.

* [Segmentação de eventos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  É possível editar expressões regulares para modificar a forma de segmentar páginas e ativos.


Depois de fazer alterações na extensão da Web do Adobe Content Analytics, use o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"} para começar a coletar dados.


### Dispositivo móvel

Você usa a [extensão para dispositivos móveis do Adobe Content Analytics](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) na propriedade Tags associada à sua configuração do Content Analytics para fazer alterações adicionais.

Depois de fazer alterações na extensão da Web do Adobe Content Analytics, use o [fluxo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview){target="_blank"} para começar a coletar dados.


## Controle de versão

>[!NOTE]
>
>Esta seção se aplica somente ao Content Analytics para o canal da Web.


Se quiser coletar experiências do Content Analytics, considere implementar o controle de versão para garantir que novas experiências (alterações na sua página da web) sejam coletadas corretamente.

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

>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>[Visão geral da publicação de tags de coleção de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview)
>
