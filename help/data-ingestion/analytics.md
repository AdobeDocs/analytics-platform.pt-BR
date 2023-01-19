---
title: Assimilar e usar dados da Adobe Analytics tradicional
description: Explique como assimilar dados do Adobe Analytics tradicional
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 10%

---

# Assimilar e usar dados da Adobe Analytics tradicional

Este guia de início rápido explica como você pode usar os dados coletados pela Adobe Analytics no Customer Journey Analytics.

>[!PREREQUISITES]
>
>Você tem a Adobe Analytics licenciada e implantada em um ou mais de seus sites, usando qualquer um dos métodos de implementação documentados:
>
>- [Implementar o Analytics usando a Experience Platform Edge](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=pt-BR)
>
>- [Implementar o Analytics usando a extensão Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=pt-BR)
>
>- [Implementar o Analytics usando JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


Para isso, é necessário:

- **Configurar um conector de origem do Adobe Analytics** no Adobe Experience Platform. Isso cuida da assimilação dos dados atuais do Adobe Analytics em um conjunto de dados no Adobe Experience Platform.

- **Configurar uma conexão** em Customer Journey Analytics. Essa conexão deve (pelo menos) incluir o conjunto de dados do Adobe Experience Platform.

- **Configurar uma visualização de dados** no Customer Journey Analytics para definir métricas e dimensões que deseja usar no Analysis Workspace.

- **Configurar um projeto** no Customer Journey Analytics para criar relatórios e visualizações.


>[!NOTE]
>
>Este é um guia simplificado sobre como assimilar dados, usando o conector de origem do Adobe Analytics, e usar esses dados no Customer Journey Analytics. É altamente recomendável estudar as informações adicionais quando referidas.


## Configurar um conector de origem do Adobe Analytics

O conector de origem do Adobe Analytics permite trazer os dados do conjunto de relatórios do Adobe Analytics para o Adobe Experience Platform.

Para criar um conector de origem do Adobe Analytics:

1. Na interface do usuário da plataforma, selecione **[!UICONTROL Fontes]**, no painel esquerdo.

2. Selecionar **[!UICONTROL Aplicativos Adobe]** na lista de [!UICONTROL CATEGORIAS].

3. Selecionar **[!UICONTROL Configurar]** ou **[!UICONTROL Adicionar dados]** no bloco Adobe Analytics.

   ![Fontes](./assets/sources-overview.png)

4. Selecionar **[!UICONTROL Conjunto de relatórios]**. Na lista de conjuntos de relatórios, selecione aquele que deseja usar.

   ![Conjuntos de relatórios](./assets/report-suites.png)

   Selecione **[!UICONTROL Próximo]**.

5. Selecionar **[!UICONTROL Esquema padrão]** como [!UICONTROL Esquema de destino]. O Adobe Experience Platform cria automaticamente o esquema e o conjunto de dados correspondente para mapear todos os campos padrão do conjunto de relatórios do Adobe Analytics selecionado.

   ![Esquema padrão](./assets/default-schema.png)

   Selecione **[!UICONTROL Próximo]**.

6. Nomeie o fluxo de dados e (opcionalmente) forneça uma descrição.

   ![Detalhes do fluxo de dados](./assets/dataflow-detail.png)

   Selecione **[!UICONTROL Próximo]**.

7. Revise a conexão e selecione **[!UICONTROL Concluir]**.

   ![Consulte a seção](./assets/review.png)


Depois que a conexão é criada, o fluxo de dados é criado automaticamente para preencher um conjunto de dados com os dados do Adobe Analytics do conjunto de relatórios, incluindo a assimilação de até 13 meses de dados históricos.

Quando a assimilação inicial for concluída, os dados do conjunto de relatórios do Adobe Analytics estarão prontos para serem usados pelo Customer Journey Analytics.

Consulte [Criar uma conexão de origem do Adobe Analytics na interface do usuário](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) para obter um tutorial muito mais abrangente.


## Configurar uma conexão

Para usar os dados do Adobe Experience Platform no Customer Journey Analytics, crie uma conexão que inclua os dados resultantes da configuração do esquema, do conjunto de dados e do fluxo de trabalho.

Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre esses conjuntos de dados, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados no Adobe Experience Platform e no Workspace.

Para criar sua conexão:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Conexões]** na navegação superior.

2. Selecionar **[!UICONTROL Criar nova conexão]**.

