---
description: Um painel que mostra os itens de dimensão anteriores ou seguintes para uma dimensão específica.
title: Painel Item anterior ou seguinte
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c7cdeb29729af35d7554b19e395047b364f0b547
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 36%

---

# Painel Item anterior ou seguinte {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Próximo item ou anterior"
>abstract="Crie um painel para entender as dimensões anteriores de onde as pessoas vêm ou a próxima dimensão que as pessoas acessam."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Item anterior ou seguinte"
>abstract="Analise quais são os lugares mais comuns de onde os visitantes vieram ou para onde irão em seguida.<br/><br/>**Dimensão**: selecione uma dimensão. Por exemplo, **Página**.<br/>**item de dimensão**: selecione um item de dimensão específico. Por exemplo, **Página inicial**.<br/>**Direção**: selecione **Próximo** para ver os itens de dimensão imediatamente a seguir ao item de dimensão selecionado. Selecione **Anterior** para ver os itens de dimensão que antecedem o item de dimensão selecionado.<br/>**Contêiner**: selecione **Sessão** para ver os itens de dimensão anteriores/seguintes na mesma sessão ou selecione **Pessoa** para ver o item de dimensão anterior/seguinte para a mesma pessoa."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Este artigo documenta o painel Item seguinte ou anterior em **Customer Journey Analytics**. Consulte [Painel do item seguinte ou anterior](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) para a versão **Adobe Analytics**deste artigo.*

>[!ENDSHADEBOX]

O painel **[!UICONTROL Item seguinte ou anterior]** contém várias tabelas e visualizações para identificar o item de dimensão seguinte ou anterior de uma dimensão específica. Por exemplo, você pode querer explorar quais páginas os clientes acessaram com mais frequência depois de visitarem a Página inicial.

## Usar

Para usar um painel **[!UICONTROL Item seguinte ou anterior]**:

1. Criar um painel **[!UICONTROL Próximo item ou anterior]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

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
