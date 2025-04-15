---
title: Como definir as preferências do usuário no Analysis Workspace
description: É possível definir preferências gerais e de projeto para usuários.
feature: Workspace Basics
exl-id: 6a934be7-0612-41ff-964e-77abc0b1efda
solution: Customer Journey Analytics
role: User
source-git-commit: ab78583eb36d6158630724fbab9eb8148bcdbe23
workflow-type: tm+mt
source-wordcount: '3632'
ht-degree: 98%

---

# Preferências do usuário

Você pode gerenciar as configurações ou preferências do usuário do Analysis Workspace e os componentes relacionados de todos os novos projetos ou painéis que criar. Os projetos e painéis existentes não são afetados.

## Atualizar preferências

Você pode atualizar suas preferências das seguintes maneiras:

- Selecione ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferências]** na interface principal do espaço de trabalho.
- Selecione **[!UICONTROL Projeto]** > **[!UICONTROL Preferências do usuário]** no menu ao trabalhar em um projeto do espaço de trabalho.
- Selecione **[!UICONTROL Componentes]** > **[!UICONTROL Preferências]** na barra superior principal do Customer Journey Analytics (disponível somente para admins de produtos).

## Configurar preferências

Você pode configurar as seguintes preferências:

### Preferências gerais

As preferências gerais se aplicam à experiência do Customer Journey Analytics no navegador. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

| Preferência | Opções |
| --- | --- |
| **[!UICONTROL Página de destino]** | Escolha qual página será exibida por padrão ao acessar o Customer Journey Analytics: <ul><li>Lista de projetos (padrão)</li><li>Projeto em branco</li><li>Análise guiada de tendências em branco</li><li>Projeto específico selecionado em uma lista</li></ul> |
| **[!UICONTROL Dicas]** | Exibe dicas em uma caixa azul na área inferior direita do Analysis Workspace. <p>Essa opção está ativada por padrão.</p> |
| **[!UICONTROL Componentes exibidos em grupos do painel esquerdo]** | Escolha quantos de cada grupo de componentes serão exibidos no menu Componentes no painel esquerdo. <p>Se você escolher 0 para um grupo de componentes, esse grupo não estará mais acessível no painel esquerdo.</p><p>Por padrão, 5 componentes são exibidos para cada um dos seguintes grupos de componentes:</p> <ul><li>Dimensões</li><li>Métricas</li><li>Filtros</li><li>Intervalos de datas</li></ul> <p>Para obter mais informações sobre Componentes no Analysis Workspace, consulte [Visão geral dos componentes](/help/components/overview.md).</p> |

### Preferências da organização IMS {#ims-organization-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Permitir compartilhamento apenas com usuários do espaço de trabalho"
>abstract="Quando habilitada, a opção **[!UICONTROL Compartilhar com qualquer pessoa]** não fica mais disponível para usuários que compartilham um projeto do Analysis Workspace. As pessoas que anteriormente receberam acesso a um projeto por meio dessa opção de compartilhamento não podem mais acessar o projeto."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Exigir autenticação da Experience Cloud"
>abstract="Quando habilitada, as pessoas que recebem acesso a um projeto pela opção “Compartilhar com qualquer pessoa” no Analysis Workspace devem se autenticar usando suas credenciais da Experience Cloud."

<!-- markdownlint-enable MD034 -->


