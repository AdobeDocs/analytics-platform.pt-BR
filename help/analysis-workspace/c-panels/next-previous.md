---
description: Um painel que mostra os itens de dimensão anteriores ou seguintes de uma dimensão específica.
title: Painel Item seguinte ou anterior
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 73%

---

# Painel Item seguinte ou anterior {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Item seguinte ou anterior"
>abstract="Crie um painel para entender as dimensões anteriores de onde as pessoas vêm ou a próxima dimensão que as pessoas acessam."

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Item seguinte ou anterior"
>abstract="Analise quais são os locais mais comuns dos quais os visitantes vieram anteriormente ou vão para o próximo. Especifique a dimensão, o item de dimensão, a direção e o contêiner a ser usado para a visualização."



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Este artigo documenta o painel Item seguinte ou anterior no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Consulte [Painel do item seguinte ou anterior](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/next-previous) para a_ versão ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]

O painel **[!UICONTROL Item seguinte ou anterior]** contém várias tabelas e visualizações para identificar o item de dimensão seguinte ou anterior de uma dimensão específica. Por exemplo, você pode querer explorar quais páginas os clientes acessaram com mais frequência depois de visitarem a página inicial.

## Usar {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="Contêiner"
>abstract="Selecione o contêiner para determinar o escopo da pesquisa."

Para usar um painel **[!UICONTROL Item seguinte ou anterior]**:

1. Crie um painel **[!UICONTROL Item seguinte ou anterior]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

É possível configurar o painel [!UICONTROL Item seguinte ou anterior] usando estas configurações de entrada:

![Painel Item seguinte ou anterior](assets/next-or-previous-item.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Dimensão]** | Selecione a dimensão cujos itens seguintes ou anteriores você deseja conhecer. |
| **[!UICONTROL Item de dimensão]** | Selecione o item de dimensão específico no centro da consulta seguinte/anterior. |
| **[!UICONTROL Direção]** | Especifique se você está procurando pelo item de dimensão [!UICONTROL seguinte] ou [!UICONTROL anterior]. |
| **[!UICONTROL Container]** | Selecione o contêiner, **[!UICONTROL Conta Global]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Conta]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Grupo de Compras]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]**, para determinar o escopo da sua consulta. |

{style="table-layout:auto"}

Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel

O painel [!UICONTROL Item seguinte ou anterior] retorna um conjunto avançado de dados e visualizações para ajudar a entender melhor quais ocorrências seguem ou precedem itens de dimensão específicos.


![Saída do painel seguinte/anterior](assets/next-or-previous-item-output.png)


| Visualização | Descrição |
| --- | --- |
| **[!UICONTROL Barra horizontal]** | Lista os itens seguintes (ou anteriores) com base no item de dimensão selecionado. Passar o mouse sobre uma barra individual destacará o item correspondente na tabela de forma livre. |
| **[!UICONTROL Número do resumo]** | Número de resumo de alto nível de todas as ocorrências de itens de dimensão seguintes ou anteriores do mês atual (até o momento). |
| **[!UICONTROL Tabela de forma livre]** | Lista os itens seguintes (ou anteriores), em um formato de tabela, com base no item de dimensão selecionado. Por exemplo, quais eram as páginas mais populares (por ocorrências) que as pessoas visitaram depois (ou antes) da página inicial ou da página do espaço de trabalho. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
