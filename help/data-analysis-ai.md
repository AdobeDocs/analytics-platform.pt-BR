---
description: Como fazer perguntas sobre a análise de dados da documentação do Customer Journey Analytics
title: Assistente de IA de análise de dados no Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 376ad62c3883eef675f9b1df639e8c46ee259229
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 3%

---


# Assistente de IA de análise de dados em Customer Journey Analytics - Alpha

O Assistente de IA de análise de dados é um agente de conversação de IA gerativa que pode ajudá-lo a responder de forma mais rápida e eficiente às perguntas que você possa ter sobre seus dados do Analysis Workspace no Customer Journey Analytics.

Quando você faz uma pergunta no Assistente de IA, ele verifica todos os componentes na visualização de dados, incluindo os diferentes tipos de métricas e componentes, e traduz o prompt para a dimensão, a métrica e o intervalo de datas corretos para a análise. Em vez de precisar se familiarizar com os componentes da visualização de dados e, em seguida, arrastar e soltar esses componentes na melhor combinação para responder à sua pergunta, você pode simplesmente digitar a pergunta no Assistente de IA.

![Assistente de IA de análise de dados](assets/cja-ai-asst-da.gif)

## Recursos dentro e fora do escopo da versão do Alpha

### Recursos de Alpha dentro do escopo