Você pode atualizar as preferências da empresa que se aplicam a todos os usuários e projetos em sua organização. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Compartilhamento de projeto** | | |
| | Permitir compartilhamento apenas com usuários do espaço de trabalho | Quando esta opção está habilitada, os usuários da sua organização não podem ver a opção **[!UICONTROL Compartilhar com qualquer pessoa]** no menu **[!UICONTROL Compartilhar]**. Isso significa que os usuários não podem compartilhar projetos com pessoas que não têm uma conta do Analysis Workspace em sua organização, conforme descrito em [Compartilhar um projeto com qualquer pessoa (não exigir logon)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md).<br/>Esta opção está desabilitada por padrão para todas as organizações (o que significa que os usuários podem compartilhar projetos com pessoas de fora da organização), exceto para clientes que tenham uma licença do Healthcare Shield. <p>Considere o seguinte ao habilitar ou desabilitar essa opção:<ul><li>Ao habilitá-la, as pessoas que anteriormente receberam acesso a um projeto por meio da opção [!UICONTROL Compartilhar com qualquer pessoa] não poderão mais acessar o projeto.</li><li>Se esta opção for habilitada (para permitir o compartilhamento somente com usuários do espaço de trabalho) e depois desabilitada (para permitir o compartilhamento com qualquer pessoa), as pessoas que receberam acesso a um projeto anteriormente por meio da opção [!UICONTROL Compartilhar com qualquer pessoa] não recuperarão automaticamente o acesso ao projeto. Neste caso, o usuário que compartilhou o projeto deve habilitar a opção [!UICONTROL **Manter o link ativo**] ao compartilhar um projeto com qualquer pessoa **([!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer pessoa]**), conforme descrito em [Compartilhar um projeto com qualquer pessoa (não exigir logon)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md).</li><li>**Para clientes com uma licença do Healthcare Shield:** essa opção está habilitada por padrão e não pode ser desabilitada. Antes de desabilitar esta opção para que os usuários possam usar a opção [!UICONTROL Compartilhar com qualquer pessoa], você primeiro precisa adicionar a permissão [!UICONTROL Compartilhar links de projeto com qualquer pessoa] (localizada em [!UICONTROL Ferramentas de relatórios]) no Adobe Admin Console. Após adicionar a permissão, você poderá desabilitar essa opção e, em seguida, aceitar o aviso legal resultante. Para obter informações sobre como adicionar uma permissão no Admin Console, consulte [Gerenciar permissões de produto no Admin Console](https://helpx.adobe.com/br/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Exigir autenticação da Experience Cloud | Quando habilitada, as pessoas que recebem acesso a um projeto pela opção “Compartilhar com qualquer pessoa” no Analysis Workspace devem se autenticar usando suas credenciais da Experience Cloud.<p>Após habilitar essa opção, sempre que um usuário compartilhar um projeto usando [!UICONTROL Compartilhar com qualquer pessoa], a opção [!UICONTROL Exigir autenticação da Experience Cloud] será habilitada na caixa de diálogo de compartilhamento e não poderá ser desabilitada pelo usuário que está compartilhando o projeto. Para obter informações sobre como compartilhar projetos com qualquer pessoa, consulte [Compartilhar um projeto com qualquer pessoa (não exigir logon)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md). <p> <p>Considere o seguinte ao habilitar essa opção: <ul><li>Ao habilitar esta opção, todos os projetos que foram compartilhados anteriormente com a opção [!UICONTROL Compartilhar com qualquer pessoa] sem habilitar [!UICONTROL Exigir autenticação da Experience Cloud] serão desativados.<p>Se esta opção for habilitada (para exigir autenticação da Experience Cloud) e depois desabilitada (para permitir que qualquer pessoa com o link acesse o projeto), as pessoas que receberam acesso a um projeto anteriormente por meio da opção [!UICONTROL Compartilhar com qualquer pessoa] não recuperarão automaticamente o acesso ao projeto. Neste caso, o usuário que compartilhou o projeto deve habilitar a opção [!UICONTROL Manter o link ativo]* ao compartilhar um projeto com qualquer pessoa **([!UICONTROL Compartilhar]** > **[!UICONTROL Compartilhar com qualquer pessoa]** > **[!UICONTROL Manter o link ativo]**), conforme descrito em [Compartilhar um projeto com qualquer pessoa (não exigir logon)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) em [Compartilhar projetos](/help/analysis-workspace/curate-share/share-projects.md).</li><li>Essa opção só estará disponível se o recurso de logon único (SSO) estiver implementado em sua organização. Para obter informações sobre como admins de sistema podem habilitar o SSO na sua organização, consulte [Configuração de identidade e logon único](https://helpx.adobe.com/br/enterprise/using/set-up-identity.html).</p><p>Se o SSO estiver configurado na sua organização, verifique se há algum tipo de criação automática de contas implementado no console. Normalmente, isso é configurado por um(a) admin de sistema, conforme descrito em [Habilitar criação automática de conta](https://helpx.adobe.com/br/enterprise/using/automatic-account-creation.html).</li><li>Se sua organização tiver uma licença do Healthcare Shield, essa opção será habilitada por padrão e não poderá ser desabilitada.</li></ul> |

{style="table-layout:auto"}

### Preferências de projetos e análises {#project-and-analysis-preferences}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Paleta categórica"
>abstract="Aplicado a muitas visualizações no Analysis Workspace e em análises guiadas. Cada cor representa um valor categórico diferente."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Paleta divergente"
>abstract="Aplicado à tabela de coorte no Analysis Workspace e em análises guiadas de crescimento de usuários. Esta paleta possui um significado numérico com dois extremos e uma linha de base no meio."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Paleta sequencial"
>abstract="Aplicado à análise guiada de tendências de frequência (barras empilhadas). Esta paleta possui um significado numérico que vai do claro ao escuro."

<!-- markdownlint-enable MD034 -->


É possível personalizar essas preferências para todos os novos projetos e painéis do Analysis Workspace, bem como para novas análises guiadas. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para projetos individuais no Analysis Workspace, conforme descrito em [Visão geral do projeto](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Exibir** | | |
|  | [Densidade da exibição](/help/analysis-workspace/build-workspace-project/view-density.md) | Escolha a quantidade de conteúdo a ser exibido na tela reduzindo o preenchimento vertical do painel à esquerda, das tabelas de forma livre e tabelas de coorte. <ul><li>Compacto</li><li>Confortável</li><li>Expandido (padrão)</li></ul> |
| | [Paleta de cores](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Escolha as paletas de cores de visualização que serão usadas no Analysis Workspace e na análise guiada. <ul><li> Paleta categórica: aplicada a muitas visualizações no Analysis Workspace e na análise guiada. Cada cor representa um valor categórico distinto. Escolha entre as opções fornecidas pela Adobe ou insira uma paleta personalizada definida por valores hexadecimais delimitados por vírgulas.</li><li> Paleta divergente: aplicada à tabela de coorte no Analysis Workspace e na análise guiada de crescimento de usuários. Esta paleta contém um significado numérico com dois extremos e uma linha de base no meio.<li> Paleta sequencial: aplicada à análise guiada de tendências de frequência (barra empilhada). Esta paleta contém um significado numérico do claro para o escuro.</li></ul> |
| **Dados** | | |
|  | [Visualização de dados](/help/analysis-workspace/c-panels/panels.md#data-view) | Escolha de onde as tabelas e as visualizações derivam seus dados. <ul><li>Mais recente (padrão)</li><li>Visualização de dados específica selecionada em uma lista</li></ul> |
|  | [Calendário](/help/analysis-workspace/c-panels/panels.md#calendar) | Selecione de uma lista de: <ul><li>Intervalos fornecidos pela Adobe (o padrão é Este mês)</li><li>Você pode habilitar a opção [!UICONTROL Tornar os componentes de intervalo de datas relativos ao calendário do painel por padrão].</li></ul> |
|  | [Tipo de painel](/help/analysis-workspace/c-panels/panels.md#panel-types) | <ul><li>Forma livre (padrão)</li><li>Em branco</li><li>Insights rápidos</li></ul> |
|  | Contagem de instâncias | Habilite a opção [!UICONTROL Contar instâncias repetidas] para especificar se as instâncias repetidas devem ser contadas em relatórios. Por exemplo, quando essa opção está habilitada, várias visualizações de página consecutivas na mesma página são tratadas como várias visualizações de página. Quando desabilitada, as várias visualizações de página consecutivas na mesma página contam como uma única visualização de página. <p>**Observação:** essa configuração afeta apenas determinadas métricas (como Sessões) e não se aplica a visualizações de fluxo ou fallout.</p> |
|  | Formato de número | <ul><li>1.000,00 (padrão)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Caractere separador do CSV | <ul><li>Vírgula (padrão)</li><li>Ponto e vírgula</li><li>Dois-pontos</li><li>Estágio</li><li>Ponto</li><li>Espaço</li><li>Tabulação</li></ul> |
|  | Mostrar anotações | Escolha se as anotações estão visíveis em seus projetos. Para obter mais informações sobre anotações, consulte [Visão geral de anotações](/help/components/annotations/overview.md). |


### Preferências da tabela de forma livre {#freeform-table-preferences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Mostrar anomalias"
>abstract="Selecionar a opção **[!UICONTROL Mostrar anomalias]** executará automaticamente a detecção de anomalias na primeira coluna de métrica adicionada a uma visualização de tabela de forma livre de série temporal."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Mostrar previsão"
>abstract="Selecionar **[!UICONTROL Mostrar previsão]** preverá automaticamente a primeira coluna de métrica adicionada a uma visualização de tabela de forma livre de série temporal."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Métrica de tabela padrão"
>abstract="Selecione a métrica padrão para usar em tabelas de forma livre. Se a exibição de dados selecionada não contiver a métrica padrão escolhida, a tabela utilizará automaticamente outra métrica principal."


<!-- markdownlint-enable MD034 -->



Você pode personalizar as preferências da tabela de forma livre para todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para tabelas individuais.

Selecione os títulos da seção vinculada para obter mais informações e contexto sobre as preferências disponíveis.

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Tabela** | | |
| | Tipo de tabela | <ul><li>Forma livre</li><li>Construtor de tabelas</li></ul> |
| | Métrica de tabela padrão | <ul><li>Ocorrências</li><li>Visitantes únicos</li><li>Visitas</li></ul> |
| | Dimensão padrão da tabela | Escolha de Minuto, Hora, Dia, Semana, Mês, Trimestre ou Ano. |
| | Alinhar datas | Selecione essa opção para alinhar as datas de cada coluna para que todas iniciem na mesma linha. |
| **[Coluna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Quebrar linha do texto do cabeçalho | Permite quebrar o texto de cabeçalho em tabelas de forma livre para tornar os cabeçalhos mais legíveis e as tabelas mais compartilháveis. Essa opção é útil para renderização de .pdf e para métricas com nomes compridos. Ativado por padrão. |
| | Exibir totais | Normalmente esse total é uma parte do [!UICONTROL Total geral] ou igual a ele. Ele reflete todos os segmentos de tabela aplicados na tabela de forma livre, incluindo a opção [!UICONTROL Não incluir]. |
| | Mostrar totais gerais | Esse total representa todos os eventos coletados e às vezes é chamado de “total de visualizações de dados”. Quando um segmento é aplicado no nível do painel ou na tabela de forma livre, esse total é ajustado para refletir todos os eventos que correspondem aos critérios do segmento. O total geral não é compatível com tabelas e detalhamentos com [linhas estáticas](/help/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Mostrar minigráfico | Mostrar ou ocultar gráficos de linha na parte inferior do gráfico. Quando oculta, a legenda será alterada para não mais fazer referência visual às linhas. |
| | Número | Determina se uma célula exibe ou oculta o valor numérico para a métrica. Por exemplo, se a métrica for Exibições de página, o valor numérico será o número de exibições de página para o item da linha. |
| | Porcentagem | Determina se uma célula exibe ou oculta o valor percentual para a métrica. Por exemplo, se a métrica for Exibições de página, o valor percentual será o número de exibições de página para o item da linha dividido pelo total de exibições de página para a coluna.  Observação: podemos apresentar percentuais maiores que 100%, para maior precisão. Também fixamos o limite superior como 1.000% para garantir que as colunas possam aumentar em largura. |
| | Mostrar anomalias <!-- This setting was moved from the "Project" tab. this is already in the tool/docs under "Freeform table, But the doc doesn't give a definition. --> | Determina se a detecção de anomalias é executada nos valores desta coluna. |
| | Mostrar previsão | Determina se os valores de previsão aparecem automaticamente na primeira coluna da métrica em qualquer tabela de forma livre de série temporal que você criou. |
| | Interpretar o zero como valor inexistente | Para células com valor 0, determina se exibirá um 0 ou uma célula em branco. Isso é útil para observar dados diários de um mês que ainda não tenha terminado.  Em vez de mostrar 0 para as datas futuras, pode-se exibir células em branco. Essa configuração também aplica-se a gráficos (ou seja, eles não exibem uma linha ou uma barra com valores de 0 quando essa configuração estiver selecionada). |
| | Histórico | Determina se uma célula exibe ou oculta todas as formatações de célula, incluindo o gráfico de barras e a formatação condicional <ul><li>Gráfico de barras</li> Exibe um gráfico de barras horizontal que representa o valor da célula relativo ao total da coluna. <li>Formatação condicional</li>Para obter mais informações sobre formatação condicional, consulte “Formatação condicional” em [Configurações de coluna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)</ul> |
| | Visualização da célula | Mostra uma visualização de como cada célula é exibida com a aplicação das opções de formatação atuais selecionadas. |
| **[Linha](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Detalhamento por posição | Selecione essa opção se desejar que o detalhamento permaneça com a posição do item em vez do próprio item. Para obter mais informações sobre detalhamentos, consulte [Analisar dimensões](/help/components/dimensions/t-breakdown-fa.md). |
| | Cálculo percentual | <ul><li>Coluna</li><li>Linha</li></ul> |
| | Totais de coluna (somente linhas estáticas) | <ul><li>Exibir soma das linhas: mostra a soma dos itens de linha individuais </li><li>Exibir total geral: mostra a soma de linhas desduplicadas.</li></ul> |

### Preferências de visualizações {#visalization-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultflowcontainer"
>title="Container padrão"
>abstract="Selecione o container padrão a ser usado para visualizações de [!UICONTROL fluxo]. Se a visualização de dados selecionada não contiver o container padrão escolhido, a visualização de [!UICONTROL fluxo] utilizará automaticamente outro container principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultfalloutcontainer"
>title="Container padrão"
>abstract="Selecione o container padrão a ser usado para as visualizações de [!UICONTROL fallout]. Se a visualização de dados selecionada não contiver o container padrão escolhido, a visualização de [!UICONTROL fallout] utilizará automaticamente outro container principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulthistogramcountingmethod"
>title="Método de contagem padrão"
>abstract="Selecione o método de contagem padrão a ser usado para visualizações de [!UICONTROL histograma]. Se a visualização de dados selecionada não contiver o método de contagem padrão escolhido, a visualização de [!UICONTROL histograma] utilizará automaticamente outro método de contagem principal."

>[!CONTEXTUALHELP]
>id="workspace_prefs_defaultjourneycanvascontainer"
>title="Container padrão"
>abstract="Selecione o container padrão a ser usado para visualizações de [!UICONTROL tela da jornada]. Se a visualização de dados selecionada não contiver o container padrão escolhido, a visualização de [!UICONTROL tela da jornada] utilizará automaticamente outro container principal."


Você pode atualizar as preferências de visualização para todos os novos projetos criados no Analysis Workspace. Para obter informações sobre como acessar essas preferências, consulte [Atualizar preferências](#update-preferences).

Algumas dessas mesmas preferências também podem ser personalizadas para visualizações individuais.

Selecione os títulos da seção vinculada para obter mais informações e contexto sobre as preferências disponíveis.

| Seção | Preferência | Opções |
| --- | --- | --- |
| **Padrões gerais** | | |
| | Porcentagens | Exibe valores em porcentagens para todas as visualizações. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para todas as visualizações. |
| | Limite máximo de itens | Reduz o número de itens no eixo X para todas as visualizações. Isso pode ser útil se você tiver um conjunto de dados grande. |
| | Exibir eixo duplo (quando aplicável) | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Normalização (quando aplicável) | Força as métricas para proporções iguais. Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Ancorar o eixo Y em zero | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |
| | Ancorar anomalias para dimensionar o eixo Y | O eixo y será dimensionado usando valores de anomalias. |
| **[Linha](/help/analysis-workspace/visualizations/line.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações de linha. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização de linha. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização de linha. Isso pode ser útil se você tiver um conjunto de dados grande. |
| | Exibir eixo duplo (quando aplicável) | Somente se aplica se você tiver duas métricas. Você pode ter um eixo Y à esquerda (para uma métrica) e outro à direta (para a outra métrica). Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Normalização (quando aplicável) | Força as métricas para proporções iguais. Isso é útil quando métricas projetadas têm magnitudes muito diferentes. |
| | Mostrar eixo X | Exibe o eixo x no gráfico de linha. |
| | Mostrar eixo Y | Exibe o eixo y no gráfico de linha. |
| | Âncora do eixo Y | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |
| | Permitir que as anomalias dimensionem o eixo Y | Se você tiver várias métricas em um gráfico, é necessário passar o mouse sobre cada anomalia para ver a faixa de confiança para essa métrica. Para tornar a visualização mais legível, o intervalo de confiança da Detecção de anomalias não dimensiona automaticamente o eixo y. Essa opção permite que o intervalo de confiança dimensione a visualização. <p>Para obter mais informações, consulte [Exibir anomalias no Analysis Workspace](/help/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| | Permitir que a previsão mude a escala do eixo Y | Se você tiver valores de previsão fora dos limites superior e inferior dos valores históricos, o eixo y não será dimensionado automaticamente de acordo com esses valores previstos. Quando ativada, essa opção dimensiona corretamente o eixo y para os valores previstos. |
| | Mostrar mín. | Sobreponha um rótulo de valor mínimo para realçar rapidamente os vales em uma métrica. Observação: os valores mín. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão. |
| | Mostrar máx. | sobrepõe um rótulo de valor máximo para destacar rapidamente os picos em uma métrica. Observação: os valores máx. são derivados dos pontos de dados visíveis na visualização, não do conjunto completo de valores em uma dimensão. |
| | Mostrar linha de tendência | Mostrar uma regressão ou uma linha de tendência média móvel para a sua série de linhas. As linhas de tendência ajudam a descrever um padrão mais claro nos dados. |
| **[Coorte](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularidade | Para visualizações de tendências, você pode alterar a granularidade de tempo (dia, semana, mês, trimestre ou ano). Essa alteração também se aplica à tabela de fonte de dados. |
| | Mostrar somente a porcentagem | Remove o valor do número e mostra somente a porcentagem. |
| | Arredondar porcentagem ao inteiro mais próximo | Arredonda o valor percentual para o inteiro mais próximo em vez de mostrar o valor decimal. |
| | Mostrar linha de porcentagem média | Insere uma nova linha na parte superior da tabela e adiciona a média para os valores dentro de cada coluna. |
| **[Gráficos de combinação](/help/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Mostrar eixo X | Exibe o eixo x no gráfico de combinação. |
| | Mostrar eixo Y | Exibe o eixo y no gráfico de combinação. |
| | Exibir barras nas linhas | Mostrar barras em linhas nos gráficos de combinação. |
| **[Resumo da métrica principal](/help/analysis-workspace/visualizations/key-metric.md)** | | |
| | Tipo de exibição de resumo | <ul><li>Enfatizar a variação percentual</li><li>Enfatizar o valor do número</li></ul> |
| | Mostrar linhas cintilantes | Mostrar ou ocultar gráficos de linha na parte inferior do gráfico. Quando oculta, a legenda será alterada para não mais fazer referência visual às linhas. |
| | Mostrar máximo e mínimo em sparklines | Mostrar valores mínimos e máximos em gráficos de linha primários e de comparação. |
| | Mostrar comparação | Mostrar dados de comparação. Quando ocultos, o gráfico de linha de comparação e os objetos de alteração de resumo não serão exibidos. |
| | Opções de valor numérico | Na seção [!UICONTROL **Resumo das métricas principais**] <ul><li>Mostrar variação percentual</li><li>Mostrar diferença bruta</li>Diferença bruta entre o valor total da métrica no intervalo de datas principal e o intervalo de datas secundário</ul> |
| **[Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Contêiner | Permite alternar entre **[!UICONTROL Sessão]** e **[!UICONTROL Pessoa]** para analisar a definição de caminho da pessoa. O padrão é **[!UICONTROL Pessoa]**. Essas configurações ajudam você a entender o engajamento de pessoas (em sessões) ou restringir a análise a uma única sessão. <p>Estas são as opções disponíveis:</p> <ul><li>Sessão</li><li>Pessoa</li></ul> |
| **[Fluxo](/help/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Contêiner | Na seção [!UICONTROL **Fluxo**] <ul><li>Sessão</li><li>Pessoa</li></ul> |
| | Rótulos de quebra de linha | Normalmente, os rótulos nos Elementos de fluxo são truncados para não poluir visualmente a tela, mas é possível tornar todos os rótulos visíveis ao selecionar esta caixa. Padrão = desmarcado. |
| | Incluir instâncias repetidas | As visualizações de fluxo são baseadas em instâncias de uma dimensão. Essa configuração oferece a opção de incluir ou excluir instâncias repetidas, por exemplo, recarregamentos de página. No entanto, as repetições não podem ser removidas das Visualizações de fluxo que incluem dimensões com vários valores, como listVars, listProps, s.product, eVars de merchandising etc. Padrão = desmarcado. |
| | Mostrar dicas de ferramentas | Determina se as dicas de ferramentas que contêm dados de nó são exibidas ao passar o cursor do mouse sobre nós individuais em uma visualização de fluxo. |
| | Número de colunas | Determina quantas colunas você deseja incluir no diagrama de Fluxo. |
| | Itens expandidos por coluna | Quantos itens você deseja em cada coluna. |
| **Gráficos empilhados** | | |
| | 100% empilhada | Essa configuração de visualizações de área empilhada, barra empilhada ou barra horizontal empilhada transforma o gráfico em uma visualização “100% empilhada”.  <p>Para obter mais informações, consulte [Barra e Barra empilhada](/help/analysis-workspace/visualizations/bar.md).</p> |
| **[Histograma](/help/analysis-workspace/visualizations/histogram.md)** | | |
| | Número de grupos | Escolha o número de intervalos de datas (compartimentos) na visualização. O número máximo de grupos é 50. <p>Para obter mais informações, consulte [Histograma](/help/analysis-workspace/visualizations/histogram.md).</p> |
| | Método de contagem | Escolha entre as seguintes opções: <ul><li>Ocorrência</li><li>Sessão</li><li>Pessoa</li></ul> <p>Por exemplo, quando usado em conjunto com visualizações de página, você pode escolher visualizações de página por visitante, por visita ou por evento. Para ocorrências, “Ocorrências” é usada como a métrica do eixo “y” na tabela de forma livre.</p> |
| **[Alteração de resumo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valor | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Mudança percentual</li><li>Diferença bruta</li></ul> |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Resumo de alterações. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização Resumo da alteração. |
| **[Número do resumo](/help/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Número de resumo. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização Número de resumo. |
| | Valor de resumo por | Escolha entre Máx., Mín., Média, Mediana e Soma. |
| | Abreviar valor | Na seção [!UICONTROL **Número de resumo**] |
| **[Mapas de árvore](/help/analysis-workspace/visualizations/treemap.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações do Mapa de árvore. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização do Mapa de árvore. Isso pode ser útil se você tiver um conjunto de dados grande. |
| **[Venn](/help/analysis-workspace/visualizations/venn.md)** | | |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização de Venn. |
| **[Dispersão](/help/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Porcentagens | Exibe valores em porcentagens para as visualizações de dispersão. |
| | Legenda visível | Permite ocultar o texto detalhado da legenda para a visualização de dispersão. |
| | Limite máximo de itens | Reduz o número de itens no eixo X na visualização de dispersão. Isso pode ser útil se você tiver um conjunto de dados grande. |
| | Ancorar o eixo Y em zero | Se todos os valores exibidos no gráfico forem consideravelmente superiores a zero, o padrão do gráfico tornará a parte inferior do eixo y DIFERENTE DE ZERO. Se marcar esta caixa, o eixo y será forçado a zero (e o gráfico será redesenhado). |

## Restaurar preferências padrão

Você pode restaurar todas as preferências do usuário para os padrões do sistema. Isso não afeta as preferências do administrador na guia Empresa.

Esta ação não pode ser desfeita.

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] **>** [!UICONTROL **Preferências**] no menu superior. Ou selecione **[!UICONTROL Projeto]** > **[!UICONTROL Configurações de usuário]** no menu do espaço de trabalho.

1. No canto superior direito, selecione **[!UICONTROL Restaurar padrões]**.

1. Selecione **[!UICONTROL Restaurar padrões]** em **[!UICONTROL Restaurar configurações padrão do sistema]**.

## [!UICONTROL Tema escuro]

Se preferir ter um fundo escuro para a interface de usuário do Customer Journey Analytics, é possível alternar para [!UICONTROL Tema escuro].

1. Clique no ícone de usuário da Experience Cloud na parte superior direita.

   ![tema escuro](assets/dark-theme.png)

1. Habilitar **[!UICONTROL Tema escuro]**.

