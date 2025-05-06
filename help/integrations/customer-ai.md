---
description: Descubra como os dados da IA do cliente da Adobe Experience Platform se integram ao espaço de trabalho no Customer Journey Analytics.
title: Integrar dados da IA do cliente
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
source-git-commit: ed7e9a6c34c5f8ba9ba4f75be05768409cbc158d
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 97%

---

# Integrar dados da IA do cliente

{{release-limited-testing}}

A [IA do cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=pt-BR), como parte dos Serviços inteligentes da Adobe Experience Platform, fornece aos profissionais de marketing o poder de gerar previsões de clientes individualmente.

Com a ajuda de fatores influentes, a IA do cliente pode informar o que um cliente deve fazer e por quê. Além disso, os profissionais de marketing podem se beneficiar das previsões e insights da IA do cliente para personalizar as experiências do cliente, disponibilizando as ofertas e mensagens mais apropriadas.

A IA do cliente depende de dados comportamentais individuais e de dados de perfil para pontuação de propensão. A IA do cliente é flexível, pois pode receber várias fontes de dados, incluindo Adobe Analytics, Adobe Audience Manager, dados de eventos de experiência do consumidor e dados de eventos de experiência. Se você usar o conector de origem da Experience Platform para trazer os dados do Adobe Audience Manager e do Adobe Analytics, o modelo seleciona automaticamente os tipos de evento padrão para treinar e pontuar o modelo. Se você trouxer seu próprio conjunto de dados de Evento de experiência sem tipos de evento padrão, todos os campos relevantes precisarão ser mapeados como eventos personalizados ou atributos de perfil se você quiser usá-lo no modelo. Isso pode ser feito na etapa de configuração da IA do cliente na Experience Platform. 

A IA do cliente pode integrar-se ao Customer Journey Analytics, permitindo que os conjuntos de dados habilitados para a IA do cliente sejam aproveitados nas visualizações de dados e relatórios do Customer Journey Analytics. É possível:

* **Rastrear as pontuações de propensão de um segmento de usuários ao longo do tempo**. 
   * Caso de uso: entender a probabilidade de conversão de clientes em um segmento específico.
   * Exemplo: um(a) profissional de marketing em uma rede de hotéis quer entender a probabilidade de clientes de um hotel comprarem ingressos para um programa no teatro do hotel.
* **Analise quais eventos ou atributos de sucesso estão associados às pontuações de propensão**. 
   * Caso de uso: entender os atributos ou eventos de sucesso associados às pontuações de propensão.
   * Exemplo: um(a) profissional de marketing de uma rede de hotéis quer entender como as compras de ingressos para programas no teatro de um hotel estão associadas às pontuações de propensão.
* **Siga o fluxo de entrada de propensão do cliente em diferentes casos de pontuação**. 
   * Caso de uso: descobrir quais pessoas eram inicialmente usuários de baixa propensão e, com o tempo, se tornaram usuários de alta propensão.
   * Exemplo: um(a) profissional de marketing em uma rede de hotéis quer entender quais clientes do hotel foram identificados(as) inicialmente como clientes com baixa propensão a comprar ingressos para um programa, mas que com o tempo se tornaram clientes com alta propensão a comprar ingressos para um programa.
* **Veja a distribuição da propensão**. 
   * Caso de uso: entender a distribuição das pontuações de propensão para maior precisão na definição de segmentos.
   * Exemplo: um varejista deseja aplicar uma promoção específica que oferece US$ 50 de desconto em um produto. É possível que queiram executar apenas uma promoção muito limitada devido ao orçamento ou outros fatores. Os dados são analisados e decide-se direcionar a promoção apenas a clientes com uma propensão superior a 80%.
