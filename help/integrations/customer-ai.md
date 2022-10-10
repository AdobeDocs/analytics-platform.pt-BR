---
description: Descubra como a IA do cliente da AEP se integra ao Workspace no CJA.
title: Integrar a IA do cliente ao CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 317e45146d493f969176bc026590fa894b4d7fb1
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 90%

---

# Integrar os dados do Customer AI ao CJA

>[!NOTE]
>
>Essa funcionalidade está atualmente em [teste limitado](/help/release-notes/releases.md) e não está disponível em geral.

A [IA do cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=pt-BR), como parte dos Serviços inteligentes da Adobe Experience Platform, fornece aos profissionais de marketing o poder de gerar previsões de clientes individualmente.

Com a ajuda de fatores influentes, a IA do cliente pode informar o que um cliente deve fazer e por quê. Além disso, os profissionais de marketing podem se beneficiar das previsões e insights da IA do cliente para personalizar as experiências do cliente, disponibilizando as ofertas e mensagens mais apropriadas.

A IA do cliente depende de dados comportamentais individuais e de dados de perfil para pontuação de propensão. A IA do cliente é flexível, pois pode receber várias fontes de dados, incluindo Adobe Analytics, Adobe Audience Manager, dados de eventos de experiência do consumidor e dados de eventos de experiência. Se você usar o conector de origem da Experience Platform para trazer os dados do Adobe Audience Manager e do Adobe Analytics, o modelo seleciona automaticamente os tipos de evento padrão para treinar e pontuar o modelo. Se você trouxer seu próprio conjunto de dados de Evento de experiência sem tipos de evento padrão, todos os campos relevantes precisarão ser mapeados como eventos personalizados ou atributos de perfil se você quiser usá-lo no modelo. Isso pode ser feito na etapa de configuração da IA do cliente na Experience Platform. &#x200B;

A IA do cliente integra-se ao Customer Journey Analytics (CJA) na medida em que os conjuntos de dados habilitados para a IA do cliente possam ser aproveitados nas visualizações de dados e relatórios no CJA. Com essa integração, você pode

* **Rastrear as pontuações de propensão para um segmento de usuários ao longo do tempo**. Exemplo de caso de uso: Qual é a probabilidade de um cliente de hotel comprar um ingresso no local do concerto do hotel?
* **Analisar quais eventos ou atributos de sucesso estão associados às pontuações de propensão**. &#x200B;Exemplo de caso de uso: quero entender os atributos ou eventos de sucesso associados às pontuações de propensão.
* **Siga o fluxo de entrada para a propensão do cliente em diferentes execuções de pontuação**. Exemplo de caso de uso: Gostaria de entender as pessoas que eram inicialmente usuários de baixa propensão e, com o tempo, se tornaram usuários de alta propensão. &#x200B;
* **Veja a distribuição da propensão**. Caso de uso: Gostaria de entender a distribuição das pontuações de propensão para que eu possa ser mais preciso com meus segmentos. &#x200B;Exemplo: um varejista deseja executar uma promoção específica que oferece US$ 50 de desconto em um produto. Eles podem querer executar apenas uma promoção muito limitada devido ao orçamento, etc. Eles analisam os dados e decidem segmentar apenas os 80%+&#x200B; de seus clientes.
* **Examine a propensão para realizar uma ação para um coorte específico ao longo do tempo**. Caso de uso: Gostaria de rastrear um coorte específico ao longo do tempo. É semelhante ao primeiro, mas é possível rastrear um coorte específico ao longo do tempo. &#x200B; Exemplo de hospitalidade: um comerciante pode rastrear o nível bronze em relação ao nível prata, ou nível prata em relação ao nível ouro ao longo do tempo. Dessa forma, eles podem ver a propensão de cada coorte para reservar o hotel ao longo do tempo. &#x200B;

## Fluxo de trabalho

Algumas etapas são executadas na Adobe Experience Platform antes de trabalhar com a saída no CJA.

### Etapa 1: Configurar uma instância da IA do cliente

Depois de preparar seus dados e ter todas as credenciais e esquemas em vigor, comece seguindo o guia [Configurar uma instância da IA do cliente](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=pt-BR) na Adobe Experience Platform.

### Etapa 2: Configurar uma conexão do CJA com conjuntos de dados da IA do cliente

No CJA, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados da Experience Platform que foram instrumentados para a API do cliente. Cada previsão, como “Probabilidade de atualização da conta”, equivale a um conjunto de dados. Esses conjuntos de dados são exibidos com o prefixo “Pontuações da IA do cliente no formato EE - nome_do_aplicativo”.

>[!IMPORTANT]
>
>Cada instância da IA do cliente tem dois conjuntos de dados de saída se o botão estiver ativado para habilitar pontuações para o CJA durante a configuração na Etapa 1. Um conjunto de dados de saída é exibido no formato XDM do perfil e um no formato XDM do evento da experiência.

![Pontuações de CAI](assets/cai-scores.png)

![Criar conexão](assets/create-conn.png)

Este é um exemplo de um esquema XDM que o CJA traria como parte de um conjunto de dados existente ou novo:

![Esquema de CAI](assets/cai-schema.png)

(Observe que o exemplo é um conjunto de dados de perfil; o mesmo conjunto de objetos de esquema seria parte de um conjunto de dados de Evento de experiência que o CJA capturaria. O conjunto de dados do Evento de experiência incluiria carimbos de data e hora como a data da pontuação.) Cada cliente classificado neste modelo teria uma pontuação, uma scoreDate, etc. associada a eles.

### Etapa 3: Criar visualizações de dados com base nessas conexões

No CJA, agora você pode prosseguir para [criar visualizações de dados](/help/data-views/create-dataview.md) com as dimensões (como pontuação, data de pontuação, probabilidade etc.) e métricas que foram trazidas como parte da conexão estabelecida.

![Criar visualização de dados](assets/create-dataview.png)

### Etapa 4: Relatório das pontuações de CAI no Workspace

No Workspace do CJA, crie um novo projeto e extraia visualizações.

**Pontuações de propensão de tendência**

Este é um exemplo de um projeto do Workspace com dados de CAI que realiza a tendência das pontuações de propensão para um segmento de usuários ao longo do tempo, em &#x200B;um gráfico de barras empilhadas:

![Intervalos de pontuação](assets/workspace-scores.png)

**Tabela com códigos de motivo**

É uma tabela que mostra códigos de motivo pelo qual um segmento tem alta ou baixa propensão:

![Códigos de motivo](assets/reason-codes.png)

**Fluxo de entrada para propensão do cliente**

Este diagrama de fluxo mostra o fluxo de entrada para a propensão do cliente em diferentes execuções de pontuação &#x200B;:

![Fluxo de entrada](assets/flow.png)

**Distribuição das pontuações de propensão**

Este gráfico de barras mostra a distribuição das pontuações de propensão:

![Distribuição](assets/distribution.png)

**Sobreposições de propensão**

Este diagrama Venn mostra as sobreposições de propensão em diferentes execuções de pontuação:

![Sobreposições de propensão](assets/venn.png)
