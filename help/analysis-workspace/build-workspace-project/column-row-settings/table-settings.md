---
description: As configurações de linha variam de acordo com qual componente foi arrastado para a tabela.
title: Configurações de linha
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# Configurações de linha

>[!NOTE] Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

As configurações de linha variam de acordo com qual componente foi arrastado para a tabela.

É possível, também, usar as [ações de clique com o botão direito](/help/analysis-workspace/visualizations/freeform-table.md) para gerenciar a(s) linha(s) selecionada(s).

Para acessar as configurações das linhas da tabela, clique o ícone de Configuração próximo a uma dimensão, segmento, métrica, período de tempo ou um detalhamento em cada uma dessas:

![](assets/row-settings.png)

| Configuração da linha | Descrição |
|--- |--- |
| Comparações de datas | Alinhar as datas de cada coluna para que todas iniciem na mesma linha.   Ao escolher alinhas das datas, por exemplo, em uma comparação de mês por mês entre outubro e setembro de 2016, a coluna da esquerda iniciará em 1° de outubro e a coluna da direita em 1° de setembro.<br>Desabilitado por padrão. |
| Porcentagens | Calcular porcentagem por linha - força a tabela de forma livre a calcular as porcentagens de células na linha, e não na coluna. Essa configuração é útil para porcentagens de tendência.<br>Ativado por padrão ao usar o ícone Visualizar. |
| Totais de colunas | Estas configurações aparecem apenas com [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL Mostrar a soma das linhas atuais como total]**: mostra uma soma das linhas da tabela do lado do cliente, o que significa que o total **não** removerá a duplicação de métricas como visitas ou visitantes.</li><li>**[!UICONTROL Mostrar total geral]**: mostra uma soma do lado do servidor, o que significa que o total removerá a duplicação de métricas como visitas ou visitantes.</li></ul> |
| Detalhamentos | **[!UICONTROL Detalhamento por posição]**: você pode executar detalhamentos baseados em uma localização fixa em uma tabela de Forma livre. Por exemplo, você pode especificar que as sete primeiras fileiras superiores devam sempre estar detalhadas.<br>(Anteriormente, a lista de valores no detalhamento era “bloqueada”, o que levava a uma situação em que, por exemplo, se você fizesse um detalhamento de  Data por Página, recebia uma lista das 50 primeiras páginas para o intervalo de data selecionado. Se salvasse o relatório e o executasse um mês depois, seria provável que as 50 páginas tivessem mudado. Entretanto, o Analysis Workspace usaria os resultados do detalhamento original e retornaria as mesmas páginas, porém com o mês atual como o intervalo de data.)<br>Para executar detalhamentos baseados em um local fixo: 1. Detalhar algumas linhas da tabela. 2. Clicar no ícone Configurações (engrenagem) próximo à linha da tabela que você deseja que fique em um local fixo. 3. Marcar a caixa de seleção ao lado de Detalhamento por posição. 4. Mudar a ordem de classificação ou o intervalo de data e observar que os detalhamentos estão agora vinculados à posição da linha e não às linhas embutidas em código.<br>Desabilitado por padrão. |