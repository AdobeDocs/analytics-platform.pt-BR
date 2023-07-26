---
title: Visão geral da análise guiada
description: Um método de análise de dados em Customer Journey Analytics que permite que as equipes de produtos obtenham insights de alta qualidade rapidamente. Também conhecido como Product Analytics.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: bbf69470727dae531065972511bcc29eb3f47679
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 8%

---

# Visão geral da análise guiada

o Adobe Product Analytics permite que as equipes de produtos realizem o autoatendimento de dados e insights sobre sua experiência com produtos por meio de fluxos de trabalho de análise guiados, baseados nos dados entre canais do Customer Journey Analytics. A análise guiada é um formato de relatório que permite que as equipes de produtos atendam rapidamente às suas necessidades de dados, para que possam obter insights de alta qualidade rapidamente e tomar mais decisões de produto orientadas por dados. Equipes multifuncionais podem se conectar em tempo real para usar e entender esses relatórios.

Semelhante aos cartões de pontuação do Analysis Workspace e Mobile, um relatório de análise guiada usa dados de um [Visualização de dados](../data-views/data-views.md), que faz referência aos dados no Adobe Experience Platform por meio de uma [Conexão](../connections/overview.md). Todos os relatórios criados na análise guiada podem ser transferidos facilmente para a Analysis Workspace para pesquisa adicional.

A análise guiada fornece várias maneiras de analisar e visualizar dados. Os tipos de exibição podem mostrar os mesmos dados de maneiras diferentes, resultando em insights diferentes usando os mesmos eventos e segmentos. Você obtém diferentes painéis de consulta e configurações de visualização dependendo da visualização escolhida. Você pode alternar livremente entre exibições e qualquer componente do painel de consulta aplicável é transportado se a exibição for compatível com elas.

A análise guiada categoriza os tipos de visualização em **Tipos de análise**. Os seguintes tipos de análise e visualização estão disponíveis:

| Tipo de análise | Tipo de visualização | Descrição |
| --- | --- | --- |
| [!UICONTROL Impacto] | [Versão](types/release.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| [!UICONTROL Impacto] | [Primeiro uso](types/first-use.md) | Medir o impacto do uso de recursos pela primeira vez em indicadores-chave. |
| [!UICONTROL Funil] | [Atrito](types/friction.md) | Comparar taxas de conversão entre etapas. |
| [!UICONTROL Funil] | [Tendências de conversão](types/conversion-trends.md) | Acompanhe as alterações nas taxas de conversão ao longo do tempo. |
| [!UICONTROL Crescimento de usuários] | [Ativo](types/active.md) | Identifique quem é novo, retido, recorrente ou inativo. |
| [!UICONTROL Crescimento líquido] | [Crescimento líquido](types/net-growth.md) | Você está ganhando ou perdendo usuários? |
| [!UICONTROL Tendências] | [Uso](types/usage.md) | Medir o engajamento do usuário ao longo do tempo. |

{style="table-layout:auto"}

## Access

Se sua organização for provisionada para análise guiada, você poderá acessá-la na página inicial do Customer Journey Analytics.

1. Clique em **[!UICONTROL Análise guiada]** da página inicial para ir diretamente para a página [Exibição de tendências de uso](types/usage.md).

   ![Mosaico da página de aterrissagem](assets/landing-page-tile.png)

1. Clique em **[!UICONTROL Criar novo]** para ver as diferentes opções de exibição e escolher um ponto de partida diferente para a análise.

   ![Criar um novo modal](assets/create-new-modal.png)

## Interface

A interface para a análise guiada, independentemente do tipo de análise, inclui os seguintes elementos principais da interface do usuário:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png) | Painel de consulta | Configure os componentes desejados (eventos, propriedades e segmentos) que compõem uma análise. Cada tipo de análise impõe limites diferentes ao número de eventos e segmentos que podem ser configurados. Se você alternar para um novo tipo de análise, suas seleções de consulta serão mantidas dentro dos limites permitidos para esse tipo de análise. |
| ![Gráfico](assets/chart.png) | Gráfico | Uma visualização dos dados retornados com base na entrada do painel de consulta e nas configurações. A visualização exibida depende da exibição e das configurações acima do gráfico. As exibições disponíveis dependem do tipo de análise acima do painel de consulta. O gráfico também inclui: <ul><li>**Dicas de ferramenta**: passe o mouse sobre qualquer ponto de dados do gráfico para expor uma dica de ferramenta com mais informações.</li><li>**Legenda**: passe o mouse sobre a legenda do gráfico para expor as definições de série, quando disponíveis.</li><li>**Ações de clique**: exponha as próximas ações disponíveis clicando com o botão esquerdo do mouse em qualquer ponto de dados. As opções incluem **Salvar segmento**.</li></ul> |
| ![Tabela](assets/table.png) | Tabela | Uma representação em tabela dos dados retornados com base na entrada do painel de consulta e nas configurações. As colunas na tabela dependem do tipo de exibição acima do gráfico. As exibições disponíveis dependem do tipo de análise acima do painel de consulta. A tabela também inclui: <ul><li>**Ações de clique**: Exponha as próximas ações disponíveis clicando no ícone **[!UICONTROL Mais]** menu. As opções incluem **Salvar segmento**.</li></ul> |
| ![Configurações de visualização](assets/visualization-settings.png) | Configurações de visualização | Várias opções acima do gráfico que permitem personalizar como o gráfico e a tabela retornam dados.<ul><li>**Tipo de visualização**: um seletor suspenso que permite apresentar dados de um determinado tipo de análise de uma maneira diferente.</li><li>**Configurações do gráfico**: Ajuste o que seu gráfico e sua tabela exibem. As opções disponíveis dependem da visualização selecionada.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas da análise. Você também pode selecionar um intervalo para exibições de tendências, como diariamente, semanalmente ou mensalmente.</li><li>**Insights**: insights contextuais dependendo da análise que você visualiza. Você pode ir para insights adicionais usando as setas ou mostrar ou ocultar esses insights usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png) | Menu | Comandos no canto superior direito da Análise guiada que fornecem ações abrangentes para sua análise.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que a análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também são alterados.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal será exibida solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal é exibida solicitando um novo nome e descrição.</li><li>**Abrir no Espaço de trabalho**: recria a análise guiada atual no Analysis Workspace. O projeto do Espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto se trabalha na análise guiada. É uma cópia da análise e não permanece em sincronia com a análise guiada original depois de aberta. Use esse comando quando quiser enviar para a equipe de analistas ou se aprofundar nos dados além do que a Análise guiada permite.</li><li>**Copiar para a área de transferência**: copia o gráfico para a área de transferência, para ser colado em outros aplicativos. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar PNG**: baixa o gráfico como um `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar CSV**: baixa os dados da tabela como um `.csv`. O painel de consulta e o gráfico não estão incluídos no arquivo.</li></ul> |

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
