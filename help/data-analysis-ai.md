---
description: Como fazer perguntas de análise de dados sobre a documentação do Customer Journey Analytics
title: Visualizar dados com o Data Insights Agent no Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: e19151a7b0c3ab2f9e532034d329896768ee095f
workflow-type: tm+mt
source-wordcount: '1972'
ht-degree: 90%

---

# Visualizar dados com o Data Insights Agent

>[!AVAILABILITY]
>
>A funcionalidade descrita neste artigo está disponível para todos os clientes elegíveis como parte de uma versão em fases a partir de 28 de maio de 2025 e pode não estar disponível ainda em seu ambiente. Essa observação será removida quando a funcionalidade estiver em disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Lançamentos de recursos do Customer Journey Analytics](/help/release-notes/releases.md).

>[!AVAILABILITY]
>
>O Data Insights Agent está disponível para clientes qualificados por um período limitado. O acesso ao Data Insights Agent terminará em 30 de novembro de 2025. Para continuar usando o Data Insights Agent sem interrupção, entre em contato com o representante de conta da Adobe para saber mais sobre como licenciar o Data Insights Agent.

O Data Insights Agent, acessível pelo Assistente de IA no Customer Journey Analytics, é um agente de conversação de IA generativa que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e seus dados reais.

Usar o Data Insights Agent para responder a perguntas centradas em dados no Analysis Workspace pode economizar inúmeras horas gastas com a criação manual de visualizações e a familiarização com componentes de visualização de dados.

![Data Insights Agent no Assistente de IA](assets/cja-ai-asst-da.gif)

## Comparação entre recursos dentro e fora do escopo

| Recurso | No escopo | Fora do escopo |
| --- | --- | --- |
| **Tipos de visualização** | <ul><li>Linha</li><li>Várias linhas</li><li>Tabela de forma livre</li><li>Barra</li><li>Rosca</li><li>Número do resumo</li></ul> | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área e área empilhada</li><li>Barra empilhada</li><li>Marcador</li><li>Combinado</li><li>Histograma</li><li>Barra horizontal e barra horizontal empilhada</li><li>Resumo da métrica principal</li><li>Dispersão</li><li>Mudança de resumo</li><li>Texto</li><li>Mapa de árvore</li><li>Venn</li><li>Análise guiada: Crescimento ativo, Tendências de conversão, Envolvimento, Impacto na primeira utilização, Frequência, Funil, Crescimento líquido, Impacto na versão, Retenção, Linha do tempo, Tendências</li></ul> |
| **Ações do espaço de trabalho e recursos do agente** | <ul><li>Criar e atualizar visualizações<p>Gera uma tabela de forma livre e uma visualização associada (como uma linha, barra, rosca e assim por diante).<p>Por exemplo, *Qual foi o lucro dos SKUs de fevereiro a maio?*</p></li><li>Fazer perguntas de acompanhamento<p>Responder a um prompt no contexto de qualquer prompt anterior. Por exemplo:</p> <ul><li>Prompt 1: *Eventos de tendência de março.*</li><li>Prompt 2: *Mostrar os dados de março a abril*</li></ul> </li><li>Detecção de prompt fora do escopo<p>Se você enviar um prompt que está fora do escopo, como *Exportar este projeto*, o Data Insights Agent responderá informando que a pergunta está fora do escopo.</p></li></ul> | <ul><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Gerenciar preferências do usuário</li><li>Gerenciar visualização de dados</li><li>Aplicativo de painéis do Analytics</li><li>Atribuição</li><li>Resumo ou resposta em linha<p>O Data Insights Agent não pode responder em linha no chat com uma resposta resumida de um prompt do usuário. Exemplos de prompts fora do escopo são: *Faça um resumo dos insights do meu último prompt* e *Resuma os destaques da visualização de linha.*</p></li></ul> |
| **Esclarecimento de questões** | Se você fizer uma pergunta que não tenha contexto suficiente para o Data Insights Agent responder, ou que seja muito genérica, o Data Insights Agent responderá com uma pergunta esclarecedora ou com opções sugeridas. <p>As seguintes perguntas de esclarecimento são exemplos de perguntas relacionadas a componentes:</p><ul><li>Métrica: *Qual métrica de “receita” você quis dizer?*</li><li>Dimension: *Em qual das “regiões” abaixo você deseja se concentrar?*</li><li>Segmento: *Que segmento de “Conta” você deseja aplicar?*</li><li>Intervalo de datas: *Por “último mês”, você quis dizer o último mês completo ou os últimos 30 dias?*</li></ul><p>A pergunta esclarecedora a seguir é um exemplo de uma pergunta relacionada a itens de dimensão:</p> <ul><li>Que “nome da loja” você quis dizer? (Por exemplo, Loja nº 5274, Loja nº 2949 e assim por diante.)</li></ul> | As perguntas de esclarecimento estão limitadas a componentes e itens de dimensão. O Data Insights Agent não pode esclarecer aspectos como visualizações de dados, visualizações, granularidade de dados, comparação e escopo. Quando não for possível usar perguntas de esclarecimento, o agente responderá por padrão com o que você provavelmente esteja solicitando. Se retornar uma visualização ou granularidade de dados inesperada, você poderá fazer uma pergunta complementar ou ajustar a visualização e os dados. |
| **Verificabilidade e correção de dados** | A verificabilidade e a correção de dados podem ser confirmadas visualizando a tabela de forma livre gerada e a visualização de dados. <p>Por exemplo, se você solicitar ao Data Insights Agent para *Analisar tendências de pedidos no mês passado*, será posível confirmar se a métrica correta (“pedidos”) e o intervalo de datas (“mês passado”) foram selecionados no painel recém-gerado, na visualização de dados e na tabela de forma livre. | O Data Insights Agent não responde informando quais componentes ou visualizações foram adicionados.</p> |
| **Mecanismos de feedback** | <ul><li>Polegar para cima</li><li>Polegar para baixo</li><li>Sinalizador</li></ul> |  |


