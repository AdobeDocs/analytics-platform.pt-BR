---
description: Use a visualização principal do resumo da métrica para comparar o desempenho da métrica em duas linhas do tempo.
title: Resumo da métrica principal
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: 6238a3b2239a20aaedbec5e5603d0c72bb4ae463
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 6%

---

# Resumo da métrica principal

>[!NOTE]
>
>Esta funcionalidade está atualmente em [testes limitados](/help/release-notes/releases.md).

O [!UICONTROL Resumo da métrica principal] A visualização permite ver como uma métrica importante apresenta as tendências em um único período. Também permite comparar o desempenho da métrica em dois intervalos de tempo. Ela oferece os benefícios de várias visualizações combinadas em uma única visualização:

* **[!UICONTROL Linha]** visualizações que mostram a tendência da métrica para os intervalos de datas principal e de comparação

* **[!UICONTROL Alteração percentual do resumo]** que mostra o aumento ou a diminuição da métrica entre os intervalos de datas principal e de comparação

* Valor total atual ([!UICONTROL **número do resumo**]) para a métrica

## Casos de uso

Essa visualização aborda uma variedade de casos de uso comuns, incluindo:

* Um analista tentando entender como a criação da oportunidade parecia este mês em comparação com o mesmo período do ano passado.

* Um comerciante que explora como a geração de leads para um tipo de lead específico mudou deste mês para o mês anterior.

* Um executivo querendo entender como novas reservas mudaram deste trimestre para o último trimestre.

## Configurar o resumo da métrica principal

1. Arraste o **[!UICONTROL Resumo da métrica principal]** da **[!UICONTROL Visualizações]** no painel à esquerda, em um painel.

1. Configure a visualização selecionando uma métrica, um intervalo de datas principal e um intervalo de datas de comparação e um segmento (se desejar):

   ![](assets/key-metric-config.png)

   | Configuração | Definição |
   | --- | --- |
   | **[!UICONTROL Métrica]** | Selecione a métrica que deseja examinar. Todas as métricas são suportadas. |
   | **[!UICONTROL Intervalo de datas primário]** | O intervalo de datas atual da tabela de forma livre. |
   | **[!UICONTROL Intervalo de datas de comparação]** | O intervalo de datas no qual você deseja comparar o intervalo de datas principal. |
   | **[!UICONTROL Segmento (opcional)]** | Qualquer segmento em que você esteja interessado especificamente neste resumo. |

   {style=&quot;table-layout:auto&quot;}

1. Clique em **[!UICONTROL Criar]**.

## Exibir a saída

![](assets/key-metric-output.png)

Observe:

* O **[!UICONTROL Período anterior]** gráfico de linha (sempre exibido em cinza) corresponde ao **[!UICONTROL Intervalo de datas de comparação]** na etapa de configuração.

* Se um intervalo de datas de comparação não for especificado durante a configuração ou estiver oculto nas configurações de visualização, somente o gráfico de linhas do intervalo de datas principal será exibido. A alteração de resumo ficará oculta.

* A partir daqui, você pode passar o mouse sobre os gráficos de linha para ver as estatísticas de dias individuais:

![](assets/key-metric-output2.png)

## Configurações de visualização

O resumo da métrica principal oferece várias configurações flexíveis para permitir melhores relatórios e comunicações de métricas importantes. As configurações podem ser acessadas por meio do ícone de engrenagem no canto superior direito da visualização.

![](assets/key-metric-settings.png)

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Realçar a alteração percentual]** | Exibir alteração de resumo em negrito de destaque no centro da visualização |
| **[!UICONTROL Realçar valor numérico]** | Exibir número do resumo em negrito de destaque no centro da visualização |
| **[!UICONTROL Legenda visível]** | Mostrar ou ocultar a legenda na parte inferior da visualização |
| **[!UICONTROL Mostrar anotações]** | Mostrar ou ocultar anotações adicionadas por um administrador |
| **[!UICONTROL Mostrar linhas cintilantes]** | Mostrar ou ocultar gráficos de linha na parte inferior do gráfico. Quando ocultada, a legenda será alterada para não mais fazer referência visualmente às linhas |
| **[!UICONTROL Mostrar mín. e máx. em linhas cintilantes]** | Mostrar ou ocultar valores mínimos e máximos em gráficos de linha primária e de comparação |
| **[!UICONTROL Mostrar comparação]** | Mostrar ou ocultar dados de comparação. Quando ocultos, o gráfico de linha de comparação e os objetos de alteração de resumo serão ocultos da exibição. |
| **[!UICONTROL Mostrar número total]** | Mostrar ou ocultar o número do resumo |
| **[!UICONTROL Mostrar diferença bruta]** | Mostrar ou ocultar diferença bruta entre o valor total da métrica no intervalo de datas principal e o intervalo de datas secundário |
| **[!UICONTROL Abreviar valor]** | Abreviar valores de números para simplificar os insights comunicados (por exemplo, 20.000 -> 20K) |

## Editar visualização

Após criar a visualização, ainda é possível editar a configuração original.

1. Clique no ícone de lápis no canto superior direito da visualização (ao lado do ícone de engrenagem de configurações).

   ![](assets/edit-icon.png)

   Agora você é levado de volta à visualização de configuração original.

1. Altere a métrica, o intervalo de datas principal, o intervalo de datas de comparação ou o segmento como preferir.
