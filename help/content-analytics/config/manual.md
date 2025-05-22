---
title: Configuração manual da Análise de conteúdo
description: Como configurar a Análise de conteúdo manualmente
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 96%

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
>[Visão geral da publicação de tags de coleção de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview)
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
