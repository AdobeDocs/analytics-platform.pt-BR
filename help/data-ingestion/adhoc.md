---
title: Assimilar e usar dados ad hoc
description: Explicar como assimilar e usar a ad hoc no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
exl-id: 17b5842f-dc81-481f-8b21-dc90a133adcf
source-git-commit: c9d7a4596a842ab7d949364e3469747d20ca15b4
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 24%

---

# Assimilar e usar dados ad hoc

Este guia de início rápido explica como você pode assimilar dados ad hoc na Experience Platform e, em seguida, usar esses dados no Customer Journey Analytics.

Para isso, é necessário:

- **Crie um conjunto de dados com um arquivo CSV** no Experience Platform. Esse fluxo de trabalho define o modelo (esquema) dos dados que você deseja coletar e onde coletar os dados (conjunto de dados).

- **Configurar uma conexão** no Customer Journey Analytics. Essa conexão deve (pelo menos) incluir seu conjunto de dados ad hoc do Experience Platform.

- **Configure uma visualização de dados** no Customer Journey Analytics para definir métricas e dimensões a partir dos campos em seus dados ad hoc que você deseja usar no Analysis Workspace.

- **Configurar um projeto** no Customer Journey Analytics para criar relatórios e visualizações.



>[!NOTE]
>
>Este guia de início rápido é um guia simplificado sobre como assimilar dados ad hoc usando no Experience Platform e usar esses dados ad hoc no Customer Journey Analytics. É altamente recomendável estudar as informações adicionais quando referidas.


## Criar um conjunto de dados com um arquivo CSV

Para esse início rápido, você deseja usar um arquivo CSV que representa dados de pesquisa e contém informações semelhantes àquelas mostradas abaixo.

| _id | tracking_code | ad_group | campaign_name |
| ---: | :---          | :---        | :---          |
| 1 | abc123 | abc-adgroup | 123 Campanha |
| 2 | def123 | def-adgroup | 123 Campanha |
| 3 | ghi123 | ghi-adgroup | 123 Campanha |
| 4 | abc456 | abc-adgroup | Campanha 456 |
| 5 | def456 | def-adgroup | Campanha 456 |

>[!NOTE]
>
>Use conjuntos de dados e esquemas ad hoc para dados baseados em registro (pesquisa, perfil). Os conjuntos de dados e esquemas ad hoc são menos adequados e não devem ser considerados para dados de séries temporais (evento, resumo).

Não é necessário criar um esquema XDM para dados ad hoc. O Experience Platform é compatível com um fluxo de trabalho que, com base nos dados no arquivo CSV:

1. Cria um esquema ad hoc automaticamente. Esse esquema está em conformidade com as colunas do arquivo CSV.
1. Cria um conjunto de dados que contém os dados do arquivo CSV.

Para iniciar o workflow:

1. Na interface do Experience Platform, no painel à esquerda, selecione **[!UICONTROL Workflows]**.
1. Selecione ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL Criar conjunto de dados do arquivo CSV]**.
1. Selecione **[!UICONTROL Iniciar]** no painel direito.
1. No assistente **[!UICONTROL Workflows]** > **[!UICONTROL Criar conjunto de dados do arquivo CSV]**:
   1. Na etapa **[!UICONTROL Configurar conjunto de dados]**:
      1. Insira um **[!UICONTROL Nome]** para o conjunto de dados. Por exemplo: `Sample Data From CSV`.
      1. Adicione uma **[!UICONTROL Descrição]** opcional. Por exemplo: `Sample data from a CSV file`.
      1. Adicione uma ou mais **[!UICONTROL Marcas]** opcionais ou selecione uma ou mais **[!UICONTROL Marcas]** existentes.

         ![Configurar conjunto de dados ad hoc](assets/adhoc-dataset-configure.png)

      1. Selecione **[!UICONTROL Próximo]**.
   1. Na etapa **[!UICONTROL Adicionar dados]**:
      1. Selecione **[!UICONTROL Escolher Arquivos]** para selecionar seu arquivo CSV do computador ou da rede. Como alternativa, arraste e solte o arquivo de seu local no computador ou na rede para **[!UICONTROL Arraste e solte arquivos]**. O arquivo foi carregado e **[!UICONTROL Dados de exemplo]** são exibidos.
      1. Habilite ou desabilite o **[!UICONTROL Diagnóstico de erro]** e o **[!UICONTROL Habilite a assimilação parcial]** de acordo com suas preferências. Quando você **[!UICONTROL Habilita a assimilação parcial]**, é possível definir um **[!UICONTROL Limite de erro %]**.

         ![Adicionar dados a um conjunto de dados ad hoc](assets/adhoc-dataset-adddata.png)

      1. Selecione **[!UICONTROL Concluir]**.