3. No [!UICONTROL Conexão sem título] tela:

   Nomeie e descreva sua conexão em [!UICONTROL Configurações de conexão].

   Selecione a sandbox correta no [!UICONTROL Sandbox] listar em [!UICONTROL Configurações de dados] e selecione o número de eventos diários no [!UICONTROL Número médio de eventos diários] lista.

   ![Configurações de conexão](./assets/cja-connections-1.png)

   Selecionar **[!UICONTROL Adicionar conjuntos de dados]**.

   No [!UICONTROL Selecionar conjuntos de dados] etapa em [!UICONTROL Adicionar conjuntos de dados]:

   - Selecione o conjunto de dados criado automaticamente pelo conector de origem do Adobe Analytics e qualquer outro conjunto de dados que você deseja incluir na conexão.

      ![Adicionar conjuntos de dados](./assets/cja-connections-2a.png)

   - Selecione **[!UICONTROL Próximo]**.
   No [!UICONTROL Configurações de conjuntos de dados] etapa em [!UICONTROL Adicionar conjuntos de dados]:

   - Para cada conjunto de dados:

      - Selecione um [!UICONTROL ID da pessoa] nas identidades disponíveis definidas nos esquemas do conjunto de dados no Adobe Experience Platform.

      - Selecione a fonte de dados correta no [!UICONTROL Tipo de fonte de dados] lista. Se você especificar **[!UICONTROL Outras]**, em seguida, adicione uma descrição para a fonte de dados.

      - Definir **[!UICONTROL Importar todos os novos dados]** e **[!UICONTROL Preenchimento retroativo de conjunto de dados com dados existentes]** de acordo com suas preferências.

      ![Configurar conjuntos de dados](./assets/cja-connections-3.png)

   - Selecionar **[!UICONTROL Adicionar conjuntos de dados]**.
   Selecione **[!UICONTROL Salvar]**.

Consulte [Visão geral das conexões](../connections/overview.md) para obter mais informações sobre como criar e gerenciar uma conexão e como selecionar e combinar conjuntos de dados.

## Configurar uma visualização de dados

Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Ele especifica todas as dimensões e métricas disponíveis no Analysis Workspace e de quais colunas elas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

Para criar sua visualização de dados:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Visualizações de dados]** na navegação superior.

2. Selecionar **[!UICONTROL Criar nova visualização de dados]**.

3. No [!UICONTROL Configurar] etapa:

   Selecione sua conexão no [!UICONTROL Conexão] lista.

   Nomeie e (opcionalmente) descreva sua conexão.

   ![Configuração da exibição de dados](./assets/cja-dataview-1.png)

   Selecionar **[!UICONTROL Salvar e continuar]**.

4. No [!UICONTROL Componentes] etapa:

   Adicione qualquer campo de esquema e/ou componente padrão que deseja incluir à [!UICONTROL MÉTRICAS] ou [!UICONTROL DIMENSION] caixas de componentes.

   ![Componentes da exibição de dados](./assets/cja-dataview-2.png)

   Selecionar **[!UICONTROL Salvar e continuar]**.

5. No [!UICONTROL Configurações] etapa:

   Configurações de ![visualização de dados](./assets/cja-dataview-3.png)

   Deixe as configurações como estão e selecione **[!UICONTROL Salvar e concluir]**.

Consulte [Visão geral das visualizações de dados](../data-views/data-views.md) para obter mais informações sobre como criar e editar uma visualização de dados, quais componentes estão disponíveis para você usar na visualização de dados e como usar configurações de filtro e sessões.


## Configurar um projeto

O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises e compartilhar insights rapidamente com base em seus dados. Você usa projetos do Workspace para combinar componentes de dados, tabelas e visualizações para criar sua análise e compartilhar com qualquer pessoa em sua organização.

Para criar o projeto:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Projetos]** na navegação superior.

2. Selecionar **[!UICONTROL Projetos]** no painel de navegação esquerdo.

3. Selecionar **[!UICONTROL Criar projeto]**.

   ![Projeto do Workspace](./assets/cja-projects-1.png)

   Selecionar **[!UICONTROL Projeto em branco]**.

   ![Workspace - Projeto em branco](./assets/cja-projects-2.png)

4. Selecione sua visualização de dados na lista.

   ![Área de trabalho Selecionar visualização de dados](./assets/cja-projects-3.png).

5. Comece a arrastar e soltar dimensões e métricas na [!UICONTROL Tabela de forma livre] no [!UICONTROL Painel] para criar seu primeiro relatório. Como exemplo, arraste `Program Points Balance` e `Page View` como métricas e `email` como dimensão para obter uma visão geral rápida dos perfis que visitaram seu site e fazem parte do programa de fidelidade que coleta pontos de fidelidade.

   ![Workspace - Primeiro relatório](./assets/cja-projects-5.png)

Consulte [Visão geral do Analysis Workspace](../analysis-workspace/home.md) para obter mais informações sobre como criar projetos e sua análise usando componentes, visualizações e painéis.


>[!SUCCESS]
>
>Você concluiu todas as etapas. A partir da configuração do conector da fonte de dados do Adobe Analytics e da configuração desse conector para o conjunto de relatórios, os dados do Adobe Analytics são automaticamente carregados no Adobe Experience Platform. Você definiu uma conexão no Customer Journey Analytics para usar os dados do Adobe Analytics assimilados e outros dados. A definição da visualização de dados permite especificar qual dimensão e métricas usar e, por fim, criar seu primeiro projeto visualizando e analisando seus dados.

