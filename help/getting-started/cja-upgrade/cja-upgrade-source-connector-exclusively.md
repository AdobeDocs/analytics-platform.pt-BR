---
title: Use o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics
description: Saiba como criar o conector de origem do Analytics e mapear campos
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 07570641949e17d30b7f9f5b38eb95c29c5176c0
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 27%

---

# Use o conector de origem do Analytics exclusivamente para atualizar para o Customer Journey Analytics

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização de Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Embora não seja recomendado, você pode usar o conector de origem do Analytics como o único caminho de implementação para o Customer Journey Analytics. No entanto, devido às desvantagens inerentes associadas a esse tipo de atualização, a Adobe recomenda usar o conector de origem do Analytics junto com uma nova implementação do SDK da Web do Experience Platform. Para obter mais informações sobre esse caminho de atualização recomendado, consulte [Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

Use as seguintes informações para entender as vantagens e desvantagens de usar exclusivamente o conector de origem:

| Vantagens | Desvantagens |
|----------|---------|
| <ul><li>O caminho de atualização menos demorado e exigente. <p>Os dados são migrados para o Customer Journey Analytics de forma rápida e fácil.</p></li></ul> | <ul><li>**Os dados não são enviados para a Edge Network**: <p>Isso resulta nas seguintes desvantagens:</p><ul><li>Nível mais alto de [latência](/help/technotes/guardrails.md#latencies) em relatórios em todos os caminhos de atualização; não otimizado para casos de uso de personalização em tempo real.</li><li>Os dados não podem ser compartilhados com outros aplicativos da Adobe Experience Platform e estão restritos somente ao Customer Journey Analytics</li><li>Dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Difícil de migrar para o SDK da Web no futuro**: no final, você provavelmente desejará acessar as vantagens fornecidas pelo SDK da Web do Experience Platform. Para começar a usar o SDK da Web do Experience Platform, você deve fazer uma nova implementação.</li><li>**Usa o grupo de campos de evento de experiência do Analytics no esquema**: esse grupo de campos adiciona muitos eventos do Adobe Analytics que não são necessários no esquema do Customer Journey Analytics.  Isso pode levar a um esquema mais desorganizado e complexo do que o necessário para o Customer Journey Analytics.</li><li>**Requer licenças para Adobe Analytics e Customer Journey Analytics**: usar o conector de origem do Analytics requer que você pague para Adobe Analytics e Customer Journey Analytics.</li></ul> |

{style="table-layout:auto"}