Depois que os dados forem preparados e carregados com êxito, você será redirecionado para **[!UICONTROL Conjuntos de dados]** na interface do Experience Platform.<br/> Você vê a **[!UICONTROL Atividade do conjunto de dados]** para o seu **[!UICONTROL Dados de Amostra do CSV]** com o status ![StatusOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL Processando]**.

![Atividade do conjunto de dados para dados ad hoc](assets/datasets-dataset-activity.png)

Para inspecionar os dados ad hoc:

1. Na interface do Experience Platform, no painel à esquerda, selecione **[!UICONTROL Conjuntos de dados]**.
1. Selecione a guia **[!UICONTROL Procurar]** em **[!UICONTROL Conjuntos de Dados]**. Você deve ver seu conjunto de dados listado.
1. Selecione o nome do esquema na coluna **[!UICONTROL Esquema]**. Por exemplo: **[!UICONTROL Dados de Exemplo de CSV...]**

   ![Selecionar esquema para o conjunto de dados ad hoc](assets/adhoc-schema-selection.png)

1. Na janela pop-up, selecione o **[!UICONTROL Nome do esquema]**. Por exemplo: **[!UICONTROL Dados de amostra do CSV - esquema adhoc - XXXXXXXXXXX]**. Você é redirecionado para a interface **[!UICONTROL Esquemas]** > **[!UICONTROL Dados de amostra do CSV - esquema adhoc - XXXXXXXXXXX]**.

Nos **[!UICONTROL Esquemas]** > **[!UICONTROL Dados de amostra do CSV - esquema adhoc - XXXXXXXXXXX]** interface:

