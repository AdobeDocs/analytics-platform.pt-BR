---
title: Visão geral do uso do produto
description: Visualize insights e relatórios sobre como sua organização usa o Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: dbf4ff28f693085320c3e496ea99eede2ddb17d2
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

---

# Visão geral do uso do produto

O uso do produto oferece à sua organização a capacidade de visualizar dados de análise sobre como sua organização usa o Customer Journey Analytics. Ele está disponível para todas as organizações que usam o Customer Journey Analytics. Após ativados, os seguintes componentes do Adobe Experience Platform são criados e conectados automaticamente para você. Todos esses componentes são de propriedade do sistema, somente leitura e não podem ser editados.

* Um esquema no Adobe Experience Platform
* Um conjunto de dados na Adobe Experience Platform
* Uma conexão no Customer Journey Analytics
* Uma visualização de dados no Customer Journey Analytics

Toda a coleta e configuração de dados é configurada automaticamente para você depois de habilitada. Sempre que um usuário fizer uma ação no Analysis Workspace, essa ação será rastreada e estará disponível para relatórios.

>[!IMPORTANT]
>
>Esse recurso conta para os limites de linha contratuais no Adobe Experience Platform. Certifique-se de que sua organização possa acomodar os dados gerados por esse recurso antes de habilitá-lo.

## Habilitar uso do produto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do Produto]**

Navegar até esta seção da interface no Customer Journey Analytics leva você às [Configurações de dados](data-settings.md), onde é possível habilitar este recurso.

## Dimensões disponíveis

Quando você habilita o Uso de produto, as seguintes dimensões estão disponíveis. Se quiser alterar qualquer configuração de dimensão, crie uma cópia da visualização de dados de propriedade do sistema e use a visualização de dados copiada no Analysis Workspace.

* **[!UICONTROL Nome da Ação]**: o tipo de ação que o usuário executou. É possível usar essa dimensão como qualquer métrica desejada ao criar uma cópia nas configurações de visualização de dados. Os itens de Dimension incluem:
   * [!UICONTROL Adicionar atribuição]
   * [!UICONTROL Adicionar componente]
   * [!UICONTROL Adicionar painel]
   * [!UICONTROL Adicionar visualização]
   * [!UICONTROL Criar nova análise guiada]
   * [!UICONTROL Criar novo projeto]
   * [!UICONTROL Preparar componentes]
   * [!UICONTROL Download em CSV]
   * [!UICONTROL Baixar o PDF]
   * [!UICONTROL Carregar análise guiada]
   * [!UICONTROL Carregar projeto]
   * [!UICONTROL Novo cartão de pontuação carregado]
   * [!UICONTROL Abrir dicionário de dados]
   * [!UICONTROL Abrir legendas inteligentes]
   * [!UICONTROL Compartilhamento de projeto]
   * [!UICONTROL Executar painel Experimentação]
   * [!UICONTROL Salvar projeto]
   * [!UICONTROL Scorecard salvo]
   * [!UICONTROL Enviar arquivo]
   * [!UICONTROL Enviar arquivo agendado]
   * [!UICONTROL Compartilhar projeto com qualquer pessoa]
   * [!UICONTROL Compartilhar projeto com usuários do Workspace]
* **[!UICONTROL Modelo de atribuição usado]**: o tipo de modelo de atribuição que o componente usa. Os itens de Dimension incluem:
   * [!UICONTROL Último contato]
   * [!UICONTROL Primeiro contato]
   * [!UICONTROL Linear]
   * [!UICONTROL Participação]
   * [!UICONTROL Mesmo contato]
   * [!UICONTROL Em forma de U]
   * Curva [!UICONTROL J]
   * [!UICONTROL J invertido]
   * [!UICONTROL Declínio de tempo]
   * [!UICONTROL Personalizado]
   * [!UICONTROL Algorítmico]
* **[!UICONTROL Nome do Componente]**: o nome do componente que foi adicionado, removido ou modificado.
* **[!UICONTROL Tipo de Componente]**: o tipo de componente que foi adicionado, removido ou modificado. Os itens de Dimension incluem:
   * [!UICONTROL Dimensão]
   * [!UICONTROL Métrica]
   * [!UICONTROL Filtro]
   * [!UICONTROL Métrica calculada]
   * [!UICONTROL Intervalo de datas]
   * [!UICONTROL Anotação]
   * [!UICONTROL Alerta]
* **[!UICONTROL Usuário do Logon]**: o usuário que executou a ação.
* **[!UICONTROL Painel Usado]**: o painel no qual o componente foi adicionado, removido ou modificado. Os itens de Dimension incluem:
   * [!UICONTROL Atribuição]
   * [!UICONTROL Painel em branco]
   * [!UICONTROL Experimentação]
   * [!UICONTROL Forma livre]
   * [!UICONTROL Próximo item ou anterior]
   * [!UICONTROL Insights rápidos]
   * [!UICONTROL Tendências]
   * [!UICONTROL Funil]
   * [!UICONTROL Crescimento de usuários]
   * [!UICONTROL Impacto]
   * [!UICONTROL Fluxo de usuários]
   * [!UICONTROL Retenção]
   * [!UICONTROL Matriz de recursos]
* **[!UICONTROL Nome do Projeto]**: o nome amigável do projeto.
* **[!UICONTROL Tipo de projeto]**: o tipo de projeto. Os itens de Dimension incluem:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL ID de Usuário]**: a ID de usuário que disparou o evento.
* **[!UICONTROL Visualização Usada]**: a visualização que foi adicionada, removida ou modificada. Os itens de Dimension incluem:
   * [!UICONTROL Tabela de forma livre]
   * [!UICONTROL Tabela de coorte]
   * [!UICONTROL Fallout]
   * [!UICONTROL Fluxo]
   * [!UICONTROL reportlet da tela de Jornada]
   * [!UICONTROL Área]
   * [!UICONTROL Área empilhada]
   * [!UICONTROL Barra]
   * [!UICONTROL Barra empilhada]
   * [!UICONTROL Marcador]
   * [!UICONTROL Combo]
   * [!UICONTROL Rosca]
   * [!UICONTROL Histograma]
   * [!UICONTROL Barra horizontal]
   * [!UICONTROL Barra horizontal empilhada]
   * [!UICONTROL Resumo da métrica principal]
   * [!UICONTROL Linha]
   * [!UICONTROL Mapa]
   * [!UICONTROL Dispersão]
   * [!UICONTROL Cabeçalho da seção]
   * [!UICONTROL Alteração de resumo]
   * [!UICONTROL Número do resumo]
   * [!UICONTROL Texto]
   * [!UICONTROL Mapas de árvores]
   * [!UICONTROL Venn]

O uso do produto não rastreia componentes de projetos individuais quando um projeto é meramente aberto ou visualizado. No entanto, a ação do usuário de abrir um projeto é rastreada.
