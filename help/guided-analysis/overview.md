---
title: Visão geral da análise guiada
description: Um método de análise de dados no Customer Journey Analytics que permite que as equipes de produtos gerem relatórios e insights facilmente.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 1%

---

# Visão geral da análise guiada

{{release-limited-testing}}

A análise guiada é um formato de relatório que permite que as equipes de produtos atendam rapidamente às suas necessidades de dados para que possam tomar mais decisões de produto orientadas por dados. Equipes multifuncionais podem se conectar em tempo real para usar e entender esses relatórios.

Semelhante aos cartões de pontuação do Analysis Workspace e Mobile, um relatório de análise guiada usa dados de um [Visualização de dados](../data-views/data-views.md), que faz referência aos dados no Adobe Experience Platform por meio de uma [Conexão](../connections/overview.md). Todos os relatórios criados na análise guiada podem ser transferidos facilmente para a Analysis Workspace para pesquisa adicional.

Os relatórios de análise guiada apresentam atualmente três tipos de análise: [Funil](analysis-types/funnel.md), [Tendências](analysis-types/trends.md), e [Crescimento do usuário](analysis-types/user-growth.md). Cada um desses tipos de análise tem vários tipos de visualização, que fornecem insights adicionais para cada um desses relatórios.

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
| [Captura de tela do painel de consulta] | Painel de consulta | Configure os componentes desejados que compõem um relatório. Tipos de análise diferentes compartilham várias opções de consulta; se dois tipos de análise compartilham opções de consulta, elas são transferidas ao alternar tipos de análise. Consulte [Tipos de análise](analysis-types/overview.md) para obter mais informações sobre as opções de consulta para cada tipo de análise respectivo. |
| [Captura de tela do gráfico] | Gráfico | Uma visualização dos dados retornados com base na entrada do painel de consulta e nas configurações. A visualização exibida depende do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do [Tipo de análise](analysis-types/overview.md) acima do painel de consulta. |
| [Captura de tela da tabela] | Tabela | Uma representação em tabela dos dados retornados com base na entrada do painel de consulta e nas configurações. As colunas na tabela dependem do tipo de exibição acima do gráfico. Os tipos de visualização disponíveis dependem do [Tipo de análise](analysis-types/overview.md) acima do painel de consulta. |
| [Captura de tela das configurações] | Configurações  | Várias opções acima do gráfico que permitem personalizar como o gráfico e a tabela retornam dados.<ul><li>**Tipo de visualização**: um seletor suspenso que permite apresentar dados para um determinado [Tipo de análise](analysis-types/overview.md) de forma diferente. Cada tipo de análise tem pelo menos dois tipos de visualização.</li><li>**Configurações do gráfico**: ajuste a aparência do gráfico e os eventos que deseja usá-lo. As opções disponíveis dependem do tipo de visualização selecionado.</li><li>**Intervalo de datas**: um seletor de calendário que permite determinar o intervalo de datas do relatório. Alguns tipos de análise também permitem intervalos, como diário, semanal ou mensal.</li><li>**Insights**: fornece insights contextuais dependendo do relatório que você visualiza. Você pode mostrar ou ocultar esses insights usando o ícone de lâmpada na parte superior direita.</li></ul> |
| [Captura de tela do menu de análise] | Menu Análise | Comandos no canto superior direito da Análise guiada que fornecem ações abrangentes.<ul><li>**Seletor de visualização de dados**: altere a visualização de dados que essa análise usa. Ao alterar a visualização de dados, os componentes disponíveis no painel de consulta também são alterados.</li><li>**Salvar**: salva a análise. Se você estiver salvando uma nova análise, uma janela modal será exibida solicitando um nome e uma descrição.</li><li>**Salvar como**: salva a análise separadamente da análise atual, criando uma cópia. Uma janela modal é exibida solicitando um novo nome e descrição.</li><li>**Abrir no Espaço de trabalho**: recria a análise guiada atual no Analysis Workspace. O projeto do Espaço de trabalho é criado em uma nova guia, evitando interrupções enquanto se trabalha na análise guiada. Use este comando quando a Análise guiada não oferecer a flexibilidade ou o insight específico que você está procurando. Por exemplo, você deseja uma [Tendências](analysis-types/trends.md) relatório que usa Sessões para um segmento e Pessoas para outro segmento.</li><li>**Baixar PNG**: baixa o gráfico como um `.png`. O painel de consulta e a tabela não estão incluídos no gráfico.</li><li>**Baixar SVG**: baixa o gráfico como um `.svg`. O painel de consulta e a tabela não estão incluídos no gráfico.</li></ul> |

{style="table-layout:auto"}

## Provisionamento

A análise guiada faz parte do Adobe Product Analytics, que é um complemento pago do Customer Journey Analytics. Se sua organização quiser começar a usar esse recurso, entre em contato com a equipe de conta do Adobe.

O Adobe planeja fornecer permissões específicas para a Análise guiada no futuro.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