* **Examine a “propensão de se realizar uma ação” de um coorte específico ao longo do tempo**. 
   * Caso de uso: rastrear um coorte específico ao longo do tempo. 
   * Exemplo: um(a) profissional de marketing em uma rede de hotéis quer rastrear clientes de nível bronze em comparação com os de nível prata, ou os de nível prata em comparação com os de nível ouro, ao longo do tempo. É possível visualizar a propensão de cada coorte em efetuar reservas no hotel ao longo do tempo. 

Para integrar de fato os dados da IA do cliente ao Customer Journey Analytics, siga estas etapas:

>[!NOTE]
>
>Algumas etapas são executadas na Adobe Experience Platform antes de trabalhar com a saída no Customer Journey Analytics.


## Etapa 1: Configurar uma instância da IA do cliente

Depois de preparar seus dados e ter todas as credenciais e esquemas em vigor, comece seguindo o guia [Configurar uma instância da IA do cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=pt-BR) na Adobe Experience Platform.

## Etapa 2: configurar uma conexão do Customer Journey Analytics com conjuntos de dados da IA do cliente

No Customer Journey Analytics, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados da Experience Platform que foram instrumentados para a IA do cliente. Cada previsão, como “Probabilidade de atualização da conta”, equivale a um conjunto de dados. Esses conjuntos de dados são exibidos com o prefixo “Pontuações da IA do cliente no formato EE - nome_do_aplicativo”.

>[!IMPORTANT]
>
>Cada instância da IA do cliente tem dois conjuntos de dados de saída quando o botão que habilita pontuações para o Customer Journey Analytics (na configuração da Etapa 1) está ativado. Um conjunto de dados de saída é exibido no formato XDM do perfil e um no formato XDM do evento da experiência.

![Pontuações de CAI](assets/cai-scores.png)

![Criar conexão](assets/create-conn.png)

Veja um exemplo de um esquema XDM que o Customer Journey Analytics traria como parte de um conjunto de dados existente ou novo:

![Esquema de CAI](assets/cai-schema.png)

(Observe que o exemplo mostra um conjunto de dados de perfil; o mesmo conjunto de objetos de esquema seria parte de um conjunto de dados de evento de experiência que o Customer Journey Analytics capturaria. O conjunto de dados do Evento de experiência incluiria carimbos de data e hora como a data da pontuação.) Cada cliente classificado neste modelo teria uma pontuação, uma scoreDate, etc. associada a eles.

## Etapa 3: Criar visualizações de dados com base nessas conexões

No Customer Journey Analytics, agora você pode prosseguir e [criar visualizações de dados](/help/data-views/create-dataview.md) com as dimensões (como pontuação, data de pontuação, probabilidade etc.) e métricas que foram trazidas como parte da conexão estabelecida.

![Criar janela de exibição de dados](assets/create-dataview.png)

## Etapa 4: relatório das pontuações de CAI no espaço de trabalho

No espaço de trabalho do Customer Journey Analytics, crie um novo projeto e abra as visualizações.

### Pontuações de propensão de tendência

Este é um exemplo de um projeto do Workspace com dados de CAI que realiza a tendência das pontuações de propensão para um segmento de usuários ao longo do tempo, em &#x200B;um gráfico de barras empilhadas:

![Intervalos de pontuação](assets/workspace-scores.png)

### Tabela com códigos de motivo

É uma tabela que mostra códigos de motivo pelo qual um segmento tem alta ou baixa propensão:

![Códigos de motivo](assets/reason-codes.png)

### Fluxo de entrada para propensão do cliente

Este diagrama de fluxo mostra o fluxo de entrada para a propensão do cliente em diferentes execuções de pontuação &#x200B;:

![Fluxo de entrada](assets/flow.png)

### Distribuição das pontuações de propensão

Este gráfico de barras mostra a distribuição das pontuações de propensão:

![Distribuição](assets/distribution.png)

### Sobreposições de propensão

Este diagrama Venn mostra as sobreposições de propensão em diferentes execuções de pontuação:

![Sobreposições de propensão](assets/venn.png)
