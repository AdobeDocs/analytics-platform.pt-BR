---
description: Um painel que mostra os itens de dimensão anteriores ou seguintes para uma dimensão específica.
title: Painel Item anterior ou seguinte
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---

# Painel Item anterior ou seguinte {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="Próximo item ou anterior"
>abstract="Crie um painel para entender as dimensões anteriores de onde as pessoas vêm ou a próxima dimensão que as pessoas acessam."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="Aninhar ou item anterior"
>abstract="Analise quais são os locais mais comuns dos quais os visitantes vieram anteriormente ou vão para o próximo.<br/><br/>**Dimension**: selecione uma dimensão. Por exemplo **Página**.<br/>**item de Dimension**: selecione um item de dimensão específico. Por exemplo, **Página inicial**.<br/>**Direção**: selecione **Avançar** para ver os itens de dimensão imediatamente a seguir ao item de dimensão selecionado. Selecione **Anterior** para ver os itens de dimensão que antecedem o item de dimensão selecionado.<br/>**Contêiner**: selecione **Sessão** para ver os itens de dimensão anteriores/seguintes na mesma sessão ou selecione **Pessoa** para ver o item de dimensão anterior/seguinte para a mesma pessoa."

<!-- markdownlint-enable MD034 -->



O painel **[!UICONTROL Item seguinte ou anterior]** contém várias tabelas e visualizações para identificar o item de dimensão seguinte ou anterior de uma dimensão específica. Por exemplo, você pode querer explorar quais páginas os clientes acessaram com mais frequência depois de visitarem a Página inicial.

## Use 

Para usar um painel **[!UICONTROL Item seguinte ou anterior]**:

1. Criar um painel **[!UICONTROL Próximo item ou anterior]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) para o painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Você pode configurar o painel [!UICONTROL Próximo item ou anterior] usando estas configurações de entrada:

![Painel do item seguinte ou anterior](assets/next-or-previous-item.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Dimensão]** | Selecione a dimensão para a qual deseja explorar os itens seguintes ou anteriores. |
| **[!UICONTROL Item de dimensão]** | Selecione o item de dimensão específico no centro da consulta seguinte/anterior. |
| **[!UICONTROL Direção]** | Especifique se você está procurando pelo item de dimensão [!UICONTROL Próximo] ou [!UICONTROL Anterior]. |
| **[!UICONTROL Contêiner]** | Selecione o contêiner [!UICONTROL Sessão] ou [!UICONTROL Pessoa] (padrão) para determinar o escopo da sua consulta. |

{style="table-layout:auto"}

Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel

O painel [!UICONTROL Item seguinte ou anterior] retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor quais ocorrências seguem ou precedem itens de dimensão específicos.


![Saída do painel seguinte/anterior](assets/next-or-previous-item-output.png)


| Visualização | Descrição |
| --- | --- |
| **[!UICONTROL Barra horizontal]** | Lista os itens seguintes (ou anteriores) com base no item de dimensão selecionado. Passar o mouse sobre uma barra individual destaca o item correspondente na tabela de Forma livre. |
| **[!UICONTROL Número do resumo]** | Número de resumo de alto nível de todas as ocorrências de itens de dimensão anteriores ou seguintes do mês atual (até o momento). |
| **[!UICONTROL Tabela de forma livre]** | Lista os itens seguintes (ou anteriores) com base no item de dimensão selecionado em um formato de tabela. Por exemplo, quais eram as páginas mais populares (por ocorrências) que as pessoas foram depois (ou antes) da página inicial ou da página do espaço de trabalho. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>