---
description: Saiba como editar configurações de coluna para configurar a formatação de coluna; alguns elementos podem ser condicionais.
title: Configurações de coluna
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 49b165c4dfec99ff1c65d4aacf4a5ffbe65d4004
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 74%

---

# [!UICONTROL Configurações de coluna]

As [!UICONTROL Configurações de coluna] permitem que você configure a formatação da coluna; alguns elementos podem ser condicionais.

Assista a um vídeo sobre as configurações de linha e coluna aqui:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

## Editar [!UICONTROL Configurações de coluna] {#edit-column-settings}

Para acessar o [!UICONTROL Configurações de coluna], arraste uma Tabela de forma livre para o projeto e clique no ícone de configurações ![Configurações de coluna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) no cabeçalho da coluna.

<img src="./assets/column-settings.png" alt="As configurações de Coluna que mostram Total de células, Células da tabela e Visualização da célula da tabela." width="50%" />

É possível editar as configurações de **diversas colunas de uma só vez**. Basta selecionar várias colunas e clicar no ícone de configurações de qualquer uma dessas colunas. Todas as alterações feitas serão aplicadas a todas as colunas com as células selecionadas.

| Elemento | Descrição |
| --- | --- |
| Número | Determina se uma célula exibe ou oculta o valor numérico para a métrica. Por exemplo, se a métrica for Exibições de página, o valor numérico será o número de exibições de página para o item da linha. |
| Porcentagem | Determina se uma célula exibe ou oculta o valor percentual para a métrica. Por exemplo, se a métrica for Exibições de página, o valor percentual será o número de exibições de página para o item da linha dividido pelo total de exibições de página para a coluna.  Observação: podemos apresentar percentuais maiores que 100%, para maior precisão. Também fixamos o limite superior como 1.000% para garantir que as colunas possam aumentar em largura. |
| Mostrar anomalias | Determina se a detecção de anomalias é executada nos valores desta coluna. |
| Mostrar previsão | Determina se os valores de previsão são mostrados nesta coluna. |
| Quebrar linha do texto do cabeçalho | Permite quebrar o texto de cabeçalho em tabelas de forma livre para tornar os cabeçalhos mais legíveis e as tabelas mais compartilháveis. Essa opção é útil para renderização de .pdf e para métricas com nomes compridos. Ativado por padrão. |
| Interpretar o zero como valor inexistente | Para células com valor 0, determina se exibirá um 0 ou uma célula em branco. Isso é útil para observar dados diários de um mês que ainda não tenha terminado.  Em vez de mostrar 0 para as datas futuras, pode-se exibir células em branco. Essa configuração também aplica-se a gráficos (ou seja, eles não exibem uma linha ou uma barra com valores de 0 quando essa configuração estiver selecionada). |
| Histórico | Determina se uma célula exibe ou oculta todas as formatações de célula, incluindo o gráfico de barras e a formatação condicional. |
| Gráfico de barras | Exibe um gráfico de barras horizontal que representa o valor da célula relativo ao total da coluna. |
| Formatação condicional | Consulte a seção abaixo. |
| Visualização de célula de tabela | Mostra uma visualização de como cada célula é exibida com a aplicação das opções de formatação atuais selecionadas. |

## Formatação condicional {#conditional-formatting}

A formatação condicional aplica formatação a limites superiores, intermediários e inferiores que você pode definir. A aplicação de formatação condicional (cores, etc.) nas tabelas de forma livre também é ativada automaticamente nos detalhamentos, a menos que sejam selecionados limites “Personalizados”.

<img src="./assets/conditional-formatting.png" alt="As opções de formatação condicional com Personalizado selecionado" width="50%" />

| Elemento | Descrição |
| --- | --- |
| Formatação condicional | Aplica um conjunto de cores pré-configurado de sua escolha às células. Dependendo de qual dos 4 esquemas de cores disponíveis você selecionar, cores diferentes serão atribuídas a valores altos, valores médios e valores baixos. <br> Substituir uma dimensão na tabela redefine os limites da formatação condicional. Substituir uma métrica recalcula os limites da coluna (na qual haja uma métrica no eixo X e uma dimensão no eixo Y). |
| Usar limites de porcentagem | Alterar para que o intervalo limite se baseie em percentagens em vez de valores absolutos. Isso funciona com métricas exclusivamente baseadas em porcentagem (como a Taxa de retorno), além de métricas que possuem uma contagem e uma porcentagem (como Exibições de página). |
| Gerado automaticamente | Calcular limites superior/médio/inferior automaticamente de acordo com os dados. O limite superior é o valor mais alto na coluna. O limite inferior é o menor valor e o ponto intermediário é a média entre os limites superior e inferior. |
| Personalizado | Atribuir limites superior/médio/inferior manualmente. Isso oferece a flexibilidade de determinar quando o valor de uma coluna se torna bom, médio ou ruim. |
| Paleta de formatação condicional | Escolha qual dos 4 esquemas de cores disponíveis usar para a formatação condicional. |

## Usar modelo de atribuição não-padrão {#attribution}

Permite substituir o modelo de atribuição padrão definido em [Visualizações de dados](/help/data-views/component-settings/attribution.md).

>[!NOTE]
>
>Considere o seguinte ao atualizar a atribuição de um componente para um modelo de atribuição não padrão:
>
>* **Ao usar o componente em um relatório com o *uma única dimensão*:** A atribuição do componente ignora o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>* **Ao usar o componente em um relatório com o *várias dimensões*:** A atribuição do componente retém o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>   Várias dimensões estão disponíveis somente quando [exportação de dados para a nuvem](/help/analysis-workspace/export/export-cloud.md).
>
> Para obter mais informações sobre alocação, consulte [Configurações do componente de Persistência](/help/data-views/component-settings/persistence.md).

Para usar um modelo de atribuição não padrão para uma métrica em uma Analysis Workspace:

1. Clique no ícone de Configurações (engrenagem) em uma métrica em uma coluna de Tabela de forma livre.

   ![As opções de Configuração de coluna destacando a opção Configurações de dados: Use o modo de atribuição não padrão.](assets/attribution-checkbox.png)

2. Em **[!UICONTROL Configurações de dados]**, marque a opção **[!UICONTROL Usar modelo de atribuição não padrão]**. Para obter mais informações sobre os diferentes modelos de atribuição, consulte [Modelos de atribuição](/help/data-views/component-settings/attribution.md).

   ![As opções de Modelo de atribuição de coluna que mostram Linear selecionado.](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gerenciar fontes de dados](/help/analysis-workspace/visualizations/t-sync-visualization.md)
