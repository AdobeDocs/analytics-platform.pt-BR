---
description: Descubra como a AEP Customer AI se integra ao Workspace no CJA.
title: Integrar o Customer AI ao CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: 0b095edc3ad8f5121818feafa6edb3f826bee84c
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---


# Integrar o Customer AI ao CJA

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), como parte dos Serviços inteligentes da Adobe Experience Platform, fornece aos profissionais de marketing o poder de gerar previsões de clientes em nível individual.

Com a ajuda de fatores influentes, a AI do cliente pode informar o que um cliente deve fazer e por quê. Além disso, os profissionais de marketing podem se beneficiar das previsões e insights do Customer AI para personalizar as experiências do cliente, disponibilizando as ofertas e mensagens mais apropriadas.

O Customer AI funciona analisando um dos seguintes conjuntos de dados para prever pontuações de abandono ou propensão de conversão:

* Dados do Adobe Analytics usando o conector de origem do Analytics
* Dados do Adobe Audience Manager usando o conector de origem Audience Manager
* Conjunto de dados Evento de experiência (EE)
* Conjunto de dados CEE (Evento de experiência do consumidor)

O Customer AI integra-se ao Customer Journey Analytics (CJA) na medida em que os conjuntos de dados habilitados para o Customer AI possam ser aproveitados nas visualizações de dados e relatórios no CJA.

## Fluxo de trabalho

Algumas etapas são executadas no Adobe Experience Platform antes de trabalhar com a saída no CJA.

### Etapa 1: Fazer download das pontuações do Customer AI

O download das pontuações do Customer AI é feito por meio de uma combinação de chamadas do Experience Platform API, conforme descrito [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### Etapa 2: Definir entradas e saídas do Customer AI

Esse processo é descrito na seção [Entrada e saída no Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) documentação.

### Etapa 3: Configurar uma instância do Customer AI

Depois de preparar seus dados e ter todas as credenciais e esquemas em vigor, comece seguindo a [Configurar uma instância do Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guia.

### Etapa 4: Configurar uma conexão CJA com conjuntos de dados do Customer AI

No CJA, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados de Experience Platform que foram instrumentados para a API do cliente. Esses conjuntos de dados aparecem com o prefixo &quot;Pontuações do Customer AI&quot;, como mostrado aqui:

![Pontuações de CAI](assets/cai-scores.png)

Cada previsão, como &quot;Probabilidade de atualização da conta&quot;, equivale a um conjunto de dados.

Este é um exemplo de um esquema XDM que o CJA traria como parte de um conjunto de dados existente ou novo:

![Esquema CAI](assets/cai-schema.png)

(Observe que o exemplo é um conjunto de dados de perfil; o mesmo conjunto de objetos de esquema seria parte de um conjunto de dados de Evento de experiência que o CJA capturaria. O conjunto de dados do Evento de experiência incluiria carimbos de data e hora como a data da pontuação.) Cada cliente classificado neste modelo teria uma pontuação, uma scoreDate, etc. associado a eles.

### Etapa 5: Criar visualizações de dados com base nessas conexões

No CJA, agora você pode continuar a criar visualizações de dados com as dimensões que foram trazidas como parte da conexão estabelecida.