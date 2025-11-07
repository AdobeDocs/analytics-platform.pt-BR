---
title: Visão geral de uso do produto
description: Exiba insights e relatórios sobre como sua organização usa o Customer Journey Analytics.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: 22f3059ffef5df76028f36ffa00da8f98956dee1
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 91%

---

# Visão geral de uso do produto

O uso do produto oferece à sua organização a capacidade de exibir dados de análise sobre como sua organização usa o Customer Journey Analytics. Ele está disponível para todas as organizações que usam o Customer Journey Analytics. Após habilitados, os seguintes componentes da Adobe Experience Platform são criados e conectados automaticamente para você. Todos esses componentes são de propriedade do sistema, somente leitura e não podem ser editados.

* Um esquema na Adobe Experience Platform
* Um conjunto de dados na Adobe Experience Platform
* Uma conexão no Customer Journey Analytics
* Uma exibição de dados no Customer Journey Analytics

Toda a configuração e coleção de dados é definida automaticamente para você depois de habilitada. Sempre que um usuário realiza uma ação no Analysis Workspace, essa ação é rastreada e fica disponível para relatórios.

>[!IMPORTANT]
>
>Ativar o Uso do produto resulta no armazenamento de dados de uso no data lake da Adobe Experience Platform. Certifique-se de que a alocação de armazenamento de data lake de sua organização possa acomodar os conjuntos de dados adicionais gerados pela ativação desse recurso.
>
>Esse recurso não é contabilizado em relação aos limites de linha licenciados do Customer Journey Analytics ou aos direitos de dados do evento.

## Habilitar uso do produto

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Ferramentas]** > **[!UICONTROL Uso do produto]**

Ao navegar até esta seção da interface no Customer Journey Analytics, você será direcionado para [Configurações de dados](data-settings.md), onde é possível habilitar este recurso.

## Dimensões disponíveis

Ao habilitar o Uso do produto, as seguintes dimensões estão disponíveis. Se quiser alterar qualquer configuração de dimensão, crie uma cópia da exibição de dados de propriedade do sistema e use a exibição de dados copiada no Analysis Workspace.

* **[!UICONTROL Nome da ação]**: o tipo de ação que o usuário executou. É possível usar essa dimensão como qualquer métrica desejada ao criar uma cópia nas configurações de exibição de dados. Os itens de dimensão incluem:
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
   * [!UICONTROL Compartilhamento do projeto]
   * [!UICONTROL  Painel Executar experimentação]
   * [!UICONTROL Salvar projeto]
   * [!UICONTROL Cartão de pontuação salvo]
   * [!UICONTROL Enviar arquivo]
   * [!UICONTROL Enviar arquivo conforme agendamento]
   * [!UICONTROL Compartilhar projeto com qualquer pessoa]
   * [!UICONTROL Compartilhar o projeto com usuários do Espaço de trabalho]
   * [!UICONTROL Alternar visualização de dados]
* **[!UICONTROL Modelo de atribuição usado]**: o tipo de modelo de atribuição que o componente usa. Os itens de dimensão incluem:
   * [!UICONTROL Último contato]
   * [!UICONTROL Primeiro contato]
   * [!UICONTROL Linear]
   * [!UICONTROL Participação]
   * [!UICONTROL Mesmo contato]
   * [!UICONTROL Em forma de U]
   * [!UICONTROL Curva J]
   * [!UICONTROL J invertido]
   * [!UICONTROL Declínio de tempo]
   * [!UICONTROL Personalizado]
   * [!UICONTROL Algorítmico]
* **[!UICONTROL ID do componente]**: a identificação do componente que foi adicionado, removido ou modificado.
* **[!UICONTROL Nome do componente]**: o nome amigável do componente que foi adicionado, removido ou modificado.
* **[!UICONTROL Tipo de componente]**: o tipo de componente que foi adicionado, removido ou modificado. Os itens de dimensão incluem:
   * [!UICONTROL Dimensão]
   * [!UICONTROL Métrica]
   * [!UICONTROL Segmento]
   * [!UICONTROL Métrica calculada]
   * [!UICONTROL Intervalo de datas]
   * [!UICONTROL Anotação]
   * [!UICONTROL Alerta]
* **[!UICONTROL ID da visualização de dados]**: a ID da visualização de dados.
* **[!UICONTROL Nome da exibição de dados]**: o nome amigável da exibição de dados.
* **[!UICONTROL Usuário logado]**: o usuário que executou a ação.
* **[!UICONTROL Painel usado]**: o painel que foi adicionado, removido ou modificado. Os itens de dimensão incluem:
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
* **[!UICONTROL ID do projeto]**: a ID do projeto.
* **[!UICONTROL Nome do projeto]**: o nome amigável do projeto.
* **[!UICONTROL Tipo de projeto]**: o tipo de projeto. Os itens de dimensão incluem:
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL Visualização usada]**: a visualização que foi adicionada, removida ou modificada. Os itens de dimensão incluem:
   * [!UICONTROL Tabela de forma livre]
   * [!UICONTROL Tabela de coorte]
   * [!UICONTROL Fallout]
   * [!UICONTROL Fluxo]
   * [!UICONTROL Reportlet da tela da jornada]
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
   * [!UICONTROL Cabeçalho de seção]
   * [!UICONTROL Alteração de resumo]
   * [!UICONTROL Número do resumo]
   * [!UICONTROL Texto]
   * [!UICONTROL Mapas de árvores]
   * [!UICONTROL Venn]

O uso do produto não rastreia componentes individuais do projeto quando um projeto é apenas aberto ou exibido. No entanto, a ação do usuário de abrir um projeto é rastreada.

## Modelo disponível

Há um [modelo da Adobe](/help/analysis-workspace/templates/use-templates.md) disponível que usa os componentes gerados automaticamente com base neste recurso.

**[!UICONTROL Modelos da Adobe]** > **[!UICONTROL Outros]** > **[!UICONTROL Visão geral de uso do produto]**

Selecione a visualização de dados que o uso do produto criou automaticamente no seletor de visualização de dados e, em seguida, selecione o modelo **[!UICONTROL Visão geral de uso do produto]**. Selecione **[!UICONTROL Visualizar]** para ver quais painéis o modelo usa e saiba mais sobre casos de uso ideais, ou selecione **[!UICONTROL Usar modelo]** para abri-lo no Analysis Workspace.
