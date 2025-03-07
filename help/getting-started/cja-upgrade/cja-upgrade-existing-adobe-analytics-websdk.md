---
title: Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados à Platform
description: Saiba como configurar a implementação existente do Adobe Analytics Web SDK
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1459a512-bfa8-4805-97e8-5b6acc6e4ac9
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 53%

---

# Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados à Platform {#existing-websdk-implementation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-remove-aa-from-datastream"
>title="Remover o Adobe Analytics como um serviço do fluxo de dados"
>abstract="Com os dados do Web SDK totalmente funcionais, trabalhe com o administrador da Platform para remover o Adobe Analytics as a service do fluxo de dados. Antes de fazer isso, verifique se os usuários passaram do Adobe Analytics para o Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Se sua implementação do Adobe Analytics já estiver usando o Adobe Experience Platform Web SDK, você poderá começar a enviar dados para a Platform configurando um fluxo de dados. Ou, se você já estiver enviando dados para a Platform, basta criar uma conexão entre os conjuntos de dados da Platform e a Customer Journey Analytics.


## Vantagens e desvantagens

Considere as seguintes vantagens e desvantagens de configurar sua implementação existente do Adobe Analytics Web SDK para enviar dados à Platform:

| Vantagens | Desvantagens |
|----------|---------|
| Esse é o caminho de atualização preferencial se a implementação do Adobe Analytics já estiver usando a Web SDK.<ul><li>**Mostra todas as vantagens de hospedar dados na Experience Edge Network**: <p>As vantagens incluem:</p><ul><li>Geração de relatórios com alto desempenho e disponibilidade de dados devido à capacidade da Adobe Experience Platform de potencializar [casos de uso de personalização em tempo real](https://experienceleague.adobe.com/br/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html)</li><li>Consolidar a implementação da coleção de dados da Adobe Experience Cloud entre outros produtos da Experience Cloud (AJO, RTCDP e assim por diante)</li><li>Não dependente da nomenclatura do Adobe Analytics (prop, eVar, evento etc.)</li></ul><li>**Uso da implementação existente**: embora sejam necessárias algumas alterações de implementação, essa abordagem não exige uma implementação totalmente nova. Você pode usar sua camada de dados e código existentes com alterações mínimas na lógica de implementação sem afetar os relatórios existentes do Adobe Analytics.</li><li>**Fornece uma opção para usar um esquema XDM**: é possível optar por usar seu esquema do Adobe Analytics existente ou criar um esquema XDM e mapear campos no objeto de dados desse esquema. [Esquemas XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home#xdm-schemas) são flexíveis e permitem definir quaisquer campos necessários e relevantes. <p>Consulte “Usar seu próprio esquema XDM” abaixo para obter mais informações sobre as vantagens de usar seu próprio esquema XDM.</p></li><li>**Mantém regras e elementos de dados**: embora sejam necessárias novas ações de regra, é possível reutilizar elementos de dados e condições de regra existentes com alterações mínimas.</li><li>**À prova de obsolescência**: se você optar por usar seu próprio esquema XDM, isso facilitará as atualizações de implementação futuras.</li></ul> | <ul><li>**Requisito de mapeamento para envio de dados para a Platform**: quando sua organização estiver pronta para usar o Customer Journey Analytics, envie dados para um conjunto de dados na Adobe Experience Platform. Essa ação exige que cada campo no objeto de dados seja uma entrada na ferramenta de mapeamento de sequência de dados que o atribui a um campo de esquema XDM. O mapeamento só precisa ser feito uma vez para esse fluxo de trabalho e não é necessário fazer alterações de implementação. No entanto, essa é uma etapa extra que não é necessária ao enviar dados em um objeto XDM.</li><li>**Apresenta complexidade adicional ao longo do tempo**: qualquer campo adicionado no futuro deve ser mapeado para XDM na sequência de dados.<p>Sempre que um novo campo for adicionado à implementação, você poderá executar um dos seguintes procedimentos:</p><ul><li>**Opção 1:** Preencha uma nova evar arbitrária ou uma nova prop no objeto de dados e mapeie-a para o campo XDM desejado.<p>Esse processo aumenta a consistência para a implementação no lado do cliente, mas requer mapeamento.</p></li><li>**Opção 2:** Deixe o objeto de dados como uma implementação herdada e comece a preencher somente o objeto XDM para todos os novos campos.<p>Esse processo não requer mapeamento, mas significa que algumas de suas variáveis estão localizadas apenas em um objeto de dados, enquanto outras variáveis estão localizadas apenas em um objeto XDM. Sempre que precisar solucionar problemas de implementação, você precisará ir para dois lugares. Verifique se os workflows internos acomodam isso.</p></li></ul> |

{style="table-layout:auto"}

## Etapas da implementação

1. Comece a enviar dados do Edge Network para a Platform. Envie todas as variáveis no formato AppMeasurement por meio do objeto de dados.

   Para obter mais informações, consulte [Mapeamento de variável de objeto de dados para Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/data-var-mapping).

1. Escolha seu esquema.

   Você pode escolher se deseja usar seu esquema existente do Adobe Analytics ou criar um esquema XDM para se alinhar melhor às necessidades da organização à medida que começa a usar outros serviços da plataforma.

   A Adobe recomenda criar um esquema XDM. Para obter mais informações, consulte [Criar um esquema personalizado para usar com a implementação do Customer Journey Analytics Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md).

   +++Usar o esquema do Adobe Analytics

   | Vantagens | Desvantagens |
   |----------|---------|
   | <p>As vantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Facilidade de atualização<p>Se você já estiver enviando dados para o Adobe Analytics com o SDK da web da Adobe Experience Platform, é possível adicionar um serviço extra à sequência de dados para enviar dados para a Adobe Experience Platform (que também pode ser usado na configuração do Customer Journey Analytics).</p></li></ul> | <p>As desvantagens de usar o esquema do Adobe Analytics incluem:</p><ul><li>Embora o uso do esquema do Adobe Analytics não limite a maneira como você utiliza outros aplicativos da Platform, ele é um esquema um pouco mais complexo. Isso ocorre porque o esquema do Adobe Analytics contém muitos objetos específicos do Adobe Analytics que provavelmente não serão usados pela organização.<p>Quando é preciso realizar alterações no esquema, é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></li></ul> |

+++

   +++Criar um esquema XDM

   | Vantagens | Desvantagens |
   |----------|---------|
   | <ul><p>As vantagens de utilizar seu próprio esquema XDM incluem:</p><ul><li>Um esquema simplificado e adaptado às necessidades da organização e aos aplicativos específicos da Platform que você usa.</li><p>Quando é preciso realizar alterações no esquema, não é necessário analisar milhares de campos não utilizados para localizar o campo que precisa de atualização.</p></ul> | <p>As desvantagens de utilizar seu próprio esquema XDM incluem:</p><ul><li>A atualização do esquema é um processo demorado e necessário antes de você começar a enviar dados para a Platform.</li></ul> |

+++

1. Use o mapeamento do fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.

   Para obter mais informações, consulte [Mapeamento](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep?lang=en#mapping) em [Preparação de dados para coleção de dados](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) na documentação do Experience Platform.

{{upgrade-final-step}}
