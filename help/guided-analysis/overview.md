---
title: Visão geral da análise guiada
description: Um método de análise de dados em Customer Journey Analytics que permite que as equipes de produtos obtenham insights de alta qualidade rapidamente. Também conhecido como Product Analytics.
keywords: análise do produto
exl-id: 1ac8157f-87e8-4d98-a2ca-f6beb68d9d6b
feature: Guided Analysis
role: User
source-git-commit: 6f80a1aa4ec9142d75fe1abb2f268dc60c7dd245
workflow-type: tm+mt
source-wordcount: '1293'
ht-degree: 2%

---

# Visão geral da análise guiada

o Adobe Product Analytics permite que as equipes de produtos realizem o autoatendimento de dados e insights sobre sua experiência com produtos por meio de fluxos de trabalho de análise guiados, baseados nos dados entre canais do Customer Journey Analytics. A análise guiada é um formato de relatório que permite que as equipes de produtos atendam rapidamente às suas necessidades de dados, para que possam obter insights de alta qualidade rapidamente e tomar mais decisões de produto orientadas por dados. Equipes multifuncionais podem se conectar em tempo real para usar e entender esses relatórios.

Semelhante aos cartões de pontuação do Analysis Workspace e Mobile, um relatório de análise guiada usa dados de um [Visualização de dados](../data-views/data-views.md), que faz referência aos dados no Adobe Experience Platform por meio de uma [Conexão](../connections/overview.md). Todos os relatórios criados na análise guiada podem ser transferidos facilmente para a Analysis Workspace para pesquisa adicional.

A análise guiada fornece várias maneiras de analisar e visualizar dados. Os tipos de exibição podem mostrar os mesmos dados de maneiras diferentes, resultando em insights diferentes usando os mesmos eventos e segmentos. Você obtém diferentes painéis de consulta e configurações de visualização dependendo da visualização escolhida. Você pode alternar livremente entre exibições e qualquer componente do painel de consulta aplicável é transportado se a exibição for compatível com elas.

A análise guiada categoriza os tipos de visualização em **Tipos de análise**. Os seguintes tipos de análise e visualização estão disponíveis:

