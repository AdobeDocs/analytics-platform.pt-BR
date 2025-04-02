---
description: Como fazer perguntas sobre a análise de dados da documentação do Customer Journey Analytics
title: Visualizar dados com o Agente de insights de dados na Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: dff6355714f4e58917ccd995662e4fbae34ec69c
workflow-type: tm+mt
source-wordcount: '1873'
ht-degree: 3%

---

# Visualizar dados com o Agente de insights de dados na Customer Journey Analytics

O Agente de insights de dados, parte do Assistente de IA no Customer Journey Analytics, é um agente de conversação de IA generativo que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e usando seus dados reais.

Usar o Agente de insights de dados para responder perguntas centradas em dados no Analysis Workspace pode economizar inúmeras horas que, de outra forma, você poderia gastar criando visualizações manualmente no Analysis Workspace e se familiarizando com seus componentes de visualização de dados.

![Agente do Data Insights no Assistente de IA](assets/cja-ai-asst-da.gif)

## Recursos dentro e fora do escopo do Beta

### Recursos do Beta dentro do escopo

| Recurso compatível | Descrição |
| --- | --- |
| **Criar e atualizar visualizações** | Gera uma tabela de forma livre e uma visualização associada (como uma linha, barra, rosca e assim por diante).<p>Exemplo: *Qual é o lucro entre SKUs de fevereiro a maio?* |
| **Tipos de visualização com suporte** | <ul><li>Linha</li><li>Várias linhas</li><li>Tabela de forma livre</li><li>Barra</li><li>Rosca</li><li>Número do resumo</li></ul> |
| **Detecção de prompt fora do escopo** | Se você enviar um prompt que está fora do escopo, como &quot;exportar este projeto&quot;, o Agente de Insights de Dados responderá informando que a pergunta está fora do escopo. |
| **Esclarecimento de questões** | Se você fizer uma pergunta que não tenha contexto suficiente para o Agente de insights de dados responder, ou que seja muito genérica, o Agente de insights de dados responderá com uma pergunta esclarecedora ou com opções sugeridas. Exemplos: <p>**Componentes**<ul><li>Métrica: *Qual métrica de &quot;receita&quot; você quis dizer?*</li><li>Dimension: *Em qual das &quot;regiões&quot; abaixo você deseja se concentrar?*</li><li>Filtro: *Qual filtro de &quot;Conta&quot; você deseja aplicar?*</li><li>Intervalo de datas: *Por &quot;último mês&quot;, você quis dizer o último mês completo ou os últimos 30 dias?*</li></ul>**Itens do Dimension**: qual &quot;nome da loja&quot; você quis dizer? (Por exemplo, Armazenar #5274, Armazenar #2949 e assim por diante.) |
| **Voltas múltiplas** | O Agente de insights de dados responde a um prompt com o contexto de qualquer prompt anterior, permitindo que os usuários atualizem as visualizações e façam perguntas de acompanhamento. Exemplo: <ul><li>Prompt 1: *Eventos de tendência de março.*</li><li>Prompt 2: *Mostrar os dados de março a abril*</li></ul> |
| **Verificabilidade** | A verificabilidade e a correção dos dados podem ser confirmadas por meio da tabela de forma livre gerada e da visualização de dados. Por exemplo, se um usuário solicitar *Pedidos de tendência no último mês*, você poderá confirmar se a métrica (&quot;pedidos&quot;) e o intervalo de datas (&quot;último mês&quot;) corretos foram selecionados no painel recém-gerado, na visualização de dados e na tabela de forma livre. |
| **Feedback** | <ul><li>Polegar para cima</li><li>Polegar para baixo</li><li>Sinalizador</li></ul> |

### Recursos do Beta fora do escopo

| Recurso incompatível | Descrição |
| --- | --- |
| **Resumo ou resposta embutida** | O agente do Data Insights não pode responder em linha no painel de chat com uma resposta resumida de um prompt do usuário. Exemplo de prompts fora do escopo:<ul><li>*Forneça um resumo dos insights do meu último prompt.*</li><li>*Resuma os destaques da visualização de linha.*</li></ul> |
| **Esclarecimento de questões** | As perguntas de esclarecimento estão limitadas a componentes e itens de dimensão. O Agente de insights de dados não pode esclarecer aspectos como visualizações de dados, visualizações, granularidade de dados, comparação e escopo. Quando o esclarecimento de questões não puder ser usado, o Agente assumirá como padrão o que você provavelmente está solicitando. Se retornar uma visualização ou granularidade de dados inesperada, você poderá usar o recurso de atualização em várias voltas para ajustar a visualização e os dados. |
| **Ações/Recursos do Workspace** | O Agente de insights de dados não pode realizar ações para um usuário no Workspace além de criar e atualizar visualizações. Por exemplo, ela não pode executar um dos seguintes procedimentos:<ul><li>Botões da interface de ação contextual (adicionar ao gráfico, novo painel, nova tabela)</li><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Gerenciar preferências do usuário</li><li>Preparar</li><li>Gerenciar visualização de dados</li><li>aplicativo Painéis do Analytics</li><li>Atribuição</li></ul> |
| **Tipos de visualização sem suporte** | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área, Área empilhada</li><li>Barra empilhada</li><li>Marcador</li><li>Combo</li><li>Histograma</li><li>Barra horizontal, Barra horizontal empilhada</li><li>Resumo da métrica principal</li><li>Dispersão</li><li>Mudança de resumo</li><li>Texto</li><li>Mapa de árvore</li><li>Venn</li></ul> |

## Gerenciar acesso ao Agente de insights de dados na Customer Journey Analytics

Os parâmetros a seguir controlam o acesso ao Agente de insights de dados na Customer Journey Analytics:

* **Acesso à solução**: o Agente de Insights de Dados está disponível para clientes da Customer Journey Analytics Prime e da Ultimate. Não está disponível no Adobe Analytics.

* **Acesso contratual**: se você não conseguir usar o Agente de Insights de Dados no Assistente de IA, entre em contato com o administrador da sua organização ou com o Representante de Conta da Adobe. Antes de sua organização poder usar o Agente de insights de dados, você deve concordar com determinados termos legais relacionados à GenAI.

* **Permissões**: no [!UICONTROL Adobe Admin Console], a permissão [!UICONTROL Ferramentas de Relatório] **[!UICONTROL Assistente de IA: Visualização de dados]** determina o acesso a esta ferramenta. Um [administrador do perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) precisa seguir estas etapas no [!UICONTROL Admin Console]:
   1. Navegue até **[!UICONTROL Admin Console]** > **[!UICONTROL Produtos e serviços]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfis de Produtos]**
   1. Selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: Conhecimento do Produto].
   1. No perfil de produto específico, selecione **[!UICONTROL Permissões]**.
   1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar as **[!UICONTROL Ferramentas de Relatório]**.
   1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) para adicionar o **Assistente de IA: Visualização de dados** a **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicionar permissão](assets/ai-assistant-permissions.png).

   1. Selecione **[!UICONTROL Salvar]** para salvar as permissões.

