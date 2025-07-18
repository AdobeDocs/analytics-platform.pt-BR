---
description: Entenda como usar o painel Item seguinte ou anterior que mostra os itens seguintes ou anteriores para uma dimensão específica.
title: Painel Item Seguinte Ou Anterior
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 94%

---

# Painel Próximo item ou anterior {#next-or-previous-item-panel}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Próximo item ou anterior"
>abstract="Crie um painel para entender as dimensões anteriores de onde as pessoas vêm ou a próxima dimensão que as pessoas acessam."

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Próximo item ou anterior"
>abstract="Analise quais são os lugares mais comuns de onde os visitantes vieram ou para onde irão em seguida. Especifique a dimensão, o item de dimensão, a direção e o container a serem usados para a visualização."


>[!BEGINSHADEBOX]

_Este artigo documenta o painel Próximo item ou anterior no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Consulte [Painel Próximo item ou anterior](https://experienceleague.adobe.com/pt-br/docs/analytics/analyze/analysis-workspace/panels/next-previous) para ver a versão do_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** deste artigo._

>[!ENDSHADEBOX]

O painel **[!UICONTROL Próximo item ou anterior]** contém várias tabelas e visualizações para identificar o item de dimensão seguinte ou anterior de uma dimensão específica. Por exemplo, você pode querer explorar quais páginas os clientes acessaram com mais frequência depois de visitarem a página inicial.

## Usar {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="Container"
>abstract="Selecione o container para determinar o escopo da sua consulta."

Para usar um painel **[!UICONTROL Próximo item ou anterior]**:

1. Criar um painel **[!UICONTROL Próximo item ou anterior]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.

### Entrada do painel

Você pode configurar o painel [!UICONTROL Próximo ou item anterior] usando estas configurações de entrada:

![Painel Próximo item ou anterior](assets/next-or-previous-item.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Dimensão]** | Selecione a dimensão para a qual deseja explorar os itens seguintes ou anteriores. |
| **[!UICONTROL Item de dimensão]** | Selecione o item de dimensão específico no centro da consulta seguinte/anterior. |
| **[!UICONTROL Direção]** | Especifique se você está procurando pelo item de dimensão [!UICONTROL Próximo] ou [!UICONTROL Anterior]. |
| **[!UICONTROL Contêiner]** | Selecione o container **[!UICONTROL Conta global]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Conta]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Grupo de compra]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Oportunidade]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}, **[!UICONTROL Sessão]** ou **[!UICONTROL Pessoa]**, a fim de determinar o escopo da sua consulta. |

{style="table-layout:auto"}

Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel

O painel [!UICONTROL Próximo item ou anterior] retorna um conjunto avançado de dados e visualizações para ajudar você a entender melhor quais ocorrências seguem ou precedem itens de dimensão específicos.


![Saída do painel Próximo/anterior](assets/next-or-previous-item-output.png)


| Visualização | Descrição |
| --- | --- |
| **[!UICONTROL Barra horizontal]** | Lista os próximos itens (ou anteriores) com base no item de dimensão selecionado. Passar o mouse sobre uma barra individual destacará o item correspondente na tabela de forma livre. |
| **[!UICONTROL Número do resumo]** | Número de resumo de alto nível de todas as ocorrências de itens de dimensão anteriores ou seguintes do mês atual (até o momento). |
| **[!UICONTROL Tabela de forma livre]** | Lista os próximos itens (ou anteriores) com base no item de dimensão selecionado em um formato de tabela. Por exemplo, quais eram as páginas mais populares (por ocorrências) às quais as pessoas foram depois (ou antes) da página inicial ou da página do espaço de trabalho. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Criar um painel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