| Recurso suportado | Descrição |
| --- | --- |
| **Criar e atualizar visualizações** | Gera uma tabela de forma livre e uma visualização associada (por exemplo, linha, barra, rosca etc.).<p>Exemplo: *Qual é o lucro entre SKUs de fevereiro a maio?* |
| **Tipos de visualização com suporte** | <ul><li>Linha</li><li>Várias linhas</li><li>Forma livre</li><li>Barra</li><li>Rosca</li><li>Número do resumo</li></ul> |
| **Detecção de prompt fora do escopo** | Se você enviar um prompt que está fora do escopo, como &quot;exportar este projeto&quot;, o Assistente responderá informando que a pergunta está fora do escopo. |
| **Esclarecimento de questões** | Se você fizer uma pergunta que não tenha contexto suficiente para o Assistente de IA responder, ou que seja muito genérica, o Assistente de IA responderá com uma pergunta esclarecedora e/ou com opções sugeridas. Exemplos: <p>**Componentes**<ul><li>Métrica: *Qual métrica de &quot;receita&quot; você quis dizer?*</li><li>Dimension: *Em qual das &quot;regiões&quot; abaixo você deseja se concentrar?*</li><li>Filtro: *Qual filtro de &quot;Conta&quot; você deseja aplicar?*</li><li>Intervalo de datas: *Por &quot;último mês&quot;, você quis dizer o último mês completo ou os últimos 30 dias?*</li></ul>**itens de Dimension**: qual &quot;nome da loja&quot; você quis dizer? (por exemplo, Armazenamento #5274, Armazenamento #2949 etc.) |
| **Voltas múltiplas** | O Assistente de IA responde a um prompt com o contexto do(s) prompt(s) anterior(es), permitindo que os usuários atualizem as visualizações e façam perguntas de acompanhamento. Exemplo: <ul><li>Prompt 1: *Eventos de tendência de março.*</li><li>Prompt 2: *Mostrar os dados de março a abril*</li></ul> |
| **Verificabilidade** | A verificabilidade e a correção dos dados podem ser confirmadas por meio da tabela de forma livre gerada e da visualização de dados. Por exemplo, se um usuário solicitar *Pedidos de tendência no último mês*, você poderá confirmar se a métrica correta (&quot;pedidos&quot;) e o intervalo de datas (&quot;último mês&quot;) foram selecionados no painel recém-gerado, na visualização de dados e na tabela de forma livre. |
| **Feedback** | <ul><li>Polegar para cima</li><li>Polegar para baixo</li><li>Sinalizador</li></ul> |

### Recursos de Alpha fora do escopo

| Recurso não suportado | Descrição |
| --- | --- |
| **Resumo ou resposta embutida** | O Assistente de IA não pode responder em linha no painel de chat com uma resposta resumida de um prompt do usuário.Exemplo de prompts fora do escopo:<ul><li>*Forneça um resumo dos insights do meu último prompt.*</li><li>*Resuma os destaques da visualização de linha.*</li></ul> |
| **Esclarecimento de questões** | As perguntas de esclarecimento estão limitadas a componentes e itens de dimensão. O Assistente de IA não pode esclarecer visualizações de dados, visualizações, granularidade de dados, comparação, escopo etc. Sem esclarecer dúvidas, o Assistente assume como padrão o que você provavelmente está solicitando. Se retornar uma visualização ou granularidade de dados inesperada, você poderá usar o recurso de várias rodadas/atualização para ajustar a visualização e os dados. |
| **Ações/Recursos do Workspace** | O Assistente de IA não pode realizar ações para um usuário no Workspace além de criar e atualizar visualizações. Por exemplo, ela não pode executar nenhum dos seguintes procedimentos:<ul><li>Botões da interface de ação contextual (adicionar ao gráfico, novo painel, nova tabela)</li><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Gerenciar preferências do usuário</li><li>Preparar</li><li>Gerenciar visualização de dados</li><li>aplicativo Painéis do Analytics</li><li>Atribuição</li></ul> |
| **Tipos de visualização sem suporte** | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área, Área empilhada</li><li>Barra empilhada</li><li>Marcador</li><li>Combo</li><li>Histograma</li><li>Barra horizontal, Barra horizontal empilhada</li><li>Resumo da métrica principal</li><li>Dispersão</li><li>Mudança de resumo</li><li>Texto</li><li>Mapas de árvore</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Acessar e usar o Assistente do Data Analysis AI

1. Acesse [experience.adobe.com](https://experience.adobe.com/) e faça logon com sua Adobe ID.

2. Selecione **Customer Journey Analytics** na página inicial do Experience Cloud

3. Clique em **[!UICONTROL Projeto em branco]** no banner na parte superior da página de projetos para abrir um novo projeto em branco.

4. Certifique-se de que a visualização de dados selecionada para o painel é a visualização de dados que foi ativada para o uso do Assistente do AI para o teste de Alpha (acesse o canal do Alpha Slack se não tiver certeza)

5. Clique no ícone de bate-papo do Assistente do AI na parte superior direita.

   ![Ícone do Assistente de IA](/help/assets/ai-asst-icon.png)

6. Na caixa de diálogo **[!UICONTROL Pergunte sobre o Customer Journey Analytics]** na parte inferior, faça uma pergunta sobre análise de dados no Assistente de IA.

### Exemplo 1

Por exemplo, digamos que você esteja interessado nos pedidos que sua empresa recebeu em julho.

1. Insira *&quot;Pedidos de tendência em julho.&quot;*

   ![Solicitação de IA](/help/assets/ai-asst-prompt1.png)

2. O Assistente de IA agora reúne insights observando os dados na visualização de dados, incluindo as métricas e os componentes. Ele traduz o prompt para a(s) dimensão(ões), métrica(s) e intervalo de dados corretos.

   Como você pode ver, ele gerou automaticamente um gráfico de linha e uma tabela de forma livre mostrando pedidos para julho.

   ![Responder ao prompt - gráfico de linhas e tabela de forma livre](/help/assets/ai-asst-result.png)

### Exemplo 2

Em seguida, você deseja ver a comparação de receita por região.

1. Na janela do prompt, digite *&quot;Mostrar receita por região.&quot;*

2. O Assistente de IA entende de forma inteligente que, por &quot;região&quot;, você significa &quot;região do cliente&quot;. Ele produz um gráfico de barras que melhor mostra a receita por região:

   ![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Exemplo 3

Em seguida, além de entender a receita por região, você também deseja ver os dados para lucro por região. Em vez de ter que digitar novamente o último prompt, você pode solicitar que o Assistente de IA atualize a visualização e a tabela de forma livre mais recentes.

1. Na janela do prompt, digite *&quot;Adicionar lucro.&quot;*

2. O gráfico de **[!UICONTROL Barra]** ainda fornece a resposta mais concisa, mas a métrica de lucro foi adicionada como uma coluna na tabela de forma livre:

   ![Gráfico de barras](/help/assets/ai-asst-result4.png)

### Exemplo 4

Por fim, vamos analisar a receita por categoria de produto.

1. Na janela do prompt, digite *&quot;Proporção da receita por categoria do produto&quot;.*

2. Novamente, o Assistente de IA de análise de dados escolhe a visualização mais apropriada, neste caso a visualização **[!UICONTROL Rosca]**, para responder à pergunta.

   ![Rosca](/help/assets/ai-asst-result3.png)

## Exemplo de prompts de análise de dados

Estes são alguns exemplos de prompts comuns e quais visualizações o Assistente de IA usa para responder a esses prompts.

| Exemplo de prompt | Visualização esperada |
| --- | --- |
| Mostrar lucros em [Mês] | Linha<p>Por padrão, solicitar uma tendência ou métrica em um determinado intervalo de tempo retorna uma visualização de linha. |
| Pedidos de tendência em [Mês] | Linha |
| Mostrar receita por região em [Mês] | Barra |
| Parte da receita por categoria de produto | Rosca |
| Pedidos por dia da semana, de janeiro a maio | Barra |
| Mostrar pedidos por gênero, de março a junho | Barra |
| Qual é o lucro em SKUs de fevereiro a maio | Barra |
| Receita por nome de armazenamento em [Mês] | Barra |
| Quais foram meus 10 principais SKUs por lucro em [Mês]? | Barra |
| Proporção de compras por mês do ano | Rosca |
| Lucro total em [Mês] | Número do resumo<p>Solicitar o &quot;total&quot; de uma métrica em um determinado intervalo de tempo deve retornar uma visualização do Número do resumo. |


## Solicitação de práticas recomendadas

O Assistente de IA processa o contexto fornecido por cada prompt do usuário e tenta responder de forma inteligente com a visualização mais apropriada, bem como com os componentes em uma tabela de forma livre. No entanto, a resposta do Assistente de IA pode variar com base nas palavras e frases específicas usadas em um prompt, portanto, pequenas alterações de idioma podem levar a resultados diferentes. Veja como aproveitar ao máximo: <ul><li>Seja específico: inclua termos exatos (como &quot;vendas do mês passado na Califórnia&quot;) para restringir a resposta.</li><li>Usar métricas e filtros claros: adicionar métricas específicas (como &quot;Receita&quot;), dimensões (por exemplo, &quot;nome do site&quot;), filtros (como &quot;usuários do iPhone&quot;) e intervalos de datas (como &quot;últimos três meses&quot;) ajuda o Assistente do AI a se concentrar nos dados corretos.</li><li>Faça perguntas diretas: escreva perguntas diretamente, como &quot;Qual é a receita média por categoria de produto este ano?&quot; O facilita o fornecimento de insights claros e relevantes pelo Assistente de IA.</li></ul>

Consulte a tabela abaixo de termos de exemplo e frases que você pode usar nos prompts com o Assistente de IA de análise de dados no CJA, juntamente com os tipos de respostas que você pode esperar. Esses exemplos são projetados para ajudá-lo a se familiarizar com a forma como palavras ou estruturas específicas podem influenciar a saída do Assistente de IA, garantindo insights mais precisos e valiosos. Observe que o Assistente de IA usa IA gerativa, portanto, as visualizações ou os dados selecionados podem variar um pouco entre prompts semelhantes.

| Resultado desejado | Exemplo de termos e frases |
| --- | --- |
| Visualização do número do resumo | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>VS</li><li>Contraste</li><li>Semana a semana</li><li>Mês a mês</li><li>Trimestre a trimestre</li><li>Ano por ano</li></ul> |
| Visualização de rosca | <ul><li>Proporção</li><li>Compartilhamento de</li><li>Distribuição</li><li>Porcentagem</li><li>Contribuição</li><li>Parte</li><li>Partes</li></ul> |
| Visualização de linha | <ul><li>Tendência</li><li>[Métrica] em [Intervalo de tempo]</li></ul> |
| Visualização de barra | <ul><li>[Métrica] por [dimensão]</li></ul> |

## Expectativas de teste de Alpha e feedback solicitado

Depois de fazer cada pergunta, analise cuidadosamente a resposta fornecida pelo assistente. É crucial avaliar as visualizações geradas de forma abrangente antes de fornecer feedback. Pense no seguinte ao avaliar a resposta do Assistente de IA:

* Resposta do painel de chat ou modelo: avalie a resposta textual fornecida pelo Assistente. A resposta é apropriada dado o contexto de seu(s) prompt(s)?

* Visualização/gráfico: avalie a visualização. Essa é a visualização apropriada/esperada para sua pergunta ou você esperaria uma visualização diferente?

* Tabela de forma livre: avalie a tabela de forma livre. Os dados da tabela de forma livre estão corretos? Ele está detalhando os dados quando solicitado? Os filtros aplicados são os que você solicitou ou espera?

* Mensagem de erro / Fora de escopo: se uma mensagem de erro genérica for fornecida dizendo que a pergunta está fora de escopo, forneça feedback sobre se você acha que a mensagem fora de escopo é apropriada, dado o seu prompt. Seu prompt estava realmente no escopo?

**Para cada resposta, aplique uma miniatura para cima ou para baixo, com base na resposta**

Após a seleção de miniaturas para cima/para baixo, faça uma seleção para as caixas de comentários de multisseleção relevantes. Se quiser fornecer feedback adicional, adicione observações na caixa de texto aberta.

## Perguntas e contato

* Enviar perguntas e comentários no canal do Alpha Slack: #aep-cja-ai-assistant-testers ???


