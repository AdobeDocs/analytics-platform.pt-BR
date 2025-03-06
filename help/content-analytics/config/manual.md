---
title: Configuração manual do Content Analytics
description: Como configurar manualmente o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

---

# Configuração manual do Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{{release-limited-testing}}

Este artigo detalha as ações manuais necessárias para ativar ou desativar uma configuração do Content Analytics ou editar sua implementação do Content Analytics.

As seguintes ações de configuração manual estão disponíveis:

## Ativar

Para ativar uma nova configuração ou alterações feitas em uma configuração existente:

1. Você precisa seguir o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Somente depois de publicar com êxito a biblioteca da propriedade Tag que contém a configuração do Content Analytics, os dados do Content Analytics são coletados para os domínios, experiências e ativos configurados.

1. Você precisa [instalar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) o código de inserção no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou publicação, sujeito à Análise de Conteúdo.


## Desativar

Para desativar a coleta de dados de análise de conteúdo:

1. Remova o [código incorporado](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) no elemento `<head>` das páginas em seu ambiente de desenvolvimento, preparo ou produção, sujeito à Análise de Conteúdo.
1. [Exclua](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) a propriedade de Marca associada para a configuração do Content Analytics.



## Modificar

Em geral, você deve usar o [assistente de configuração guiado](guided.md) para fazer alterações na implementação.

Como alternativa, você pode usar a [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade Tag associada à sua configuração do Content Analytics para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Você deve verificar se a sandbox e a sequência de dados configuradas na extensão Adobe Content Analytics já estão configuradas para o Content Analytics usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Você também deve verificar se as atualizações para sandbox ou fluxos de dados não interferem com outra configuração do Content Analytics configurada para usar a mesma sandbox ou fluxos de dados.
  >

* [Filtragem de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  É possível editar expressões regulares para modificar a forma como você filtra páginas e ativos.


Depois de fazer alterações na extensão do Adobe Content Analytics, use o [fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} para ativar as alterações.



>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>[Visão geral da publicação de Marcas de coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Controle de versão

Se você exigir o controle de versão das suas experiências de Análise de conteúdo, será necessário adicionar uma função global `adobe.getContentExperienceVersion` nas páginas em que você considera as experiências que deseja analisar.

A função `adobe.getContentExperienceVersion` deve retornar uma cadeia de caracteres como valor, que pode ser qualquer item que você escolher para identificar a versão. A versão é anexada ao URL da Experience ID.

Se a função não estiver presente ou nenhum valor for retornado da função, o valor `NoVersion` será usado como padrão.

### Exemplo

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
