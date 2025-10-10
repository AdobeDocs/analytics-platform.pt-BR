---
title: Métodos alternativos ao atualizar para o Customer Journey Analytics
description: Saiba mais sobre os métodos alternativos ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 0bf35c67-c8ae-4349-93fb-b9806c1064a8
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 58%

---

# Alternativa de atualização: use a coleção de dados do AppMeasurement com o SDK da web da Experience Platform e o Customer Journey Analytics {#data-collection-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic"
>title="Usar a lógica do AppMeasurement com o SDK da web"
>abstract="Em vez de enviar dados por meio de um objeto XDM, é possível enviar todas as variáveis no formato do AppMeasurement por meio do objeto de dados. <br><br>Essa opção economiza tempo de implementação, permitindo mapear a lógica do AppMeasurement para o XDM, em vez de preencher um objeto XDM do zero. No entanto, ela se torna mais complexa com o tempo, pois qualquer campo adicionado no futuro deve ser mapeado para o XDM na sequência de dados."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-appmeasurement-logic-step"
>title="Altere a lógica do AppMeasurement para apontar para o SDK da web"
>abstract="esta etapa é exibida porque você optou por um atalho de implementação. Copie ou altere a lógica do AppMeasurement para preencher o objeto de dados, em vez do objeto s. Por exemplo, altere a atribuição de s.eVar1 para data.__adobe.analytics.eVar1 e repita para todas as variáveis do Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Ao atualizar para o Customer Journey Analytics, a Adobe [recomenda uma nova implementação do SDK da web da Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). No entanto, dependendo de vários fatores, como restrições de linha do tempo e de recursos, as etapas de atualização recomendadas podem não ser práticas para a organização.

Você pode usar sua lógica de coleta de dados de extensão do AppMeasurement ou Analytics com o Web SDK para enviar dados para a Platform e o Customer Journey Analytics, em vez de coletar dados com o objeto XDM. No entanto, essa alternativa introduz uma complexidade adicional ao longo do tempo.

## Vantagens e desvantagens

Este método é mutuamente exclusivo com [o envio de toda a camada de dados para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-appmeasurement.md), pois ambos os métodos realizam a mesma tarefa. (Esse método é preferível ao envio de toda a camada de dados para a Adobe. Ele é mais refinado porque props e evars passam pelos dados.__adobe.analytics._nome-variável_.)

Considere as seguintes vantagens e desvantagens de usar essa alternativa de atualização:

