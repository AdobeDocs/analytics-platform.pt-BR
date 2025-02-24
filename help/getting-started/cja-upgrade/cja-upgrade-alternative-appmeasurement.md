---
title: Métodos alternativos ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre os métodos alternativos ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 2b66e2db9b22bab5304fe981e58828d4ae9fabbd
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 19%

---

# Alternativa de atualização: use a coleta de dados do AppMeasurement com o Experience Platform Web SDK e o Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Usar a lógica do AppMeasurement com o Web SDK"
>abstract="Em vez de enviar dados por meio de um objeto XDM, envie todas as variáveis no formato AppMeasurement por meio do objeto de dados.<br><br>Essa opção economiza tempo de implementação, permitindo mapear a lógica do AppMeasurement para o XDM, em vez de preencher um objeto XDM do zero. No entanto, apresenta complexidade adicional com o tempo, pois qualquer campo adicionado no futuro deve ser mapeado para XDM no fluxo de dados."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use as informações desta página ao responder perguntas da [lista de verificação de atualização do Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Ao atualizar para o Customer Journey Analytics, o Adobe [recomenda uma nova implementação do Experience Platform Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). No entanto, dependendo de vários fatores, como linha do tempo e restrições de recursos, as etapas de atualização recomendadas podem não ser práticas para sua organização.

Você pode usar sua lógica de coleta de dados de extensão do AppMeasurement ou Analytics com o Web SDK para enviar dados para a Platform e o Customer Journey Analytics, em vez de coletar dados com o objeto XDM. No entanto, essa alternativa introduz uma complexidade adicional ao longo do tempo.

## Vantagens e desvantagens

Este método é mutuamente exclusivo com [o envio de toda a camada de dados para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), pois ambos os métodos realizam a mesma tarefa. (Esse método é preferível ao envio de toda a camada de dados para a Adobe. Ele é mais refinado porque props e evars passam pelos dados.__adobe.analytics._nome-variável_.)

Considere as seguintes vantagens e desvantagens de usar essa alternativa de atualização:

| Vantagens | Desvantagens |
|----------|---------|
| <ul><li>**Mostra todas as vantagens de hospedar dados na Experience Edge Network**: <p>As vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados devido à capacidade da Adobe Experience Platform de potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/br/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não limitado à nomenclatura do Adobe Analytics (prop, eVar, evento e assim por diante)</li></ul><li>**Uso da implementação existente**: embora sejam necessárias algumas alterações de implementação, essa abordagem não exige uma implementação totalmente nova. Ela permite mapear a lógica do AppMeasurement para o XDM, em vez de preencher um objeto XDM do zero.</li></ul> | <ul><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que cada campo no objeto de dados seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li><li>**Apresenta complexidade adicional ao longo do tempo**: qualquer campo adicionado no futuro deve ser mapeado para XDM na sequência de dados.<p>Sempre que um novo campo for adicionado à implementação, você poderá executar um dos seguintes procedimentos:</p><ul><li>**Opção 1:** Preencha uma nova evar arbitrária ou uma nova prop no objeto de dados e mapeie-a para o campo XDM desejado.<p>Esse processo aumenta a consistência para a implementação no lado do cliente, mas requer mapeamento.</p></li><li>**Opção 2:** Deixe o objeto de dados como uma implementação herdada e comece a preencher somente o objeto XDM para todos os novos campos.<p>Esse processo não requer mapeamento, mas significa que algumas de suas variáveis estão localizadas apenas em um objeto de dados, enquanto outras variáveis estão localizadas apenas em um objeto XDM. Sempre que precisar solucionar problemas de implementação, você precisará ir para dois lugares. Verifique se os workflows internos acomodam isso.</p></li></ul> </li></ul> |

{style="table-layout:auto"}

## Etapas básicas

As etapas básicas para migrar uma implementação do Adobe Analytics (AppMeasurement ou a extensão do Analytics) para usar o Web SDK para enviar dados para o Customer Journey Analytics são:

1. (Opcional) Migre sua implementação do Adobe Analytics para usar o Adobe Experience Platform Web SDK e comece a enviar dados para o Edge Network.

   Esta é uma etapa opcional que permite migrar sua implementação existente do Adobe Analytics para usar o Web SDK e validar se tudo está funcionando no Adobe Analytics. Depois que isso for configurado e os dados no Adobe Analytics forem satisfatórios, você poderá enviar dados do Edge Network para o Customer Journey Analytics.

   Essa flexibilidade permite uma atualização mais metódica e ponderada para o Customer Journey Analytics.

   Para obter informações sobre como fazer isso, consulte os seguintes artigos na documentação do Adobe Analytics:

   * [Migrar para o Web SDK usando marcas](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrar para o Web SDK usando o JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Enviar dados do Edge Network para o Customer Journey Analytics.

   1. Envie todas as variáveis no formato AppMeasurement por meio do objeto de dados.

      Para obter mais informações, consulte [Mapeamento de variável de objeto de dados para Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Caso ainda não o tenha feito, crie um esquema XDM para sua organização.

      Para obter mais informações, consulte [Criar um esquema personalizado para usar com a implementação do Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   1. Use o mapeamento do fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.

      Para obter mais informações, consulte [Mapeamento](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) em [Preparação de dados para coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) na documentação do Experience Platform.