## Gerenciar acesso ao Data Insights Agent

Os seguintes parâmetros regulam o acesso ao Data Insights Agent no Customer Journey Analytics:

* **Acesso à solução**: o Data Insights Agent estará disponível para todos os clientes da Customer Journey Analytics como parte de um programa de acesso limitado até 30 de novembro de 2025. Não está disponível no Adobe Analytics.

* **Acesso contratual**: se você não conseguir usar o Data Insights Agent no Assistente de IA, entre em contato com o administrador da organização ou com a equipe de contas da Adobe. Antes de poder usar o Data Insights Agent na sua organização, você deve concordar com determinados termos legais relacionados à IA generativa.

* **Permissões**: as permissões necessárias devem ser concedidas no [!UICONTROL Adobe Admin Console] para que os usuários possam acessar o Data Insights Agent.

  Para conceder permissões, um [administrador de perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) deve concluir as seguintes etapas no [!UICONTROL Admin Console]:
   1. No **[!UICONTROL Admin Console]**, selecione a guia **[!UICONTROL Produtos]** para exibir a página **[!UICONTROL Todos os produtos e serviços]**.
   1. Selecione **[!UICONTROL Customer Journey Analytics]**.
   1. Na guia **[!UICONTROL Perfis de produto]**, selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: conhecimento do produto].
   1. No perfil específico do produto, selecione a guia **[!UICONTROL Permissões]**.

      ![Guia Permissões no Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Na linha **[!UICONTROL Ferramentas de relatórios]** da tabela fornecida, selecione o ícone de edição ![Editar](/help/assets/icons/Edit.svg).
   1. Role até a opção ou pesquise por **[!UICONTROL Assistente de IA: conhecimento do produto]** e selecione o ícone de adição ![AddCircle](/help/assets/icons/AddCircle.svg) ao lado dessa permissão.

      A permissão **[!UICONTROL Assistente de IA: conhecimento do produto]** é adicionada à coluna **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicione a permissão](assets/ai-assistant-permissions.png).

   1. Selecione a guia **[!UICONTROL Ferramentas de visualização de dados]** e clique no ícone de adição ![AddCircle](/help/assets/icons/AddCircle.svg) ao lado da permissão **[!UICONTROL Data Insights Agent]**.

      A permissão **[!UICONTROL Data Insights Agent]** é adicionada à coluna **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicione a permissão](assets/ai-assistant-permissions-dataviewtools.png).

   1. Selecione a guia **[!UICONTROL Visualizações de dados]** para escolher as visualizações de dados que você deseja habilitar para o Data Insights Agent.

      >[!IMPORTANT]
      >
      >Considere o seguinte ao ativar as visualizações de dados:
      >* É possível habilitar no máximo 50 visualizações de dados por organização IMS. Se você habilitar mais de 50 visualizações de dados em todos os perfis de produto para uma determinada organização, a Data Insights Agent usará as 50 visualizações de dados mais usadas.
      >* O Data Insights Agent pode fazer referência às visualizações de dados incluídas em algum momento do mesmo dia em que você as habilita no Admin Console.

   1. Procure ou role a tela até as visualizações de dados que deseja habilitar e selecione o ícone de adição ![AddCircle](/help/assets/icons/AddCircle.svg) ao lado do nome de cada visualização de dados.

      Cada visualização de dados adicionada está visível na coluna **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicione a permissão](assets/ai-assistant-permissions-dataviews.png).

   1. Clique em **[!UICONTROL Salvar]** para salvar as permissões.

  Para obter informações adicionais sobre o controle de acesso, consulte [Controle de acesso](/help/technotes/access-control.md#access-control).

## Acessar o Data Insights Agent no Assistente de IA

1. Acesse [experience.adobe.com](https://experience.adobe.com/) e faça logon com a Adobe ID.

2. Selecione **Customer Journey Analytics** na página inicial da Experience Cloud.

3. Selecione **[!UICONTROL Projeto em branco]** no banner na parte superior da página de projetos para abrir um novo projeto em branco.

4. Verifique se a visualização de dados selecionada para o painel é uma visualização de dados que foi habilitada para uso com o Data Insights Agent, conforme descrito em [Gerenciar acesso ao Data Insights Agent no Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Selecione o ícone de chat do Assistente de IA na área superior direita da página.

   Se você não vir o ícone de chat, entre em contato com o(a) admin para solicitar que os seguintes recursos sejam habilitados no Admin Console:

   * Ferramentas de relatórios: **[!UICONTROL Assistente de IA: conhecimento do produto]**

   * Ferramentas de visualização de dados: **[!UICONTROL Data Insights Agent]**

   Para obter detalhes adicionais, consulte [Gerenciar acesso ao Data Insights Agent no Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![Ícone do Assistente de IA](/help/assets/ai-asst-icon.png)

6. Na caixa de diálogo **[!UICONTROL Perguntar sobre o Customer Journey Analytics]** na parte inferior da página, faça uma pergunta sobre visualizações de dados usando o Data Insights Agent.

   Para obter mais informações, veja os exemplos a seguir.

### Exemplo 1

Por exemplo, digamos que você tenha interesse nos pedidos que sua empresa recebeu em julho.

**Prompt:** digite *“Tendências de pedidos em julho”.*

![Prompt de IA](/help/assets/ai-asst-prompt1.png)

**Resposta:** o Data Insights Agent coleta informações verificando os dados na visualização de dados, incluindo as métricas e os componentes. Ele converte o prompt nas dimensões e métricas certas no intervalo de dados.

Como pode ver, ele gerou automaticamente um gráfico de linhas e uma tabela de forma livre para mostrar os pedidos de julho.

![Resposta ao prompt: gráfico de linhas e tabela de forma livre](/help/assets/ai-asst-result.png)

### Exemplo 2

Em seguida, digamos que você deseja ver a comparação de receita por região.

**Prompt:** na janela de prompt, digite *“Mostrar receita por região”.*

**Resposta:** o Data Insights Agent entende de forma inteligente que, por “região”, você quer dizer “região do cliente”. Ele produz um gráfico de barras que exibe detalhes sobre a receita por região:

![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Exemplo 3

Em seguida, além de entender a receita por região, digamos que você também deseja ver os dados de lucro por região. Em vez de repetir o prompt anterior, é possível solicitar que o Data Insights Agent atualize a visualização mais recente e a tabela de forma livre.

**Prompt:** na janela de prompt, digite *“Adicionar lucro”.*

**Resposta:** o gráfico de **[!UICONTROL Barra]** ainda fornece a resposta mais concisa, mas a métrica de lucro é adicionada como uma coluna na tabela de forma livre:

![Gráfico de barras](/help/assets/ai-asst-result4.png)

### Exemplo 4

Por fim, vamos analisar a receita por categoria de produto.

**Prompt:** na janela do prompt, digite *“Proporção de receita por categoria de produto.”*

**Resposta:** novamente, o Data Insights Agent escolhe a visualização mais apropriada (neste caso, a visualização em **[!UICONTROL Rosca]**) para responder à pergunta.

![Rosca](/help/assets/ai-asst-result3.png)

## Exemplo de prompts de visualização de dados

Veja a seguir alguns exemplos de prompts comuns e as visualizações usadas pelo Data Insights Agent para responder a esses prompts.

| Exemplo de prompt | Visualização esperada |
| --- | --- |
| Mostrar lucros em [Mês] | Linha<p>Solicitar uma tendência ou métrica dentro de um determinado período retorna, por padrão, uma visualização de linha. |
| Tendência de pedidos em [Mês] | Linha |
| Mostrar receita por região em [Mês] | Barra |
| Parte da receita por categoria de produto | Rosca |
| Pedidos por dia da semana, de janeiro a maio | Barra |
| Mostrar pedidos por gênero, de março a junho | Barra |
| Qual é o lucro em SKUs de fevereiro a maio | Barra |
| Receita por nome de loja em [Mês] | Barra |
| Quais foram as 10 principais SKUs por lucro em [Mês]? | Barra |
| Proporção de compras por mês do ano | Rosca |
| Lucro total em [Mês] | Número do resumo<p>Solicitar o “total” de uma métrica em um determinado período deve retornar uma visualização numérica de resumo. |


## Práticas recomendadas ao gerar prompts

O Data Insights Agent processa o contexto fornecido por cada prompt do usuário e tenta responder de forma inteligente com a visualização e os componentes mais apropriados em uma tabela de forma livre.

As respostas podem variar com base nas palavras e frases específicas usadas no prompt, e pequenas alterações no idioma podem gerar resultados diferentes.

Para obter os melhores resultados, considere as seguintes diretrizes:

* **Seja específico(a):** Inclua termos exatos para restringir a resposta. Este é um exemplo de um prompt específico: “Vendas do mês passado na Califórnia”

* **Use métricas, dimensões e segmentos claros:** adicionar métricas (como “Receita”), dimensões (como “nome do site”), segmentos (como “usuários de iPhone”) e intervalos de datas (como “últimos três meses”) específicos ajuda o Data Insights Agent a se concentrar nos dados corretos.

* **Faça perguntas diretas:** formular perguntas diretas ajuda o Data Insights Agent a fornecer insights claros e relevantes. O exemplo a seguir mostra uma pergunta direta em um prompt: “Qual é a receita média por categoria de produto neste ano?”

Analise a tabela a seguir de termos e frases de exemplo que você pode usar em prompts com o Data Insights Agent, juntamente com os tipos de respostas que você pode esperar.

Esses exemplos foram elaborados para ajudar você a se familiarizar com a forma como palavras ou estruturas específicas podem influenciar os resultados do Data Insight Agent, garantindo insights mais precisos e valiosos. O Data Insights Agent usa IA generativa, de modo que as visualizações ou os dados selecionados podem variar um pouco entre prompts semelhantes.

| Resultado desejado | Exemplo de termos e frases |
| --- | --- |
| Visualização do número resumido | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>com</li><li>Contraste</li><li>Semana a semana</li><li>Mês a mês</li><li>Trimestre a trimestre</li><li>Ano a ano</li></ul> |
| Visualização de rosca | <ul><li>Proporção</li><li>Parcela de</li><li>Distribuição</li><li>Porcentagem</li><li>Contribuição</li><li>Parte</li><li>Partes</li></ul> |
| Visualização de linha | <ul><li>Tendência</li><li>[Métrica] em [Intervalo de tempo]</li></ul> |
| Visualização de barra | <ul><li>[Métrica] por [Dimensão]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->

<!--
## Configuration best practices

Below are best practices for your Customer Journey Analytics configuration (data view, calculated metrics, segments, and more) to ensure the Data Insights Agent can locate the correct components and return cleaner answers without having you to prompt for additional information.

* **Balance what components you need**. Do not add all the fields of your datasets as metrics or dimension components to your data view. Especially, those you most certainly will not use in your analysis. On the other hand, do not strictly limit yourself only to the fields you anticipate you require for your analysis. A too limited data view restricts the flexibility in your analysis and the Data Insight's agent functionality.
* **Always use friendly display names**. Ensure that all fields you define in your data view, either as a metrics or dimension component, do have a friendly component name. The process of renaming fields with a friendly name is especially relevant for fields from Adobe Analytics source connector datasets. These fields often have non-friendly unidentifiable names like `eVar41`, or `prop25`.
* **Use distinctive names**. Distinctive names are especially relevant when you use a field both as a metric and a dimension component in your data view. Or when you use a field in multiple components, each with different component settings. 
* **Use a component naming convention**. You can use a component naming convention to group components. For example, **[!UICONTROL Orders | Product]** and  **[!UICONTROL Orders | Customer]** to distinguish between different order metrics that might exist in your data.
* **Use the Data Dictionary**. Add description and other relevant data for components in the Data Dictionary. The Data Insight agent currently does not use description and tags. but might use Data Dictionary description and tags in the future. 
* **Use approved calculated metrics**. Agree on a process to use only approved calculated metrics as components in your data view, and avoid using experimental calculated metrics.
* **Share required segments**. Ensure you share segments and make segments visible that are required for Data Insights agent prompts.
* **Standardize on component names across data views**. If you use the same fields as a component in multiple data views, ensure you use a single friendly name and a single identifier for that component. A single name and identifier allows the Data Insights agent to switch data views without losing context.

>[!MORELIKETHIS]
>
>[Component settings](/help/data-views/component-settings/overview.md)
>[Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md)
>[Approve calculated metric](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>[Share segments](/help/components/segments/seg-share.md)
>

-->