| Vantagens | Desvantagens |
|----------|---------|
| Esse é o caminho de atualização recomendado se a implementação do Adobe Analytics já estiver usando o SDK da web.<ul><li>**Mostra todas as vantagens de hospedar dados na Experience Edge Network**: <p>As vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados devido à capacidade da Adobe Experience Platform de potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=pt-BR)</li><li>Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Uso da implementação existente**: embora sejam necessárias algumas alterações de implementação, essa abordagem não exige uma implementação totalmente nova. Você pode usar sua camada de dados e código existentes com alterações mínimas na lógica de implementação sem afetar os relatórios existentes do Adobe Analytics.</li><li>**Fornece uma opção para usar um esquema XDM**: é possível optar por usar seu esquema do Adobe Analytics existente ou criar um esquema XDM e mapear campos no objeto de dados desse esquema. [Esquemas XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home#xdm-schemas) são flexíveis e permitem definir quaisquer campos necessários e relevantes. <p>Consulte “Usar seu próprio esquema XDM” abaixo para obter mais informações sobre as vantagens de usar seu próprio esquema XDM.</p></li><li>**Mantém regras e elementos de dados**: embora sejam necessárias novas ações de regra, é possível reutilizar elementos de dados e condições de regra existentes com alterações mínimas.</li><li>**À prova de obsolescência**: se você optar por usar seu próprio esquema XDM, isso facilitará as atualizações de implementação futuras.</li></ul> | <ul><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que cada campo no objeto de dados seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li><li>**Apresenta complexidade adicional ao longo do tempo**: qualquer campo adicionado no futuro deve ser mapeado para XDM na sequência de dados.<p>Sempre que um novo campo for adicionado à implementação, você poderá executar um dos seguintes procedimentos:</p><ul><li>**Opção 1:** Preencha uma nova evar arbitrária ou uma nova prop no objeto de dados e mapeie-a para o campo XDM desejado.<p>Esse processo aumenta a consistência para a implementação no lado do cliente, mas requer mapeamento.</p></li><li>**Opção 2:** Deixe o objeto de dados como uma implementação herdada e comece a preencher somente o objeto XDM para todos os novos campos.<p>Esse processo não requer mapeamento, mas significa que algumas de suas variáveis estão localizadas apenas em um objeto de dados, enquanto outras variáveis estão localizadas apenas em um objeto XDM. Sempre que precisar solucionar problemas de implementação, você precisará ir para dois lugares. Verifique se os workflows internos acomodam isso.</p></li></ul> |

{style="table-layout:auto"}

## Etapas básicas

As etapas básicas para migrar uma implementação do Adobe Analytics (AppMeasurement ou a extensão do Analytics) para usar o Web SDK para enviar dados para o Customer Journey Analytics são:

1. Migre sua implementação do Adobe Analytics para usar o Adobe Experience Platform Web SDK e comece a enviar dados para o Edge Network.

   Esta etapa permite migrar a implementação existente do Adobe Analytics para usar o Web SDK. Opcionalmente, é possível enviar dados para o Adobe Analytics para validar se tudo está funcionando no Adobe Analytics antes de enviar os dados para o Customer Journey Analytics. Depois que isso for configurado e os dados no Adobe Analytics forem satisfatórios, você poderá enviar dados do Edge Network para o Customer Journey Analytics.

   Essa flexibilidade permite uma atualização mais metódica e ponderada do Customer Journey Analytics.

   Para obter informações sobre como fazer isso, consulte os seguintes artigos na documentação do Adobe Analytics:

   * [Migrar para o Web SDK usando marcas](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)

   * [Migrar para o Web SDK usando o JavaScript](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)

1. Comece a enviar dados do Edge Network para a Platform.

   1. Envie todas as variáveis no formato AppMeasurement por meio do objeto de dados.

      Para obter mais informações, consulte [Mapeamento de variável de objeto de dados para Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

   1. Escolha seu esquema.

      Você pode escolher se deseja usar seu esquema existente do Adobe Analytics ou criar um esquema XDM para se alinhar melhor às necessidades da organização à medida que começa a usar outros serviços da plataforma.

      A Adobe recomenda criar um esquema XDM. Para obter mais informações, consulte [Criar um esquema personalizado para usar com a implementação do Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

      +++Usar o esquema do Adobe Analytics

      | Vantagens | Desvantagens |
      |----------|---------|
      | <p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade para atualizar<p>Se você já estiver enviando dados para o Adobe Analytics com o SDK da web da Adobe Experience Platform, é possível adicionar um serviço extra à sequência de dados para enviar dados para a Adobe Experience Platform (que também pode ser usado na configuração do Customer Journey Analytics).</p></li></ul> | <p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite a maneira como você utiliza outros aplicativos da Platform, ele é um esquema um pouco mais complexo. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados pela organização.<p>Quando é preciso realizar alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></li></ul> |

      +++

      +++Criar um esquema do XDM

      | Vantagens | Desvantagens |
      |----------|---------|
      | <ul><p>As vantagens de utilizar seu próprio esquema XDM incluem:</p><ul><li>Um esquema simplificado e adaptado às necessidades da organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando é preciso realizar alterações no esquema, não é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></ul> | <p>As desvantagens de utilizar seu próprio esquema XDM incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário para começar a enviar dados à Platform.</li></ul> |

      +++

   1. Use o mapeamento do fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.

      Para obter mais informações, consulte [Mapeamento](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) em [Preparação de dados para coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) na documentação do Experience Platform.

{{upgrade-final-step}}.




