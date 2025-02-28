---
title: Configuração manual do Content Analytics
description: Como configurar manualmente o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

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

Para ativar uma nova configuração ou as alterações feitas em uma configuração existente, é necessário [publicar](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} a propriedade de Marca associada. Somente quando você publica a propriedade Tag do Content Analytics, os dados do Content Analytics são coletados para os domínios, a experiência e os ativos configurados.


## Desativar

Para desativar a coleta de dados de análise de conteúdo, [desfaça a publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} da propriedade de Marca associada para a sua configuração do Content Analytics.



## Modificar

Em geral, você deve usar o [assistente de configuração guiado](guided.md) para fazer alterações na implementação.

Como alternativa, você pode usar a extensão Adobe Content Analytics na propriedade Tag associada à configuração do Content Analytics para fazer alterações nos seguintes artefatos:

* [Sandbox e sequência de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}.

  >[!CAUTION]
  >
  >Você deve verificar se a sandbox e a sequência de dados configuradas na extensão Adobe Content Analytics já estão configuradas para o Content Analytics usando a [configuração guiada](guided.md) em um estágio anterior. Essa configuração garante que todos os artefatos necessários estejam disponíveis.<br/><br/>Você também deve verificar se as atualizações para sandbox ou fluxos de dados não interferem com outra configuração do Content Analytics configurada para usar a mesma sandbox ou fluxos de dados.
  >

* [Filtragem de eventos](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  É possível editar expressões regulares para modificar a forma como você filtra páginas e ativos.


Depois de fazer alterações na extensão do Adobe Content Analytics, certifique-se de [ativar](#activate) as alterações.



>[!MORELIKETHIS]
>
>[Configuração guiada](guided.md)
>[Visão geral da publicação de Marcas de coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>