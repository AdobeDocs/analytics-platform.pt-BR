---
title: Configuração manual do Content Analytics
description: Como configurar manualmente o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 01459765d84a46d170c1619ffeae184957bbf839
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 1%

---

# Configuração manual do Content Analytics

{{draft-aca}}

{{release-limited-testing}}

Este artigo detalha as ações manuais necessárias para ativar ou desativar uma configuração do Content Analytics ou editar sua implementação do Content Analytics.

As seguintes ações de configuração manual estão disponíveis:

## Ativar

Para ativar uma nova configuração ou alterações feitas em uma configuração existente:

1. Você precisa seguir o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. A biblioteca da propriedade Tags, que contém a configuração do Content Analytics, foi publicada com sucesso.

1. Você precisa [instalar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) o código incorporado no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou publicação, sujeito ao Content Analytics.


## Desativar

Para desativar a coleta de dados de análise de conteúdo:

1. Remova o [código inserido](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou produção, sujeito ao Content Analytics.
1. [Exclua](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) a propriedade de marcas associada da sua configuração do Content Analytics.



## Modificar

Você pode fazer pequenas alterações em uma configuração implementada usando o [assistente de configuração guiado](guided.md). Por exemplo, altere a visualização de dados.

Você usa a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tags associada à sua configuração do Content Analytics para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Verifique se a sandbox e a sequência de dados configuradas na extensão do Adobe Content Analytics já estão configuradas para o Content Analytics usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Verifique também se as atualizações da sandbox ou das sequências de dados não interferem com outra configuração do Content Analytics configurada para usar a mesma sandbox ou sequências de dados.
  >

* [Captura e definição de experiência](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  É possível editar a expressão regular para modificar a maneira como você .

* [Filtragem de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  É possível editar expressões regulares para modificar a forma como você filtra páginas e ativos.


Depois de fazer alterações na extensão do Adobe Content Analytics, use o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para ativar as alterações.



>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>[Visão geral da publicação de Marcas de coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Controle de versão

Se você precisar de controle de versão das suas experiências do Content Analytics, adicione uma função global `adobe.getContentExperienceVersion` nas páginas que você considera experiências que deseja analisar.

A função `adobe.getContentExperienceVersion` deve retornar uma cadeia de caracteres como valor, que pode ser qualquer item que você escolher, para identificar a versão. A versão está anexada à [URL da Experience ID](/help/content-analytics/report/components.md#experience-metadata).

Se a função não estiver presente ou nenhum valor for retornado da função, o valor `NoVersion` será usado como padrão.

### Exemplo

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
