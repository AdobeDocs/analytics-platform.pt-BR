---
description: Como fazer perguntas sobre a análise de dados da documentação do Customer Journey Analytics
title: Assistente de IA de análise de dados no Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e18d8facbd54ae65d158ce2c72f47709ef988f8f
workflow-type: tm+mt
source-wordcount: '1422'
ht-degree: 4%

---


# Assistente de IA de análise de dados em Customer Journey Analytics - Alpha

O Assistente de IA de análise de dados é um agente de conversação inteligente e sensível ao contexto que pode ajudá-lo a responder com mais rapidez e eficiência às perguntas que você possa ter sobre seus dados do Analysis Workspace no Customer Journey Analytics.

O Assistente verifica todos os dados em uma visualização de dados, incluindo os diferentes tipos de métricas e componentes, e traduz o prompt para a dimensão, a métrica e o intervalo de datas corretos para essa análise. Em vez de precisar se familiarizar com os componentes da visualização de dados e, em seguida, arrastar e soltar esses componentes na melhor combinação para responder à sua pergunta, você pode simplesmente digitar a pergunta no Assistente de IA.

## Recursos dentro e fora do escopo da versão do Alpha

### Recursos dentro do escopo

| Recurso suportado | Descrição |
| --- | --- |
| **Criar e atualizar visualizações** | Gera uma tabela de forma livre e uma visualização associada (por exemplo, linha, barra, rosca etc.).<p>Exemplo: *Qual é o lucro entre SKUs de fevereiro a maio?* |
| **Tipos de visualização com suporte** | <ul><li>Linha</li><li>Várias linhas</li><li>Forma livre</li><li>Barra</li><li>Rosca</li><li>Número do resumo</li></ul> |
| **Detecção de prompt fora do escopo** | Se você enviar um prompt que está fora do escopo, como &quot;exportar este projeto&quot;, o Assistente responderá informando que a pergunta está fora do escopo. |
| **Esclarecimento de questões** | Se você fizer uma pergunta que não tenha contexto suficiente para o Assistente de IA responder, ou que seja muito genérica, o Assistente de IA responderá com uma pergunta esclarecedora e/ou com opções sugeridas. Exemplos: <p>**Componentes**<ul><li>Métrica: *Qual métrica de &quot;receita&quot; você quis dizer?*</li><li>Dimension: *Em qual das &quot;regiões&quot; abaixo você deseja se concentrar?*</li><li>Filtro: *Qual filtro de &quot;Conta&quot; você deseja aplicar?*</li><li>Intervalo de datas: *Por &quot;último mês&quot;, você quis dizer o último mês completo ou os últimos 30 dias?*</li></ul>**itens de Dimension**: qual &quot;nome da loja&quot; você quis dizer? (por exemplo, Armazenamento #5274, Armazenamento #2949 etc.) |
| **Voltas múltiplas** | O Assistente de IA responde a um prompt com o contexto do(s) prompt(s) anterior(es), permitindo que os usuários atualizem as visualizações e façam perguntas de acompanhamento. Exemplo: *Mostrar os dados de março a abril.* |
| **Feedback** | <ul><li>Polegar para cima</li><li>Polegar para baixo</li><li>Sinalizador</li></ul> |

### Recursos fora do escopo

| Recurso não suportado | Descrição |
| --- | --- |
| **Resumo ou resposta embutida** | O Assistente de IA não pode responder em linha no painel de chat com uma resposta resumida de um prompt do usuário.Exemplo de prompts fora do escopo:<ul><li>*Forneça um resumo dos insights do meu último prompt.*</li><li>*Resuma os destaques da visualização de linha.*</li></ul> |
| **Esclarecimento de questões** | As perguntas de esclarecimento estão limitadas a componentes e itens de dimensão. O Assistente de IA não pode esclarecer visualizações de dados, visualizações, granularidade de dados, comparação, escopo etc. Sem esclarecer dúvidas, o Assistente assume como padrão o que você provavelmente está solicitando. Se retornar uma visualização ou granularidade de dados inesperada, você poderá usar o recurso de várias rodadas/atualização para ajustar a visualização e os dados. |
| **Ações/Recursos do Workspace** | O Assistente de IA não pode realizar ações para um usuário no Workspace além de criar e atualizar visualizações. Por exemplo, ela não pode executar nenhum dos seguintes procedimentos:<ul><li>Botões da interface de ação contextual (adicionar ao gráfico, novo painel, nova tabela)</li><li>Compartilhar</li><li>Exportar</li><li>Baixar</li><li>Gerenciar preferências do usuário</li><li>Preparar</li><li>Gerenciar visualização de dados</li><li>aplicativo Painéis do Analytics</li><li>Atribuição</li></ul> |
| **Tipos de visualização sem suporte** | <ul><li>Fluxo</li><li>Fallout</li><li>Tabela de coorte</li><li>Área, Área empilhada</li><li>Barra empilhada</li><li>Marcador</li><li>Combo</li><li>Histograma</li><li>Barra horizontal, Barra horizontal empilhada</li><li>Resumo da métrica principal</li><li>Dispersão</li><li>Mudança de resumo</li><li>Texto</li><li>Mapas de árvore</li><li>Venn</li></ul> |
| **Explicabilidade e Verificabilidade** | Descrição ou citação transparente sobre como o Assistente de IA gerou uma resposta e fornece uma maneira de confirmar se a resposta está correta. |

## Acesso a recursos na interface do usuário do Customer Journey Analytics

[Precisamos mesmo desta seção para o Alpha?]

Os parâmetros a seguir controlam o acesso ao recurso Assistente da IA de análise de dados:

* **Acesso à solução**: o Assistente de IA de análise de dados está disponível para clientes do Customer Journey Analytics Prime e Ultimate. Não está disponível no Adobe Analytics.

Ele também está disponível em aplicativos Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP e Experience Platform adicionais.

* **Acesso contratual**: se você não conseguir usar o Assistente de IA, entre em contato com o administrador da sua organização ou com o Representante de Conta do Adobe. Antes de sua organização poder usar o Assistente de IA de análise de dados, você deve concordar com determinados termos legais relacionados à GenAI.

* **Permissões**: no [!UICONTROL Adobe Admin Console], a permissão [!UICONTROL Ferramentas de Relatório] **[!UICONTROL Assistente de IA: Análise de Dados]** determina o acesso a esta ferramenta. Um [administrador de perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) precisa seguir estas etapas no [!UICONTROL Admin Console]:
   1. Navegue até **[!UICONTROL Admin Console]** > **[!UICONTROL Produtos e serviços]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfis de Produtos]**
   1. Selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: Conhecimento do Produto].
   1. No perfil de produto específico, selecione **[!UICONTROL Permissões]**.
   1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar as **[!UICONTROL Ferramentas de Relatório]**.
   1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) para adicionar o **Assistente de IA: Análise de Dados** a **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicionar permissão](assets/ai-assistant-permissions.png).

   1. Selecione **[!UICONTROL Salvar]** para salvar as permissões.

