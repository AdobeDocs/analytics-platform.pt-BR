---
title: Criar uma exibição de dados
description: Descreve como criar uma visualização de dados para um conjunto de dados da plataforma no Customer Journey Analytics (CJA).
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 94%

---

# Criar uma exibição de dados

Uma visualização de dados é semelhante a um conjunto de relatórios virtual no Analytics, na medida em que, no sentido, é uma visualização &quot;filtrada&quot; dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados. Por exemplo, você pode ter uma visualização de dados em que todas as dimensões estão definidas como &quot;Último contato&quot; e, simultaneamente, outra visualização de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas como &quot;Primeiro contato&quot;.

Os projetos do Workspace no Customer Journey Analytics são baseados em visualizações de dados.

Clique [aqui](https://docs.adobe.com/content/help/pt-BR/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) para obter uma visão geral do vídeo.

## Pré-requisito

Antes de criar visualizações de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados da Experience Platform](/help/connections/create-connection.md).

## Definir configurações

1. No Customer Journey Analytics, acesse a guia **[!UICONTROL Visualizações de dados]**.

1. Clique em **[!UICONTROL Adicionar]** para adicionar uma visualização de dados e definir suas configurações.

   | Configuração da sessão | Definição |
   |---|---|
   | Conexão | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém os conjuntos de dados da [!UICONTROL Experience Platform]. |
   | Nome | É obrigatório dar um nome à visualização de dados. |
   | Descrição | Uma descrição detalhada não é obrigatória, mas é recomendada. |
   | Adicionar tags | As tags permitem organizar as visualizações de dados em categorias. |
   | Fuso horário | Escolha o fuso horário para a visualização de dados. |
   | Tempo limite da sessão | Selecione a definição de &quot;sessão&quot;. A configuração de tempo limite de sessão define a quantidade de inatividade que um visitante único deve ter antes que uma nova sessão seja iniciada automaticamente. O padrão é 30 minutos. Por exemplo, se o tempo limite de sessão for definido para 45 minutos, um novo grupo de sessões será criado para cada sequência de ocorrências coletadas, separadas por 45 minutos de inatividade. <!--This setting impacts not only your visit counts, but also how visit filter containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Iniciar nova sessão com evento | Uma nova sessão começa quando um evento é acionado, independente do fato de uma sessão ter ultrapassado o tempo limite. A sessão recentemente criada inclui o evento que a iniciou. Além disso, é possível usar vários eventos para começar uma sessão e uma nova sessão é acionada se qualquer um desses eventos for observado nos dados. Essa configuração afetará a contagem de visitas, o contêiner de filtro Sessão (anteriormente Visita) e a lógica de expiração de visitas nas dimensões. |
   | Adicionar filtros | Se você quiser filtrar os dados, arraste o filtro apropriado para cá a partir do painel esquerdo. Se você não selecionar um filtro, a visualização de dados conterá todos os dados. |

1. Clique em **[!UICONTROL Continuar]**.

## Adicionar componentes

1. Agora é hora de adicionar componentes (dimensões, métricas) à visualização de dados. Observe que cada um dos campos nos conjuntos de dados agora é convertido em dimensões ou métricas. Arraste dimensões e métricas para o painel ou clique em **[!UICONTROL Selecionar tudo]** para adicionar todos os componentes.

   ![](assets/add-all-components.png)

1. Clique na guia **[!UICONTROL Adicionar componentes]** para adicionar dimensões e métricas à visualização de dados.

   ![](assets/add-all-components2.png)

1. (Opcional) É possível renomear um componente com um nome simples ou alterar suas configurações de atribuição selecionando-o e editando sua configuração. Observe que o nome subjacente é preservado. Para obter mais informações, consulte [Configurar visualizações de dados e atribuição](/help/data-views/configure-dataviews.md).

1. As próximas etapas são para [especificar configurações de componentes e atribuições](/help/data-views/configure-dataviews.md).

## Excluir visualizações de dados

Se você excluir uma visualização de dados no [!UICONTROL Customer Journey Analytics], uma mensagem de erro indicará que qualquer projeto do Workspace que depende dessa visualização de dados excluída deixará de funcionar.
