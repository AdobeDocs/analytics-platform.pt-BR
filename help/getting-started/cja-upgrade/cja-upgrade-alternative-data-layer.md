---
title: Métodos alternativos ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre os métodos alternativos ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 3a0d03d1-def0-45e6-8eb2-115b88497e6d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 44%

---

# Alternativa de atualização: enviar a camada de dados para o Customer Journey Analytics {#data-collection-data-layer}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer"
>title="Enviar camada de dados para a Adobe"
>abstract="Em vez de enviar dados por meio de um objeto XDM, é possível enviar toda a camada de dados para a Adobe por meio do objeto de dados.<br><br>Essa opção economiza tempo de implementação, permitindo mapear a camada de dados para o XDM, em vez de preencher um objeto XDM do zero. No entanto, esse mapeamento é bastante trabalhoso devido à grande quantidade de dados que a Adobe não conseguirá interpretar prontamente. Essa opção também se torna mais complexa com o tempo, pois qualquer campo adicionado aos dados posteriormente deverá ser mapeado para o XDM no fluxo de dados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-send-data-layer"
>title="Enviar camada de dados para a Adobe"
>abstract="Configure a implementação para enviar dados para a Adobe no momento desejado e configure todo o conteúdo JSON como uma camada de dados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-layer-map"
>title="Atribuir cada elemento da camada de dados ao XDM"
>abstract="Mapeie cada elemento da camada de dados para o campo XDM desejado. Quaisquer elementos da camada de dados que não estão mapeados para um campo XDM são descartados permanentemente, já que a Adobe não sabe onde ou como armazenar esses dados."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Ao atualizar para o Customer Journey Analytics, o Adobe [recomenda uma nova implementação do Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). No entanto, dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização.

Você pode enviar toda a camada de dados para a Customer Journey Analytics em vez de coletar dados com o objeto XDM. No entanto, essa alternativa introduz uma complexidade adicional ao longo do tempo.

## Vantagens e desvantagens

Este método é mutuamente exclusivo com o [usando sua lógica de coleta de dados do AppMeasurement com o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), pois ambos os métodos realizam a mesma tarefa.

Veja a seguir as vantagens e desvantagens de usar essa alternativa de atualização:

| Vantagens | Desvantagens |
|----------|---------|
| <ul><li>**Mostra todas as vantagens de hospedar dados na Experience Edge Network**: <p>As vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados devido à capacidade da Adobe Experience Platform de potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/br/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Usa a lógica da camada de dados atual**: este método usa a lógica da camada de dados atual no lugar de uma implementação convencional do Web SDK. Embora essa abordagem exija alguma configuração, ela não requer uma implementação completamente nova do zero e não requer o preenchimento de elementos de dados ou regras de tag. Ela permite mapear dados da camada de dados para o XDM, em vez de preencher um objeto XDM do zero.</li></ul> | <ul><li>**Requer mapeamento para enviar dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, você deverá enviar dados para um conjunto de dados na Adobe Experience Platform. <p>Como essa opção permite que você coloque toda a camada de dados do lado do cliente no objeto de dados e envie-a para a Adobe, isso resulta em uma quantidade significativa de dados que a Adobe não consegue interpretar prontamente. Para permitir que o Adobe interprete os dados, você deve usar o mapeamento de fluxo de dados para mapear cada campo individual para o campo XDM desejado.</p></li><li>**Implementação rígida**: a implementação está restrita ao que a camada de dados fornece no momento em que a ocorrência é enviada. Isso pode ser aceitável para organizações com necessidades básicas de dados, mas a maioria das organizações deve evitar esse tipo de implementação rígida em favor de uma implementação mais flexível que permita o preenchimento de elementos de dados.</li><li>**As alterações futuras são mais difíceis de implementar**: qualquer campo adicionado aos dados posteriormente deve ser mapeado para o XDM na sequência de dados.</li></ul> |

{style="table-layout:auto"}

## Etapas básicas

As etapas básicas para enviar toda a camada de dados para o Customer Journey Analytics são:

1. Configure a implementação para enviar dados para a Adobe no momento desejado e configure todo o conteúdo JSON como uma camada de dados.

1. Mapeie cada elemento da camada de dados para o campo XDM desejado.

   Quaisquer elementos da camada de dados que não estão mapeados para um campo XDM são descartados permanentemente, já que a Adobe não sabe onde ou como armazenar esses dados.