| Tipo de análise | Tipo de visualização | Descrição |
| --- | --- | --- |
| [!UICONTROL Impacto] | [Versão](types/release.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| [!UICONTROL Impacto] | [Primeira utilização](types/first-use.md) | Meça o impacto do uso de recursos pela primeira vez nos indicadores principais. |
| [!UICONTROL Funil] | [Fricção](types/friction.md) | Comparar taxas de conversão entre etapas. |
| [!UICONTROL Funil] | [Tendências de conversão](types/conversion-trends.md) | Rastreie as alterações nas taxas de conversão ao longo do tempo. |
| [!UICONTROL Crescimento do usuário] | [Ativo](types/active.md) | Identifique quem é novo, está retido, retornando ou está inativo. |
| [!UICONTROL Crescimento do usuário] | [Crescimento líquido](types/net-growth.md) | Você está ganhando ou perdendo usuários? |
| [!UICONTROL Tendências] | [Uso](types/usage.md) | Meça o engajamento do usuário ao longo do tempo. |
| [!UICONTROL Tendências] | [Frequência](types/frequency.md) | Meça o engajamento por frequência de uso. |

{style="table-layout:auto"}

## Access

Se sua organização for provisionada para análise guiada, você poderá acessá-la na página inicial do Customer Journey Analytics.

1. Clique em **[!UICONTROL Análise guiada]** na página inicial, que leva você diretamente para a página [Exibição de tendências de uso](types/usage.md).

   ![Mosaico da página de aterrissagem](assets/landing-page-tile.png)

1. Clique em **[!UICONTROL Criar novo]** para ver as diferentes opções de exibição e escolher um ponto de partida diferente para a análise.

   ![Criar um novo modal](assets/create-new-modal.png)

Se sua organização ainda não tiver sido provisionada para análise guiada, entre em contato com a Equipe de conta do Adobe.

## Interface

A interface para análise guiada segue um formato de pergunta e resposta. Formule sua pergunta no painel de consulta e obtenha uma resposta com um insight por escrito, gráfico e tabela. Em seguida, você pode fazer a próxima pergunta com as configurações de visualização e os tipos de visualização.

Independentemente do tipo de análise, a análise guiada usa os seguintes elementos de interface do usuário:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png) | Painel de consulta | Configure os componentes desejados (eventos, propriedades e segmentos) que compõem uma análise. Cada tipo de análise impõe limites diferentes ao número de eventos e segmentos que podem ser configurados.<p>Use o ícone de filtro para restringir por propriedades de evento específicas ou criar segmentos em tempo real. Depois que uma propriedade é selecionada, além dos critérios de filtro padrão, como &quot;é igual&quot;, &quot;contém&quot; e &quot;termina com&quot;, uma lista dos 1000 principais valores de propriedade é disponibilizada para filtragem rápida.<p>Se você alternar para um novo tipo de análise, suas seleções de consulta serão mantidas dentro dos limites permitidos para esse tipo de análise. |
| ![Gráfico](assets/chart.png) | Gráfico | Uma visualização dos dados retornados com base na entrada do painel de consulta e nas configurações. A visualização exibida depende da exibição e das configurações acima do gráfico. O gráfico também inclui: <ul><li>**Dicas de ferramenta**: passe o mouse sobre qualquer ponto de dados do gráfico para expor uma dica de ferramenta com mais informações.</li><li>**Legenda**: passe o mouse sobre a série de legendas do gráfico para exibir as definições quando disponíveis, concentrar-se nessa série e ocultar temporariamente outras séries. Ocultar uma série na legenda clicando nela.</li><li>**Anotações**: Aplicável [anotações](../components/annotations/overview.md) são visíveis entre a visualização e a legenda. É mostrado como um ![Ícone de anotação](assets/annotation.png) ícone na cor configurada da anotação. Os tipos de exibição que mostram dados ao longo do tempo colocam o ![Ícone de anotação](assets/annotation.png) ícone na data ou intervalo de datas configurado. Os tipos de exibição que não mostram dados ao longo do tempo mostram ![Ícone de anotação](assets/annotation.png) no canto inferior direito do gráfico.</li><li>**Ações de clique**: exponha as próximas ações disponíveis clicando com o botão esquerdo do mouse em qualquer ponto de dados. As opções incluem **Salvar segmento**.</li></ul> |
| ![Tabela](assets/table.png) | Tabela | Uma representação em tabela dos dados retornados com base na entrada do painel de consulta e nas configurações. As colunas na tabela dependem do tipo de exibição acima do gráfico. A tabela também inclui: <ul><li>**Ações de clique**: oculte ou exponha uma série de gráficos, alternando a variável ![Mostrar ícone ocultar](assets/hide-in-chart.png) em cada linha. Ações adicionais estão disponíveis clicando no link **[!UICONTROL Mais]** menu. As opções incluem **Salvar segmento**.</li></ul> |
| ![Configurações de visualização](assets/visualization-settings.png) | Configurações de visualização | Opções acima do gráfico que permitem fazer a próxima pergunta e personalizar como o gráfico e a tabela retornam dados. As seguintes opções estão disponíveis em todos os tipos de visualização, com configurações adicionais disponíveis para cada visualização. <ul><li>**Tipo de visualização**: um seletor suspenso que permite apresentar dados de um determinado tipo de análise de uma maneira diferente.</li><li>**Configurações do gráfico**: Ajuste o que seu gráfico e sua tabela exibem. As opções disponíveis dependem da visualização selecionada.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas da análise. Você também pode selecionar um intervalo para exibições de tendências, como diariamente, semanalmente ou mensalmente.</li><li>**Insights**: insights contextuais dependendo da análise que você visualiza. Você pode ir para insights adicionais usando as setas ou mostrar ou ocultar esses insights usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png) | Menu | Comandos no canto superior direito da análise guiada que fornecem ações abrangentes para sua análise.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que a análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também são alterados.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal será exibida solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal é exibida solicitando um novo nome e descrição.</li><li>**Abrir no Espaço de trabalho**: recria a análise guiada atual no Analysis Workspace. O projeto do Espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto se trabalha na análise guiada. É uma cópia da análise e não permanece em sincronia com a análise guiada original depois de aberta. Use esse comando quando quiser enviar para a equipe de analistas ou se aprofundar nos dados além do que a Análise guiada permite.</li><li>**Copiar para a área de transferência**: copia o gráfico para a área de transferência, para ser colado em outros aplicativos. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar PNG**: baixa o gráfico como um `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar CSV**: baixa os dados da tabela como um `.csv`. O painel de consulta e o gráfico não estão incluídos no arquivo.</li></ul> |

{style="table-layout:auto"}

## Provisionamento

A análise guiada faz parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics. Se a organização quiser começar a usar esse conjunto de recursos, entre em contato com a equipe de conta do Adobe.

Depois que sua organização for provisionada para usar a Análise guiada, os administradores do perfil de produto poderão adicionar ou remover o acesso a ela na Adobe Admin Console.

1. Faça logon no [Adobe Admin Console](https://adminconsole.adobe.com).
1. Selecionar **[!UICONTROL Customer Journey Analytics]** na lista de produtos.
1. Selecione o perfil de produto desejado para as permissões que deseja editar.
1. Clique em **[!UICONTROL Permissões]** e clique em **[!UICONTROL Editar]** em [!UICONTROL Ferramentas de relatório].
1. Clique no ícone de adição ao lado de **[!UICONTROL Acesso guiado à análise]** na lista de [!UICONTROL Itens de permissão disponíveis], que o adiciona à lista de [!UICONTROL Itens de permissão incluídos].
1. Clique em **[!UICONTROL Salvar]**.

>[!TIP]
>
>Alguns administradores preferem ativar a Análise guiada e desativar o Analysis Workspace para novos usuários para o Customer Journey Analytics. Quando esses usuários amadurecerem com o produto e seus dados organizacionais, você poderá habilitar o acesso ao Analysis Workspace.
