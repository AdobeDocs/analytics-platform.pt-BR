---
title: Visão geral da análise guiada
description: Um método de análise de dados no Customer Journey Analytics que permite que as equipes de produtos gerem relatórios e insights facilmente.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 10%

---

# Visão geral da análise guiada

{{release-limited-testing}}

A análise guiada é um formato de relatório que permite que as equipes de produtos atendam rapidamente às suas necessidades de dados para que possam tomar mais decisões de produto orientadas por dados. Equipes multifuncionais podem se conectar em tempo real para usar e entender esses relatórios.

Semelhante aos cartões de pontuação do Analysis Workspace e Mobile, um relatório de análise guiada usa dados de um [Visualização de dados](../data-views/data-views.md), que faz referência aos dados no Adobe Experience Platform por meio de uma [Conexão](../connections/overview.md). Todos os relatórios criados na análise guiada podem ser transferidos facilmente para a Analysis Workspace para pesquisa adicional.

A análise guiada fornece várias maneiras de analisar dados. Esses tipos de visualização podem mostrar os mesmos dados de maneiras diferentes, resultando em insights diferentes usando os mesmos eventos e segmentos. Você obtém diferentes painéis de consulta e opções de visualização dependendo do tipo de visualização escolhido. Você pode alternar livremente entre tipos de visualização e qualquer componente do painel de consulta aplicável é transportado se o tipo de visualização for compatível com eles.

A análise guiada categoriza os tipos de visualização em **Tipos de análise**. Os seguintes tipos de análise e visualização estão disponíveis:

| Tipo de análise | Tipo de visualização | Descrição |
| --- | --- | --- |
| Impacto | [Versão](types/release.md) | Compare o desempenho em períodos iguais antes e depois do lançamento. |
| Impacto | [Primeiro uso](types/first-use.md) | Medir o impacto do uso de recursos pela primeira vez em indicadores-chave. |
| Funil | [Atrito](types/friction.md) | Comparar taxas de conversão entre etapas. |
| Funil | [Tendências de conversão](types/conversion-trends.md) | Acompanhe as alterações nas taxas de conversão ao longo do tempo. |
| Crescimento de usuários | [Ativo](types/active.md) | Meça o crescimento da sua base de usuários. |
| Crescimento de usuários | [Crescimento líquido](types/net-growth.md) | Equilibrar ganhos e perdas do usuário. |
| Tendências | [Uso](types/usage.md) | Medir o engajamento do usuário ao longo do tempo. |

{style="table-layout:auto"}

## Interface

A interface para a análise guiada, independentemente do tipo de análise, inclui os seguintes elementos principais da interface do usuário:

1. **Painel de consulta**: use esse painel à esquerda para criar sua análise.
1. **Gráfico**: após selecionar os eventos, as pessoas ou as etapas desejados, um gráfico é exibido à direita que visualiza os dados.
1. **Tabela**: uma tabela abaixo do gráfico que mostra os números usados na visualização.
1. **Configurações e insights**: vários elementos de interface acima do gráfico que permitem personalizar os dados retornados.

[Captura de tela da interface]

A análise guiada contém as seguintes partes da interface:

| Visualização da interface | Elemento da interface | Descrição |
| --- | --- | --- |
| ![Painel de consulta](assets/query-rail.png) | Painel de consulta | Configure os componentes desejados que compõem um relatório. Tipos de análise diferentes compartilham várias opções de consulta; se dois tipos de análise compartilham opções de consulta, elas são transferidas ao alternar tipos de análise. |
| ![Gráfico](assets/chart.png) | Gráfico | Uma visualização dos dados retornados com base na entrada do painel de consulta e nas configurações. A visualização exibida depende do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do tipo de Análise acima do painel de consulta. |
| ![Tabela](assets/table.png) | Tabela | Uma representação em tabela dos dados retornados com base na entrada do painel de consulta e nas configurações. As colunas na tabela dependem do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do tipo de Análise acima do painel de consulta. |
| ![Configurações de visualização](assets/visualization-settings.png) | Configurações de visualização | Várias opções acima do gráfico que permitem personalizar como o gráfico e a tabela retornam dados.<ul><li>**Tipo de visualização**: um seletor suspenso que permite apresentar dados de um determinado tipo de análise de uma maneira diferente. Cada tipo de análise tem pelo menos dois tipos de visualização.</li><li>**Configurações do gráfico**: ajuste a aparência do gráfico e os eventos que deseja usá-lo. As opções disponíveis dependem do tipo de visualização selecionado.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas do relatório. Alguns tipos de análise também permitem intervalos, como diário, semanal ou mensal.</li><li>**Insights**: fornece insights contextuais dependendo do relatório que você visualiza. Você pode mostrar ou ocultar esses insights usando o ícone de lâmpada na parte superior direita.</li></ul> |
| ![Menu](assets/menu.png) | Menu Análise | Comandos no canto superior direito da Análise guiada que fornecem ações abrangentes.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que essa análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também são alterados.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal será exibida solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal é exibida solicitando um novo nome e descrição.</li><li>**Abrir no Espaço de trabalho**: recria a análise guiada atual no Analysis Workspace. O projeto do Espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto se trabalha na análise guiada. Use este comando quando a Análise guiada não oferecer a flexibilidade ou o insight específico que você está procurando. Por exemplo, você deseja uma [Uso](types/usage.md) relatório que usa Sessões para um segmento e Pessoas para outro segmento.</li><li>**Baixar PNG**: baixa o gráfico como um `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar SVG**: baixa o gráfico como um `.svg`. O painel de consulta e a tabela não estão incluídos no gráfico.</li></ul> |

{style="table-layout:auto"}

## Provisionamento

A análise guiada faz parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics. Se sua organização quiser começar a usar esse recurso, entre em contato com a equipe de conta do Adobe.

Depois que sua organização for provisionada para usar a Análise guiada, os administradores do perfil de produto poderão conceder acesso a ela na Adobe Admin Console.

1. Faça logon no [Adobe admin console](https://adminconsole.adobe.com).
1. Selecionar **[!UICONTROL Customer Journey Analytics]** na lista de produtos.
1. Selecione o perfil de produto desejado para editar permissões.
1. Clique em **[!UICONTROL Permissões]** e clique em **[!UICONTROL Editar]** em [!UICONTROL Ferramentas de relatório].
1. Clique no ícone de adição ao lado de **[!UICONTROL Acesso guiado à análise]** na lista de [!UICONTROL Itens de permissão disponíveis] para adicioná-lo à lista de [!UICONTROL Itens de permissão incluídos].
1. Clique em **[!UICONTROL Salvar]**.
