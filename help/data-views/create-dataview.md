---
title: Criar uma exibição de dados
description: Descreve como criar uma visualização de dados para um conjunto de dados da plataforma no CJA (Customer Journey Analytics).
translation-type: tm+mt
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Criar uma exibição de dados

Uma visualização de dados é semelhante a um conjunto de relatórios virtual no Analytics, na medida em que, no sentido, é uma visualização &quot;filtrada&quot; dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados. Por exemplo, você pode ter uma visualização de dados em que todas as dimensões estão definidas como &quot;Último contato&quot; e, simultaneamente, outra visualização de dados (com base no mesmo conjunto de dados) com todas as dimensões definidas como &quot;Primeiro contato&quot;.

Os projetos da área de trabalho no Análise de jornada do cliente são baseados em visualizações de dados.

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) para obter uma visão geral do vídeo.

## Pré-requisito

Antes de poder criar visualizações de dados, é necessário [configurar uma ou mais conexões com os conjuntos de dados da plataforma] Experience](/help/connections/create-connection.md).

## Definir configurações

1. No Customer Journey Analytics, vá para a **[!UICONTROL Data Views]** guia.

1. Clique em **[!UICONTROL Add]** para adicionar uma visualização de dados e definir suas configurações.

   | Configuração da sessão | Definição |
   |---|---|
   | Conexão | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém os [!UICONTROL Experience Platform] conjuntos de dados. |
   | Nome | É obrigatório dar um nome à visualização de dados. |
   | Descrição | Uma descrição detalhada não é obrigatória, mas recomendada. |
   | Adicionar tags | As tags permitem que você organize suas visualizações de dados no categoria. |
   | Fuso Horário | Escolha o fuso horário para sua visualização de dados. |
   | Tempo limite da sessão | Selecione a definição de &quot;sessão&quot;. A configuração de limite de tempo de sessão define a quantidade de inatividade que um visitante único deve ter antes que uma nova sessão seja iniciada automaticamente. O padrão é 30 minutos. Por exemplo, se você definir o tempo limite da sessão como 45 minutos, um novo agrupamento de sessão será criado para cada sequência de ocorrências coletadas, separadas por 45 minutos de inatividade. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Start de nova sessão com Evento | Uma nova sessão é start quando um evento é acionado, independentemente de a sessão ter expirado. A sessão recém-criada inclui o evento que a iniciou. Além disso, você pode usar vários eventos para start de uma sessão e uma nova sessão é acionada se algum desses eventos for observado nos dados. Essa configuração afetará sua contagem de visitas, o container de segmento Sessão (antigo Visita) e a lógica de expiração de visita nas dimensões. |
   | Adicionar filtros | &quot;Filtros&quot; é o termo para &quot;segmentos&quot; no Customer Journey Analytics. Se você quiser filtrar seus dados, arraste o filtro apropriado para aqui do painel esquerdo. Se você não selecionar um filtro, a visualização de dados conterá todos os seus dados. |

1. Clique em **[!UICONTROL Continue]**.

## Adicionar componentes

1. Agora é hora de adicionar componentes (dimensões, métricas) à visualização de dados (semelhante à experiência de curadoria em conjuntos de relatórios virtuais). Observe que cada um dos campos nos conjuntos de dados agora é convertido em dimensões ou métricas. Arraste dimensões e métricas para o painel ou **[!UICONTROL Selecionar tudo** para adicionar todos os componentes.

   ![](assets/add-all-components.png)

1. Clique na **[!UICONTROL Add Components]** guia para adicionar dimensões e métricas à visualização de dados.

   ![](assets/add-all-components2.png)

1. (Opcional) É possível renomear um componente para um nome amigável ou alterar suas configurações de atribuição selecionando-o e editando sua configuração. Observe que o nome subjacente é preservado. Para obter mais informações, consulte [Configurar visualizações de dados e atribuição](/help/data-views/configure-dataviews.md).

1. As próximas etapas são para [especificar configurações](/help/data-views/configure-dataviews.md)de componentes e atribuições.