- Selecione o objeto de nome de locatário mais acima sob **[!UICONTROL Esquemas]** > **[!UICONTROL Dados de amostra do CSV - esquema adhoc - XXXXXXXXXXX]** para revelar os campos dentro do objeto. Os campos no objeto representam a estrutura do arquivo CSV. O schema é criado automaticamente com base no upload dos dados ad hoc.

  ![Esquema ad hoc](dataset/../assets/adhoc-schema.png)

  >[!NOTE]
  >
  >O fluxo de trabalho define todos os campos no esquema como do tipo String. Não é possível alterar esse tipo em um estágio posterior. Se você precisar de mais flexibilidade na definição de um esquema ad hoc, considere [usar a API para criar um esquema ad hoc](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/ad-hoc) e usar o fluxo de trabalho [Criar conjunto de dados a partir do esquema](https://experienceleague.adobe.com/pt-br/docs/experience-platform/catalog/datasets/user-guide#schema).
  > 




## Configurar uma conexão

Para usar o conjunto de dados do Experience Platform no Customer Journey Analytics, crie uma conexão que inclua o conjunto de dados ad hoc resultante do [fluxo de trabalho](#create-a-dataset-with-a-csv-file)

Uma conexão permite integrar conjuntos de dados do Experience Platform ao Workspace. Para criar relatórios sobre esses conjuntos de dados, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Workspace.

Para criar sua conexão:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Conexões]**, opcionalmente em **[!UICONTROL Gerenciamento de dados]**, no menu superior.

1. Selecione **[!UICONTROL Criar nova conexão]**.

1. Na tela **[!UICONTROL Conexão sem título]**:

   1. Nomeie e descreva sua conexão em **[!UICONTROL Configurações de conexão]**.

   1. Selecione a sandbox correta na lista **[!UICONTROL Sandbox]** em **[!UICONTROL Configurações de dados]** e selecione o número de eventos diários na lista **[!UICONTROL Número médio de eventos diários]**.

      ![Configurações de conexão](./assets/cja-connections-1.png)

   1. Selecione **[!UICONTROL Adicionar conjuntos de dados]**.

1. Na etapa **[!UICONTROL Selecionar conjuntos de dados]** em **[!UICONTROL Adicionar conjuntos de dados]**:

   1. Selecione o conjunto de dados criado anteriormente, por exemplo **[!UICONTROL Dados de Exemplo do CSV]**, e qualquer outro conjunto de dados que você queira incluir em sua conexão. Os conjuntos de dados ad hoc têm o **[!UICONTROL tipo de conjunto de dados]** [!UICONTROL Adhoc].

      ![Adicionar conjuntos de dados](./assets/cja-connections-adhoc-2.png)

   1. Selecione **[!UICONTROL Próximo]**.

1. Na etapa **[!UICONTROL Configurações de conjuntos de dados]** em **[!UICONTROL Adicionar conjuntos de dados]**:

   Para seu conjunto de dados ad hoc:

   1. Selecione o tipo de conjunto de dados ad hoc. Por exemplo: **[!UICONTROL Pesquisa]**.
   1. Selecione uma **[!UICONTROL Chave]** a partir das chaves disponíveis definidas no esquema ad hoc.
   1. Selecione uma **[!UICONTROL Chave correspondente]** de um conjunto de dados de evento que você adicionou como parte de sua conexão.
   1. Selecione a fonte de dados correta na lista **[!UICONTROL Tipo de fonte de dados]**. Se você especificar **[!UICONTROL Outros]**, em seguida, adicione uma descrição para a fonte de dados.

   1. Definir **[!UICONTROL Importar todos os novos dados]** e **[!UICONTROL Preenchimento retroativo de conjunto de dados com dados existentes]** de acordo com suas preferências.

      ![Configurar conjuntos de dados](./assets/cja-connections-3-adhoc.png)

   1. Selecione **[!UICONTROL Adicionar conjuntos de dados]**.

   1. Selecione **[!UICONTROL Salvar]**.

Consulte [Configurações do conjunto de dados ad hoc](/help/connections/create-connection.md#adhoc-dataset) para obter mais detalhes sobre as configurações disponíveis para conjuntos de dados ad hoc.

>[!IMPORTANT]
>
>Além da recomendação geral para não usar esquemas e conjuntos de dados ad hoc para dados de séries de tempo, você não pode usar o fluxo de trabalho **[!UICONTROL Criar conjunto de dados do CSV]** para dados de séries de tempo. Esse workflow define todos os campos como sendo do tipo String que você não pode modificar posteriormente. Quando você adiciona um conjunto de dados com base em séries de tempo (evento ou resumo) a uma conexão, esse tipo de conjunto de dados exige a definição de pelo menos um campo do tipo DateTime.<br/>Se você precisar usar dados de série temporal ad hoc, considere [usar a API para criar um esquema ad hoc](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438) e usar o fluxo de trabalho [Criar conjunto de dados a partir do esquema](https://experienceleague.adobe.com/pt-br/docs/experience-platform/catalog/datasets/user-guide#schema).


Depois de criar uma [conexão](/help/connections/overview.md), você poderá executar várias tarefas de gerenciamento, como [selecionar e combinar conjuntos de dados](/help/connections/combined-dataset.md), [verificar o status dos conjuntos de dados de uma conexão e o status da assimilação de dados](/help/connections/manage-connections.md) e muito mais.

## Configurar uma visualização de dados

Uma visualização de dados é um container específico do Customer Journey Analytics que permite determinar como interpretar dados de uma conexão. Ele especifica todas as dimensões e métricas disponíveis no Analysis Workspace e de quais colunas elas obtêm seus dados. As visualizações de dados são definidas na preparação de relatórios no Analysis Workspace.

Para criar a visualização de dados:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Visualizações de dados]**, opcionalmente em **[!UICONTROL Gerenciamento de dados]**, no menu superior.

1. Selecione **[!UICONTROL Criar nova visualização de dados]**.

1. Na etapa **[!UICONTROL Configurar]**:

   1. Selecione sua [conexão](#set-up-a-connection) na lista **[!UICONTROL Conexão]**.

   1. Nomeie e (opcionalmente) descreva a conexão.

      ![Configuração da visualização de dados](./assets/cja-dataview-1.png)

   1. Selecione **[!UICONTROL Salvar e continuar]**.

1. Na etapa **[!UICONTROL Componentes]**:

   1. Adicione qualquer campo de esquema e/ou componente padrão que você deseja incluir nas caixas de componentes **[!UICONTROL MÉTRICAS]** ou **[!UICONTROL DIMENSÕES]**. Adicione campos relevantes a partir do conjunto de dados que contém os dados ad hoc. Para acessar esses campos:

      1. Selecione **[!UICONTROL Conjuntos de dados de evento]**.
      1. Selecione **[!UICONTROL Campos Adhoc e Relacionais]**.

         ![Visualização de dados - componentes adhoc](assets/cja-dataview-components-adhoc.png)

      1. Arraste e solte campos dos esquemas ad hoc para **[!UICONTROL MÉTRICAS]** ou **[!UICONTROL DIMENSÕES]**.



   1. Opcionalmente, use [campos derivados](/help/data-views/derived-fields/derived-fields.md) para modificar qualquer um dos campos ad hoc de seu tipo e formato de Cadeia de Caracteres padrão para outro tipo ou formato.

   1. Selecione **[!UICONTROL Salvar e continuar]**.

1. Na etapa **[!UICONTROL Configurações]**:

   Deixe as configurações como estão e selecione **[!UICONTROL Salvar e concluir]**.

Consulte [Visão geral das visualizações de dados](../data-views/data-views.md) para obter mais informações sobre como criar e editar uma visualização de dados. E quais componentes estão disponíveis para você usar na visualização de dados e como usar as configurações de segmento e sessões.


## Configurar um projeto

O Analysis Workspace é uma ferramenta de navegador flexível que permite criar análises rapidamente e compartilhar insights com base em seus dados. Os projetos do Espaço de trabalho permitem combinar componentes de dados, tabelas e visualizações para criar a análise e compartilhar com qualquer pessoa na organização.

Para criar o projeto:

1. Na interface do usuário do Customer Journey Analytics, selecione **[!UICONTROL Projetos]** no menu superior.

1. Selecione **[!UICONTROL Projetos]** no painel de navegação esquerdo.

1. Selecione **[!UICONTROL Criar projeto]**.

1. Selecione **[!UICONTROL Projeto em branco]**.

1. Selecione sua [visualização de dados](#set-up-a-data-view) na lista.

1. Para criar seu primeiro relatório, comece a arrastar e soltar dimensões e métricas na [!UICONTROL Tabela de forma livre] do [!UICONTROL Painel]. Incluindo as métricas ou dimensões baseadas em seus dados ad hoc.

Consulte [Visão geral do Analysis Workspace](../analysis-workspace/home.md) para obter mais informações sobre como criar projetos e sua análise usando componentes, visualizações e painéis.

>[!SUCCESS]
>
>Você concluiu todas as etapas. Você começou definindo quais dados ad hoc desejava coletar (arquivo CSV). Você usou o fluxo de trabalho para criar um conjunto de dados ad hoc e um esquema desse arquivo CSV. Você definiu uma conexão no Customer Journey Analytics para usar os dados ad hoc assimilados e outros dados. A definição da visualização de dados permite especificar qual dimensão e métricas usar e, por fim, criar seu primeiro projeto visualizando e analisando seus dados.