Consulte [Controle de acesso](/help/technotes/access-control.md#access-control) para obter mais informações.

## Acessar e usar o Assistente do Data Analysis AI

1. Acesse este link para abrir o Workspace na Organização IMS do Labs (no estágio) e faça logon com sua Adobe ID.

1. Clique em **[!UICONTROL Projeto em branco]** no banner na parte superior da página de projetos para abrir um novo projeto em branco.

1. Clique no ícone de bate-papo do Assistente do AI na parte superior direita.

   ![Ícone do Assistente de IA](/help/assets/ai-asst-icon.png)

1. Na caixa de diálogo **[!UICONTROL Pergunte sobre o Customer Journey Analytics]** na parte inferior, faça uma pergunta sobre análise de dados no Assistente de IA.

### Exemplo 1

Por exemplo, digamos que você esteja interessado nos pedidos que sua empresa recebeu em julho.

1. Insira &quot;Mostrar pedidos em julho&quot;.

   ![Solicitação de IA](/help/assets/ai-asst-prompt1.png)

1. O Assistente de IA agora reúne insights observando os dados na visualização de dados, incluindo as métricas e os componentes. Ele traduz o prompt para a(s) dimensão(ões), métrica(s) e intervalo de dados corretos.

   Como você pode ver, ele gerou automaticamente um gráfico de linha e uma tabela de forma livre mostrando pedidos para julho.

   ![Responder ao prompt - gráfico de linhas e tabela de forma livre](/help/assets/ai-asst-result.png)

### Exemplo 2

Em seguida, você deseja ver a comparação de receita por região.

1. Na janela do prompt, digite &quot;Mostrar receita por região&quot;.

2. A IA é inteligente o suficiente para entender que, por &quot;região&quot;, você significa &quot;região do cliente&quot;. Ele produz um gráfico de barras que melhor mostra a receita por região:

   ![Gráfico de barras](/help/assets/ai-asst-result2.png)

### Exemplo 3

Agora, vamos analisar a receita por categoria de produto.

1. Na janela do prompt, digite &quot;Mostrar receita por categoria do produto&quot;.

2. Novamente, o Assistente de IA de análise de dados escolhe a visualização mais apropriada, neste caso a visualização **[!UICONTROL Rosca]**, para responder à pergunta.

   ![Rosca](/help/assets/ai-asst-result3.png)

### Exemplo 4

Por fim, você quer saber qual SKU é a mais lucrativa e onde deve investir recursos de marketing.

1. Na janela do prompt, pergunte &quot;Qual é o lucro entre as SKUs de fevereiro a maio&quot;.

1. Um gráfico simples de **[!UICONTROL Barra]** fornece a resposta mais concisa:

   ![Gráfico de barras](/help/assets/ai-asst-result4.png)

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

A ser determinado

## Expectativas de teste de Alpha e feedback solicitado

Depois de fazer cada pergunta, analise cuidadosamente a resposta fornecida pelo assistente. É crucial avaliar as visualizações geradas de forma abrangente antes de fornecer feedback.

Avalie a resposta: a resposta fornecida está correta?

Se o Assistente responder no painel de chat: avalie a resposta textual.

* Se uma visualização/gráfico for exibido: avalie a visualização. Essa é a visualização apropriada/esperada para sua pergunta?

* Se uma tabela de forma livre for exibida: avalie a tabela de forma livre. Os dados da tabela de forma livre estão corretos? Ele está detalhando os dados quando solicitado? Os filtros aplicados são os que você solicitou ou espera?

* Se uma mensagem de erro genérica for fornecida informando que a pergunta está fora do escopo, forneça feedback se você acha que a mensagem fora do escopo é apropriada, dado o seu prompt. Seu prompt estava realmente no escopo?

Para cada resposta, aplique um polegar para cima ou para baixo, com base na resposta

Após a seleção de miniaturas para cima/para baixo, faça uma seleção para as caixas de comentários de multisseleção relevantes. Se quiser fornecer feedback adicional, adicione observações na caixa de texto aberta.

## Perguntas e contato

Email `taylorb@adobe.com` (PM)
Enviar perguntas e comentários no canal do Alpha Slack: #aep-cja-ai-assistant-testers ???


