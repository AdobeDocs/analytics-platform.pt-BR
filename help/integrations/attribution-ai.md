---
description: Descubra como o AEP Attribution AI se integra ao Workspace no CJA.
title: Integrar o Attribution AI ao CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 77b253390dafb27228995f339d138eb9f4fa2c56
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 3%

---

# Integrar o Attribution AI ao CJA

>[!NOTE]
>
>Essa funcionalidade será lançada em 25 de maio de 2022.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), como parte dos Serviços inteligentes da Adobe Experience Platform, é um serviço de atribuição de vários canais e algoritmos que calcula a influência e o impacto incremental das interações com o cliente em relação aos resultados especificados. Com o Attribution AI, os profissionais de marketing podem medir e otimizar os gastos com marketing e publicidade, entendendo o impacto de cada interação individual com o cliente em cada fase das jornadas do cliente.

O Attribution AI suporta duas categorias de pontuações: algorítmico e baseado em regras. As pontuações algorítmicas incluem pontuações incrementais e influenciadas.

* **Pontuações influenciadas** divida 100% do crédito de conversão entre canais de marketing.
* **Pontuações incrementais** primeiro, considere uma linha de base de conversão que você teria alcançado mesmo sem marketing. Essa linha de base depende de observações de IA de padrões, sazonalidade e assim por diante, devido ao reconhecimento de marca, fidelidade e palavra de boca existentes. O crédito restante é dividido entre os canais de marketing.

As pontuações baseadas em regras incluem [!UICONTROL Primeiro contato], [!UICONTROL Último contato], [!UICONTROL Linear], [!UICONTROL Forma de U]e [!UICONTROL Declínio de tempo]. O Attribution AI suporta 3 esquemas de Experience Platform: Evento de experiência, Adobe Analytics e Evento de experiência do consumidor.

O Attribution AI integra-se ao Customer Journey Analytics (CJA) na medida em que o Attribution AI executa modelos em relação a dados e, em seguida, o CJA importa a saída desses modelos como um conjunto de dados, que pode ser integrado ao restante dos conjuntos de dados do CJA. Os conjuntos de dados habilitados para o Attribution AI podem ser aproveitados em exibições de dados e relatórios no CJA.

## Fluxo de trabalho

Algumas etapas são executadas no Adobe Experience Platform antes de trabalhar com a saída no CJA. A saída consiste em um conjunto de dados com um modelo de Attribution AI aplicado.

### Etapa 1: Fazer download das pontuações do Attribution AI

No Adobe Experience Platform, baixe as pontuações do Attribution AI, conforme descrito [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### Etapa 2: Criar uma instância do Attribution AI

No Experience Platform, crie uma instância do Attribution AI selecionando e mapeando dados, definindo eventos e treinando seus dados, conforme descrito [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Etapa 3: Configurar uma conexão CJA com conjuntos de dados do Attribution AI

No CJA, agora você pode [criar uma ou mais conexões](/help/connections/create-connection.md) para conjuntos de dados de Experience Platform que foram instrumentados para o Attribution AI. Esses conjuntos de dados são exibidos com o prefixo &quot;Pontuações de Attribution AI&quot;, como mostrado aqui:

![Pontuações do AAI](assets/aai-scores.png)

>[!IMPORTANT]
>
>Você pode adicionar perfis e conjuntos de dados de pesquisa, bem como call center e dados de CRM à conexão. No entanto, o Adobe não recomenda adicionar conjuntos de dados do Adobe Analytics a conjuntos de dados com pontuações do Attribution AI na mesma conexão.


### Etapa 4: Criar visualizações de dados com base nessas conexões

No CJA, [criar uma ou mais visualizações de dados](/help/data-views/create-dataview.md) que contêm os campos XDM do Attribution AI. (Seria ótimo ter uma captura de tela aqui.)

### Etapa 5: Relatório de dados do AAI no CJA Workspace

Em um projeto do CJA Workspace, você pode obter métricas como &quot;Pedidos de AAI&quot; e dimensões como &quot;Nome da campanha AAI&quot; ou &quot;Canal de marketing AAI&quot;, por exemplo.

![Dimensões de AAI](assets/aai-dims.png)

Aqui vemos um projeto do Workspace com dados do AAI que mostra pedidos com pontuações influenciadas e incrementais.

![Projeto AAI](assets/aai-project.png)

![Projeto AAI](assets/aai-project2.png)


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
