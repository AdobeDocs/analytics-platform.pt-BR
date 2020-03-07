---
title: Criar uma exibição de dados
description: Descreve como criar uma exibição de dados para um conjunto de dados da plataforma no CJA (Customer Journey Analytics).
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# Criar uma exibição de dados

Uma exibição de dados é semelhante a um conjunto de relatórios virtual no Analytics, já que, no sentido, é uma exibição &quot;filtrada&quot; dos dados. Você pode criar diferentes exibições de dados para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias exibições de dados para um único conjunto de dados. Por exemplo, você pode ter uma exibição de dados em que todas as dimensões estão definidas como &quot;Último contato&quot; e, simultaneamente, outra exibição de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas como &quot;Primeiro contato&quot;.

Os projetos da área de trabalho no Análise de jornada do cliente são baseados em exibições de dados.

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) para obter uma visão geral do vídeo.

## Pré-requisitos

Antes de criar exibições de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados](/help/connections/create-connection.md)da plataforma Adobe Experience.

## Definir configurações

1. No Customer Journey Analytics, vá para a **[!UICONTROL Data Views]** guia.

1. Clique em **[!UICONTROL Add]** para adicionar uma exibição de dados e definir suas configurações.

   | Configuração da sessão | Definição |
   |---|---|
   | Conexão | Esse campo vincula a exibição de dados à conexão estabelecida anteriormente, que contém os conjuntos de dados da plataforma. |
   | Nome | Atribuir um nome à exibição de dados é obrigatório. |
   | Descrição | Uma descrição detalhada não é obrigatória, mas recomendada. |
   | Adicionar tags | As tags permitem que você organize suas exibições de dados em categorias. |
   | Fuso Horário | Escolha o fuso horário para sua exibição de dados. |
   | Tempo limite da sessão | Selecione a definição de &quot;sessão&quot;. A configuração de tempo limite da sessão define a quantidade de inatividade que um visitante único deve ter antes que uma nova sessão seja iniciada automaticamente. O padrão é 30 minutos. For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Iniciar nova sessão com evento | Uma nova sessão começa quando um evento é acionado, independente do fato de uma sessão ter ultrapassado o tempo limite. A sessão recentemente criada inclui o evento que a iniciou. Além disso, é possível usar vários eventos para começar uma sessão e uma nova sessão é acionada se qualquer um desses eventos for observado nos dados. Essa configuração afetará sua contagem de visitas, o contêiner de segmento Sessão (antigo Visita) e a lógica de expiração de visita nas dimensões. |
   | Adicionar filtros | &quot;Filtros&quot; é o termo para &quot;segmentos&quot; no Customer Journey Analytics. Se você quiser filtrar seus dados, arraste o filtro apropriado para aqui do painel esquerdo. Se você não selecionar um filtro, a exibição de dados conterá todos os seus dados. |

1. Clique em **[!UICONTROL Continue]**.

## Adicionar componentes

1. Agora é hora de adicionar componentes (dimensões, métricas) à exibição de dados (semelhante à experiência de curadoria em conjuntos de relatórios virtuais). Observe que cada um dos campos nos conjuntos de dados agora é convertido em dimensões ou métricas. Arraste dimensões e métricas para o painel ou **[!UICONTROL Selecionar tudo** para adicionar todos os componentes.

   ![](assets/add-all-components.png)

1. Clique na **[!UICONTROL Add Components]** guia para adicionar dimensões e métricas à exibição de dados.

   ![](assets/add-all-components2.png)

1. (Opcional) É possível renomear um componente para um nome amigável ou alterar suas configurações de atribuição selecionando-o e editando sua configuração. Observe que o nome subjacente é preservado. Para obter mais informações, consulte [Configurar exibições de dados e atribuição](/help/data-views/configure-dataviews.md).

1. As próximas etapas são para [especificar configurações](/help/data-views/configure-dataviews.md)de componentes e atribuições.