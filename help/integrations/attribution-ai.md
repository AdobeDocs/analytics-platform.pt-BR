---
description: Descubra como o AEP Attribution AI se integra ao Workspace no CJA.
title: Integrar o Attribution AI ao CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 4%

---

# Integrar o Attribution AI ao CJA

>[!NOTE]
>
>Esta página está em construção.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), como parte dos Serviços inteligentes da Adobe Experience Platform, é um serviço de atribuição de vários canais e algoritmos que calcula a influência e o impacto incremental das interações com o cliente em relação aos resultados especificados. Com o Attribution AI, os profissionais de marketing podem medir e otimizar os gastos com marketing e publicidade, entendendo o impacto de cada interação individual com o cliente em cada fase das jornadas do cliente.

O Attribution AI suporta duas categorias de pontuações: algorítmico e baseado em regras. As pontuações algorítmicas incluem pontuações incrementais e influenciadas. As pontuações com base em regras incluem Primeiro toque, Último toque, Linear, Forma de U e Declínio de tempo. O Attribution AI suporta 3 esquemas de Experience Platform: Evento de experiência, Adobe Analytics e Evento de experiência do consumidor.

O Attribution AI integra-se ao Customer Journey Analytics (CJA) na medida em que o Attribution AI executa modelos em relação a dados e, em seguida, o CJA importa a saída desses modelos como um conjunto de dados, que pode ser integrado ao restante dos conjuntos de dados do CJA. Os conjuntos de dados habilitados para o Attribution AI podem ser aproveitados em exibições de dados e relatórios no CJA.

## Fluxo de trabalho

Algumas etapas são executadas no Adobe Experience Platform antes de trabalhar com a saída no CJA.

### Etapa 1: Fazer download das pontuações do Attribution AI

No Adobe Experience Platform, baixe as pontuações do Attribution AI, conforme descrito [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### Etapa 2: Criar uma instância do Attribution AI

No Experience Platform, crie uma instância do Attribution AI selecionando e mapeando dados, definindo eventos e treinando seus dados, conforme descrito [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Etapa 3: Configurar uma conexão CJA com conjuntos de dados do Attribution AI

No CJA, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados de Experience Platform que foram instrumentados para o Attribution AI. Esses conjuntos de dados são exibidos com o prefixo &quot;Pontuações de Attribution AI&quot;, como mostrado aqui:

![Pontuações do AAI](assets/aai-scores.png)

### Etapa 4: Criar visualizações de dados com base nessas conexões

No CJA,

## Diferenças entre o Attribution AI e o Attribution IQ

Portanto, quando você deve usar os dados do Attribution AI versus [Attribution IQ](/help/analysis-workspace/attribution/overview.md), um recurso CJA nativo? Esta tabela mostra algumas das diferenças na funcionalidade:

| Funcionalidade | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Atribuição fracionária | Sim | Não |
| Permite que os usuários ajustem o modelo | Não | Sim |
| A atribuição em canais (Observação: O AAI não usa os mesmos dados compilados que o CJA usa.) | Sim | Sim |
| Inclui pontuações incrementais e influenciadas | Sim | Não |
| Modelagem do Does ML | Sim | Sim |
| Modelagem do ML com previsões | Sim | Não |

{style=&quot;table-layout:auto&quot;}
