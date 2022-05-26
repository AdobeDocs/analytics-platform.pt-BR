---
description: Descubra como a AEP Customer AI se integra ao Workspace no CJA.
title: Integrar o Customer AI ao CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 320b34ca171bb835aa3b4a9a981cc19b14060ad9
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# Integrar o Customer AI ao CJA

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), como parte dos Serviços inteligentes da Adobe Experience Platform, fornece aos profissionais de marketing o poder de gerar previsões de clientes em nível individual.

Com a ajuda de fatores influentes, a AI do cliente pode informar o que um cliente deve fazer e por quê. Além disso, os profissionais de marketing podem se beneficiar das previsões e insights do Customer AI para personalizar as experiências do cliente, disponibilizando as ofertas e mensagens mais apropriadas.

O Customer AI depende de dados comportamentais individuais e de dados de perfil para pontuação de propensão. O Customer AI é flexível, pois pode receber várias fontes de dados, incluindo Adobe Analytics, Adobe Audience Manager, dados de eventos de experiência do consumidor e dados de eventos de experiência. Se você usar o conector de origem do Experience Platform para trazer os dados do Adobe Audience Manager e do Adobe Analytics, o modelo seleciona automaticamente os tipos de evento padrão para treinar e pontuar o modelo. Se você trazer seu próprio conjunto de dados de Evento de experiência sem tipos de evento padrão, quaisquer campos relevantes precisarão ser mapeados como eventos personalizados ou atributos de perfil se quiser usá-lo no modelo. Isso pode ser feito na etapa de configuração do Customer AI no Experience Platform. &#x200B;

O Customer AI integra-se ao Customer Journey Analytics (CJA) na medida em que os conjuntos de dados habilitados para o Customer AI possam ser aproveitados nas visualizações de dados e relatórios no CJA. Com essa integração, você pode

* **Rastrear as pontuações de propensão para um segmento de usuários ao longo do tempo**. Exemplo de caso de uso: Qual é a probabilidade de um cliente de hotel comprar um ingresso no local do concerto do hotel?
* **Analisar quais eventos ou atributos de sucesso estão associados às pontuações de propensão**. &#x200B;Exemplo de caso de uso: Quero entender os atributos ou eventos de sucesso associados às pontuações de propensão.
* **Siga o fluxo de entrada para a propensão do cliente em diferentes execuções de pontuação**. Exemplo de caso de uso: Gostaria de entender as pessoas que eram inicialmente usuários de baixa propensão e, com o tempo, se tornaram usuários de alta propensão. &#x200B;
* **Veja a distribuição da propensão**. Caso de uso: Eu gostaria de entender a distribuição das pontuações de propensão para que eu possa ser mais preciso com meus segmentos. &#x200B;Exemplo: um varejista deseja executar uma promoção específica de US$ 50 de um produto. Eles podem querer executar apenas uma promoção muito limitada devido ao orçamento, etc. Eles analisam os dados e decidem direcionar somente os mais de 80% &#x200B; principais de seus clientes.
* **Examine a propensão para realizar uma ação para um coorte específico ao longo do tempo**. Caso de uso: Gostaria de rastrear um coorte específico ao longo do tempo. Isso é semelhante ao primeiro, mas é possível rastrear um coorte específico ao longo do tempo. &#x200B; Exemplo de hospitalidade: Um comerciante pode rastrear a camada de bronze em relação à camada de prata, ou camada de prata em relação à camada de ouro ao longo do tempo. Então eles podem ver a propensão de cada coorte para reservar o hotel ao longo do tempo. &#x200B;

## Fluxo de trabalho

Algumas etapas são executadas no Adobe Experience Platform antes de trabalhar com a saída no CJA.

### Etapa 1: Configurar uma instância do Customer AI

Depois de preparar seus dados e ter todas as credenciais e esquemas em vigor, comece seguindo a [Configurar uma instância do Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) no Adobe Experience Platform.

### Etapa 2: Configurar uma conexão CJA com conjuntos de dados do Customer AI

No CJA, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados de Experience Platform que foram instrumentados para a API do cliente. Cada previsão, como &quot;Probabilidade de atualização da conta&quot;, equivale a um conjunto de dados. Esses conjuntos de dados são exibidos com o prefixo &quot;Pontuações do Customer AI no formato EE - nome_do_aplicativo&quot;.

>[!IMPORTANT]
>
>Cada instância do Customer AI tem dois conjuntos de dados de saída se o botão estiver ativado para ativar pontuações para CJA durante a configuração na Etapa 1. Um conjunto de dados de saída é exibido no formato XDM do perfil e um no formato XDM do evento da experiência.

![Pontuações de CAI](assets/cai-scores.png)

![Criar conexão](assets/create-conn.png)

Este é um exemplo de um esquema XDM que o CJA traria como parte de um conjunto de dados existente ou novo:

![Esquema CAI](assets/cai-schema.png)

(Observe que o exemplo é um conjunto de dados de perfil; o mesmo conjunto de objetos de esquema seria parte de um conjunto de dados de Evento de experiência que o CJA capturaria. O conjunto de dados do Evento de experiência incluiria carimbos de data e hora como a data da pontuação.) Cada cliente classificado neste modelo teria uma pontuação, uma scoreDate, etc. associado a eles.

### Etapa 3: Criar visualizações de dados com base nessas conexões

No CJA, agora você pode prosseguir para [criar visualizações de dados](/help/data-views/create-dataview.md) com as dimensões (como pontuação, data de pontuação, probabilidade etc.) e métricas que foram trazidas como parte da conexão estabelecida.

![Criar visualização de dados](assets/create-dataview.png)

### Etapa 4: Relatório das pontuações de CAI no Workspace

Na CJA Workspace, agora é possível criar um novo projeto e extrair visualizações.

**Pontuações de propensão de tendência**

Este é um exemplo de um projeto do Workspace com dados de CAI que realiza a tendência das pontuações de propensão para um segmento de usuários ao longo do tempo, em &#x200B; um gráfico de barras empilhadas:

![Classificações por pontuação](assets/workspace-scores.png)

**Tabela com códigos de motivo**

Esta é uma tabela que mostra códigos de motivo para o motivo pelo qual um segmento tem &#x200B; de alta ou baixa propensão:

![Códigos de motivo](assets/reason-codes.png)

**Fluxo de entrada para propensão do cliente**

Este diagrama de fluxo mostra o fluxo de entrada para a propensão do cliente em diferentes execuções de pontuação &#x200B;:

![Fluxo de entrada](assets/flow.png)

**Distribuição das pontuações de propensão**

Este gráfico de barras mostra a distribuição das pontuações de propensão &#x200B;:

![Distribuição](assets/distribution.png)

**Sobreposições de propensão**

Este diagrama Venn mostra as sobreposições de propensão em diferentes execuções de pontuação:

![Sobreposições de propensão](assets/venn.png)
