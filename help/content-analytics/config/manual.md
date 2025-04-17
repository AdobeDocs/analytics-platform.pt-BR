---
title: Configuração manual do Content Analytics
description: Como configurar manualmente o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 981cd0c01d775acbd71cada7efed4911b4bcb157
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---

# Configuração manual do Content Analytics

{{release-limited-testing}}


Este artigo detalha as ações manuais necessárias para iniciar ou interromper a coleta de dados de uma configuração do Content Analytics ou editar a implementação do Content Analytics.

As seguintes ações de configuração manual estão disponíveis:

## Iniciar coleta de dados

Para iniciar a coleta de dados de uma configuração Content Analytics implementada:

1. Siga o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. A biblioteca da propriedade Tags, que contém a configuração do Content Analytics, foi publicada com sucesso.

1. [Instalar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) o código inserido no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou publicação, sujeito ao Content Analytics.


## Interromper coleta de dados

Para interromper a coleta de dados de uma configuração Content Analytics implementada:

1. Remova o [código inserido](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou produção, sujeito ao Content Analytics.
1. [Exclua](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) a propriedade de marcas associada da sua configuração do Content Analytics.



## Modificar coleção de dados

Você pode fazer pequenas alterações em uma configuração implementada usando o [assistente de configuração guiado](guided.md). Por exemplo, altere a visualização de dados ou ative ou desative as experiências.

Você usa a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associada à sua configuração do Content Analytics para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifique se a sandbox e a sequência de dados configuradas na extensão do Adobe Content Analytics já estão configuradas para o Content Analytics usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Verifique também se as atualizações da sandbox ou das sequências de dados não interferem com outra configuração do Content Analytics configurada para usar a mesma sandbox ou sequências de dados.
  >

* [Captura e definição de experiência](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  Você pode ativar ou desativar experiências e editar as combinações de expressão regular e parâmetros de consulta para determinar como o conteúdo é renderizado em seu site.

* [Filtragem de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  É possível editar expressões regulares para modificar a forma como você filtra páginas e ativos.


Depois de fazer alterações na extensão do Adobe Content Analytics, use o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para iniciar a coleta de dados com base nas alterações feitas.



>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>[Visão geral da publicação de Marcas de coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Controle de versão

Se quiser coletar experiências do Content Analytics, considere implementar o controle de versão para garantir que novas experiências (alterações na página da Web) sejam coletadas corretamente.

Para implementar o controle de versão, adicione uma função global `adobe.getContentExperienceVersion` nas páginas que você considera experiências que deseja analisar.

A função `adobe.getContentExperienceVersion` deve retornar uma cadeia de caracteres como valor, que pode ser qualquer item que você escolher, para identificar a versão. A versão está anexada à [URL da Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Se a função não estiver presente ou nenhum valor for retornado da função, o valor `NoVersion` será usado como padrão.

### Exemplo

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
