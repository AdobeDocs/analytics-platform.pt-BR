---
title: Use o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics
description: Saiba como criar o conector de origem do Analytics e mapear campos
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 41%

---

# Alternativa de atualização: use o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Use somente o conector de origem do Analytics"
>abstract="(Não recomendado) É possível usar o conector de origem do Analytics como o único caminho de implementação para o Customer Journey Analytics. <br><br>Essa opção economiza tempo de implementação enviando dados rapidamente para o Customer Journey Analytics. No entanto, ela inclui várias desvantagens, como maior latência e dificuldade para sair do Adobe Analytics no futuro."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Embora não seja recomendado, você pode usar o conector de origem do Analytics como o único caminho de implementação para o Customer Journey Analytics. No entanto, devido às desvantagens inerentes associadas a esse tipo de atualização, a Adobe recomenda usar o conector de origem do Analytics junto com uma nova implementação do Experience Platform Web SDK. Para obter mais informações sobre esse caminho de atualização recomendado, consulte [Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

## Vantagens e desvantagens

Use as informações na tabela abaixo para entender as vantagens e desvantagens de usar o conector de origem exclusivamente ao atualizar para o Customer Journey Analytics.

| Vantagens | Desvantagens |
|----------|---------|
| <ul><li>O caminho de atualização menos demorado e exigente. <p>Os dados são migrados para o Customer Journey Analytics de forma rápida e fácil.</p></li></ul> | <ul><li>**Os dados não são enviados para a Edge Network**: <p>Isso resulta nas seguintes desvantagens:</p><ul><li>Nível mais alto de [latência](/help/technotes/guardrails.md#latencies) em relatórios em todos os caminhos de atualização; não otimizado para casos de uso de personalização em tempo real.</li><li>Os dados não podem ser compartilhados com outros aplicativos da Adobe Experience Platform e estão restritos somente ao Customer Journey Analytics</li><li>Dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Difícil de migrar para o Web SDK no futuro**: você provavelmente desejará acessar as vantagens fornecidas pelo Experience Platform Web SDK. Para começar a usar o Experience Platform Web SDK, é necessário fazer uma nova implementação.</li><li>**Usa o grupo de campos de evento de experiência do Analytics no esquema**: esse grupo de campos adiciona muitos eventos do Adobe Analytics que não são necessários no esquema do Customer Journey Analytics.  Isso pode levar a um esquema mais desorganizado e complexo do que o necessário para o Customer Journey Analytics.</li><li>**Requer licenças para Adobe Analytics e Customer Journey Analytics**: usar o conector de origem do Analytics requer que você pague para Adobe Analytics e Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

## Etapas básicas

Se você decidir usar o conector de origem do Analytics como o único caminho de implementação para o Customer Journey Analytics, siga as etapas de implementação descritas em [Assimilar e use dados usando conectores de origem](/help/data-ingestion/sources.md).