Consulte [Controle de acesso](/help/technotes/access-control.md#access-control) para obter mais informações.

## Acessar o Agente de insights de dados no Assistente de IA

1. Acesse [experience.adobe.com](https://experience.adobe.com/) e faça logon com sua Adobe ID.

2. Selecione **Customer Journey Analytics** na página inicial da Experience Cloud.

3. Selecione **[!UICONTROL Projeto em branco]** no banner na parte superior da página de projetos para abrir um novo projeto em branco.

4. Verifique se a visualização de dados selecionada para o painel é a mesma visualização de dados que foi habilitada para uso com o Agente de insights de dados para teste do Beta.

   Se não tiver certeza, entre em contato com o canal do Beta Slack.

5. Selecione o ícone de chat do Assistente do AI na área superior direita da página.

   Se você não vir o ícone de bate-papo, entre em contato com o administrador para que ele possa habilitar os seguintes recursos no Admin Console:

   * **[!UICONTROL Assistente de IA: Conhecimento do Produto]**

   * **[!UICONTROL Assistente de IA: Análise de Dados]**

   Para obter detalhes adicionais, os administradores podem ver [estas instruções](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![Ícone do Assistente de IA](/help/assets/ai-asst-icon.png)

6. Na caixa de diálogo **[!UICONTROL Perguntar sobre o Customer Journey Analytics]**, na parte inferior da página, faça uma pergunta sobre visualização de dados usando o Agente de Insights de Dados.

   Para obter mais informações, consulte os exemplos a seguir.

### Exemplo 1

Por exemplo, digamos que você esteja interessado nos pedidos que sua empresa recebeu em julho.

**Aviso:** Insira *&quot;Pedidos de tendência em julho.&quot;*

![Solicitação de IA](/help/assets/ai-asst-prompt1.png)

**Resposta:** o Agente de Insights de Dados coleta insights verificando os dados na visualização de dados, incluindo as métricas e os componentes. Ele traduz o prompt para as dimensões e métricas certas no intervalo de dados.

Como você pode ver, ele gerou automaticamente um gráfico de linhas e uma tabela de forma livre para mostrar os pedidos de julho.

![Responder ao prompt - gráfico de linhas e tabela de forma livre](/help/assets/ai-asst-result.png)

### Exemplo 2

Em seguida, você deseja ver a comparação de receita por região.

**Prompt:** Na janela de prompt, digite *&quot;Mostrar receita por região.&quot;*

**Resposta:** O Agente do Data Insights entende de forma inteligente que por &quot;região&quot;, você quer dizer &quot;região do cliente&quot;. Ele produz um gráfico de barras que melhor mostra a receita por região:

![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Exemplo 3

Em seguida, além de entender a receita por região, você também deseja ver os dados para lucro por região. Em vez de repetir o prompt anterior, você pode solicitar que o Agente de insights de dados atualize a visualização e a tabela de forma livre mais recentes.

**Prompt:** Na janela de prompt, digite *&quot;Adicionar lucro.&quot;*

**Resposta:** O gráfico de **[!UICONTROL Barra]** ainda fornece a resposta mais concisa, mas a métrica de lucro foi adicionada como uma coluna na tabela de forma livre:

![Gráfico de barras](/help/assets/ai-asst-result4.png)

### Exemplo 4

Por fim, vamos analisar a receita por categoria de produto.

**Prompt:** Na janela do prompt, digite *&quot;Proporção da receita por categoria do produto.&quot;*

**Resposta:** Novamente, o Agente de Insights de Dados escolhe a visualização mais apropriada, neste caso a visualização **[!UICONTROL Rosca]**, para responder à pergunta.

![Rosca](/help/assets/ai-asst-result3.png)

## Exemplo de prompts de visualização de dados

A seguir estão alguns exemplos de prompts comuns e as visualizações usadas pelo Agente de Insights de Dados para responder a esses prompts.

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

O Agente de insights de dados processa o contexto fornecido por cada prompt do usuário e tenta responder de forma inteligente com a visualização e os componentes mais apropriados em uma tabela de forma livre.

As respostas podem variar com base nas palavras e frases específicas usadas no prompt, e pequenas alterações no idioma podem levar a resultados diferentes.

Para obter os melhores resultados, considere as seguintes diretrizes:

* Seja específico: inclua termos exatos para restringir a resposta. Veja a seguir um exemplo de um prompt específico: &quot;Vendas do mês passado na Califórnia&quot;

* Usar métricas e filtros simples: adicionar métricas específicas (como &quot;Receita&quot;), dimensões (como &quot;nome do site&quot;), filtros (como &quot;usuários do iPhone&quot;) e intervalos de datas (como &quot;últimos três meses&quot;) ajuda o Agente de insights de dados a se concentrar nos dados corretos.

* Fazer perguntas diretas: a formulação direta de perguntas facilita que o Agente de insights de dados forneça insights claros e relevantes. Veja a seguir um exemplo de como fazer uma pergunta direta em um prompt: &quot;Qual é a receita média por categoria de produto este ano?&quot;

Analise a tabela a seguir de termos de exemplo e frases que você pode usar em prompts com o Agente de Insights de Dados, juntamente com os tipos de respostas que você pode esperar.

Esses exemplos foram projetados para ajudar você a se familiarizar com a forma como palavras ou estruturas específicas podem influenciar a saída do Agente de insights de dados, garantindo insights mais precisos e valiosos. O Agente de insights de dados usa IA generativa, de modo que as visualizações ou os dados selecionados podem variar um pouco entre prompts semelhantes.

| Resultado desejado | Exemplo de termos e frases |
| --- | --- |
| Visualização do número do resumo | <ul><li>Total</li></ul> |
| Comparar componentes | <ul><li>Comparar</li><li>VS</li><li>Contraste</li><li>Semana a semana</li><li>Mês a mês</li><li>Trimestre a trimestre</li><li>Ano por ano</li></ul> |
| Visualização de rosca | <ul><li>Proporção</li><li>Compartilhamento de</li><li>Distribuição</li><li>Porcentagem</li><li>Contribuição</li><li>Parte</li><li>Partes</li></ul> |
| Visualização de linha | <ul><li>Tendência</li><li>[Métrica] em [Intervalo de tempo]</li></ul> |
| Visualização de barra | <ul><li>[Métrica] de [Dimension]</li></ul> |

## Expectativas de teste do Beta e feedback solicitado

Depois de fazer cada pergunta, analise cuidadosamente a resposta fornecida pelo assistente. É crucial avaliar as visualizações geradas de forma abrangente antes de fornecer feedback.

Considere o seguinte ao avaliar uma resposta do Agente de insights de dados:

* Resposta do painel de chat ou modelo: avalie a resposta textual fornecida. A resposta é apropriada de acordo com o contexto do seu prompt?

* Visualização/gráfico: avalie a visualização. Essa é a visualização apropriada ou esperada para sua pergunta, ou você esperaria uma visualização diferente?

* Tabela de forma livre: avalie a tabela de forma livre. Os dados da tabela de forma livre estão corretos? Ele está detalhando os dados quando solicitado? Os filtros aplicados são os que você solicitou ou espera?

* Mensagem de erro / Fora de escopo: se uma mensagem de erro genérica for fornecida declarando que a pergunta está fora do escopo, forneça feedback sobre se você acha que a mensagem fora do escopo é apropriada, dado o seu prompt. O seu prompt estava realmente no escopo?

**Para cada resposta, aplique uma miniatura para cima ou para baixo, com base na resposta.**

Após a seleção de miniaturas para cima ou miniaturas para baixo, faça uma seleção para as caixas de comentários de multisseleção relevantes. Se quiser fornecer feedback adicional, adicione observações na caixa de texto aberta.

## Perguntas e contato

* Envie perguntas e comentários no canal do Beta Slack: #data-insights-agent-in-cja-beta
