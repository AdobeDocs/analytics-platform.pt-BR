---
description: No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.
title: Visão geral do calendário e do intervalos de datas
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
source-git-commit: 524aed20a62b8d8648230be81c63f9c58c84ae87
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 100%

---

# Visão geral do calendário e do intervalos de datas

No calendário, você pode especificar datas e intervalos de datas ou selecionar uma predefinição.

As seleções do calendário se aplicam a nível de painel, mas existe a opção de aplicá-las a todos os painéis. Ao clicar em um intervalo de datas no Espaço de trabalho, a interface exibe o mês atual do calendário e o mês anterior. Você pode ajustar esses dois calendários clicando nas setas para a direita e para a esquerda em cada canto superior respectivo.

![Calendário](assets/aw_calendar2.png){width="60%"}

O primeiro clique em um calendário inicia uma seleção de intervalo de datas. O segundo clique conclui uma seleção de intervalo de datas, que é realçada. Se a tecla `Shift` for pressionada (ou se o clique com o botão direito do mouse for usado), ela será anexada ao intervalo selecionado no momento.

Você também pode arrastar datas (e dimensões de tempo) em um projeto do Espaço de trabalho. É possível selecionar dias, semanas, meses e anos específicos ou uma data do acumulado.

[Usando intervalos de data e calendário na Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=pt-BR) (4:07)

| Configuração | Descrição |
| --- | --- |
| Dias selecionados | Dias/semanas/meses/anos selecionados |
| Usar datas do acumulado | Datas do acumulado permitem gerar um relatório dinâmico que analisa antes e depois de um período de tempo com base na execução do relatório. Por exemplo, se você quiser relatar todos os pedidos feitos no “Mês anterior” (dependendo da Data de criação) e executar o relatório em dezembro, você verá os pedidos feitos em novembro. Se executar o mesmo relatório em janeiro, verá os pedidos feitos em dezembro.<ul><li>**[!UICONTROL Visualização de data]**: indica o período compreendido no calendário em andamento.</li><li>**[!UICONTROL Início]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li><li>**[!UICONTROL Fim]**: você pode escolher entre dia atual, semana atual, mês atual, trimestre atual, ano atual.</li></ul>Par ver um exemplo, clique [aqui](/help/components/date-ranges/custom-date-ranges.md). |
| Intervalo de datas | Permite selecionar um intervalo de datas predefinido. Últimos 30 dias é padrão. **[!UICONTROL Essa semana/mês/trimestre/ano (exceto hoje)]** permite escolher entre intervalos de datas que não incluem dados parciais do dia de hoje. |
| Aplicar a todos os painéis | Permite alterar o intervalo de datas selecionado para o painel atual e também para todos os outros painéis do projeto. |
| Aplicar | Aplica o intervalo de datas somente a este painel. |

## Sobre intervalos de datas relativos do painel {#relative-panel-dates}

Se você estiver trabalhando no espaço de trabalho, é possível tornar os componentes do intervalo de datas relativos ao calendário do painel. Há três casos de uso comuns em que você verá as datas relativas do painel entrarem em vigor: intervalos de datas de gráficos combinados, de resumos de métricas principais e de tabelas de forma livre.

Para usar intervalos de datas relativos ao painel

1. Clique na guia **Espaço de trabalho**.
1. Selecione **Projeto em branco**.
1. Adicione dimensões, métricas e segmentos do painel esquerdo.
1. Clique no campo de intervalo de datas do painel para alternar a configuração de intervalos de datas relativos ao painel.
1. Selecione **Tornar os componentes do intervalo de datas relativos ao calendário do painel**.
   * Selecione a opção para tornar os componentes do intervalo de datas relativos ao calendário do painel.
Se datas relativas forem selecionadas, as datas contínuas serão baseadas na data inicial do calendário do painel, e não na data de hoje.
   * Se essa opção não estiver selecionada, as datas contínuas serão baseadas na data de hoje.

   ![datas relativas do painel](assets/relative-date-selected.png){width="60%"}

1. Clique em **Aplicar**.
As datas relativas são mostradas no canto superior direito.

   ![datas relativas em forma livre ](assets/relative-date-range1.png)

## Diretrizes para intervalos de datas relativas do painel {#guidelines}

Lembre-se das seguintes diretrizes ao usar intervalos de datas relativos ao painel.

### Fórmulas e intervalos de datas relativos {#formula-relative-dates}

Se você tiver selecionado datas relativas, todas as fórmulas de datas usarão a data inicial do painel como ponto de partida.

### Calendários personalizados e intervalos de datas relativos {#custom-calendar-formulas}

Ao usar um calendário personalizado com base em semanas e adicionar meses ou anos, a fórmula calcula a diferença de dias no período especificado. A data real pode ser diferente devido a essa diferença. A fórmula escolhe o dia baseado no mesmo local do calendário personalizado. Por exemplo, a terceira sexta-feira da terceira semana em um calendário personalizado.

### Sobre segmentos que usam datas contínuas e intervalos de datas relativos ao painel {#segments-relative-dates}

Se você criar um segmento ou usar um segmento com uma data contínua, por exemplo, os últimos 7 dias ou as últimas 2 semanas, e clicar na pré-visualização do segmento, a data contínua será iniciada a partir de *Hoje* em vez da data inicial do painel. Como resultado, as informações da pré-visualização do segmento não corresponderão às que você verá ao usar o segmento na tabela. A pré-visualização é afetada, não o segmento propriamente dito.

## Diretrizes para intervalos de datas e visualizações do painel {#guidelines-panel-dates}

* A partir da versão de fevereiro, as visualizações de componentes e dados serão baseadas no intervalo de datas do painel e não nos últimos 90 dias.
* Todos os componentes listados no painel esquerdo estarão disponíveis com base no intervalo de datas do painel.
* Todas as visualizações de data nos construtores de métrica calculada e de segmento serão baseadas no intervalo de datas do painel, a menos que sejam acessadas pelos gerentes de componente, que não têm um painel associado; neste caso, elas ainda serão baseadas nos últimos 90 dias.
* Quaisquer visualizações de dados exibirão dados ou componentes com base no intervalo de datas do painel.