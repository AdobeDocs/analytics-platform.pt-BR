---
description: Como fazer perguntas sobre a documentação do Customer Journey Analytics
title: Assistente de IA do Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 82b36895fe5186f0133c128d434470ea7f875677
workflow-type: ht
source-wordcount: '648'
ht-degree: 100%

---


# Assistente de IA do Adobe Customer Journey Analytics

O Assistente de IA fornece uma experiência de conversação que permite que profissionais concluam tarefas com muito mais rapidez. Não importa se a tarefa envolve entender conceitos, solucionar problemas ou pesquisar informações. O Assistente de IA também permite que pessoas que não são especialistas realizem tarefas especializadas e aumenta a qualidade geral do trabalho.

O Assistente de IA do Customer Journey Analytics é treinado com base na documentação da Adobe Experience League. Quando você faz uma pergunta, o Assistente de IA fornece uma resposta útil que agiliza o aprendizado.

Como usuário iniciante, você pode usar o Assistente de IA para aprender conceitos do Customer Journey Analytics e se familiarizar com produtos e recursos que ainda não conhece. Como usuário experiente, você pode usar o Assistente de IA para apresentar casos de uso mais avançados ou dicas e truques.

Veja alguns exemplos de perguntas conceituais:

* Qual é a diferença entre ingestão em lote e por transmissão?
* Para que o Customer Journey Analytics é melhor utilizado?
* Como configurar uma visualização de dados?

Esse recurso não responderá perguntas que não se enquadram no escopo do Customer Journey Analytics, como perguntas sobre outros produtos, como o Adobe Target e a Adobe Creative Cloud Suite.

O Assistente de IA do Customer Journey Analytics está disponível para todos os níveis de produto.

## Conhecimento do produto {#knowledge}

| Conhecimento do produto | Exemplos |
| --- | --- |
| Aprendizagem pontual | <ul><li>Qual é a diferença entre o Adobe Analytics e o Customer Journey Analytics?</li><li>Como criar uma métrica calculada?</li></ul> |
| Descoberta aberta | <ul><li>Como posso exportar um projeto do espaço de trabalho?</li><li>Como posso encontrar componentes duplicados do espaço de trabalho?</li></ul> |
| Solução de problemas | <ul><li>Quanto tempo leva para os dados entrarem no CJA?</li><li>Quantos campos derivados posso ter em uma conexão do Customer Journey Analytics?</li></ul> |

## Análise de dados

O Data Insights Agent, acessível pelo Assistente de IA no Customer Journey Analytics, é um agente de conversação de IA generativa que responde de forma rápida e eficiente a perguntas sobre seus dados. Ele cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e seus dados reais.

Para mais informações sobre como usar o Data Insights Agent dentro do Assistente de IA, consulte [Visualizar dados com o Data Insights Agent](/help/data-analysis-ai.md).

## Acesso ao recurso

Os parâmetros a seguir controlam o acesso ao recurso do Assistente de IA:

* **Acesso à solução**: o Assistente de IA está disponível no Customer Journey Analytics, mas não no Adobe Analytics. Também está disponível na Adobe Experience Platform, no Adobe Journey Optimizer, na Adobe Real-Time CDP e em outros aplicativos da Experience Platform.

* **Acesso contratual**: se você não conseguir usar o Assistente de IA, entre em contato com o(a) admin da organização ou representante de conta da Adobe. Antes da sua organização poder usar o Assistente de IA, você deve concordar com determinados termos legais relacionados à IA generativa.

* **Permissões**: no [!UICONTROL Adobe Admin Console], a permissão [!UICONTROL Ferramentas de relatórios] **[!UICONTROL Assistente de IA: conhecimento do produto]** determina o acesso a esta ferramenta. Um(a) [admin de perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) precisa seguir estas etapas no [!UICONTROL Admin Console]:
   1. Navegue até **[!UICONTROL Admin Console]** > **[!UICONTROL Produtos e serviços]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfis de produtos]**
   1. Selecione o título do perfil de produto para o qual você deseja fornecer acesso ao [!UICONTROL Assistente de IA: conhecimento do produto].
   1. No perfil de produto específico, selecione **[!UICONTROL Permissões]**.
   1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar as **[!UICONTROL Ferramentas de relatório]**.
   1. Clique no ![AddCircle](/help/assets/icons/AddCircle.svg) para adicionar **Assistente de IA: conhecimento do produto** a **[!UICONTROL Itens de permissão incluídos]**.

      ![Adicionar permissão](assets/ai-assistant-permissions.png).

   1. Clique em **[!UICONTROL Salvar]** para salvar as permissões.

Consulte [Controle de acesso](/help/technotes/access-control.md#access-control) para obter mais informações.

## Acesse o Assistente de IA na interface do Customer Journey Analytics

1. Para iniciar o Assistente de IA, clique no ícone do recurso no cabeçalho superior de qualquer página na interface do Customer Journey Analytics.

   ![Ícone do Assistente de IA](assets/ai-asst1.png)

   Ao usar o Assistente de IA pela primeira vez, um aviso de isenção de responsabilidade será exibido com alguns termos e condições para uso do assistente.

1. Na caixa fornecida, faça uma pergunta específica em linguagem natural para o Assistente de IA.

   ![Caixa de perguntas](assets/ai-asst2.png)

1. (Opcional) Para exibir as fontes de referência, clique em **[!UICONTROL Mostrar fontes]** e a documentação usada como referência para a resposta será exibida.

1. (Opcional) Também é possível fornecer feedback sobre a utilidade das respostas fornecidas com os ícones de polegar para cima (foi útil) e polegar para baixo (não foi útil).

1. (Opcional) É possível sinalizar a resposta como conteúdo inadequado ou prejudicial.
