---
description: Saiba como criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos em uma análise de fallout no Analysis Workspace.
keywords: fallout e segmentação;segmentos na análise de fallout;comparar segmentos no fallout
title: Aplicar Segmentos Na Análise De Fallout
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 23%

---

# Aplicar segmentos na análise de fallout

Você pode criar segmentos a partir de um ponto de contato, adicionar segmentos como ponto de contato e comparar fluxos de trabalho principais em vários segmentos no Analysis Workspace.

>[!IMPORTANT]
>
>Os segmentos usados como pontos de verificação no Fallout devem usar um contêiner que esteja em um nível inferior ao contexto geral da visualização do Fallout. Com um Fallout de contexto de pessoa, os segmentos usados como pontos de verificação devem ser segmentos baseados em sessão ou evento. Com um Fallout de contexto de sessão, os segmentos usados como ponto de verificação devem ser segmentos baseados em eventos. Se você usar uma combinação inválida, o fallout será de 100%. Você vê um aviso na visualização de Fallout ao adicionar um segmento incompatível como ponto de contato. Determinadas combinações inválidas de contêineres de segmento resultam em diagramas de Fallout inválidos, por exemplo:
>
>* Usar um segmento com base em pessoas como um ponto de contato dentro de uma visualização de Fallout de contexto de pessoa.
>* Usar um segmento com base em pessoas como um ponto de contato dentro de uma visualização de Fallout de contexto de sessão.
>* Usar um segmento baseado em sessão como um ponto de contato dentro de uma visualização de Fallout de contexto de sessão.

<!-- Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* -->

## Criar um segmento a partir de um ponto de contato

1. Crie um segmento a partir de um ponto de contato específico no qual esteja interessado e que possa ser útil para aplicar a outros relatórios. Clique com o botão direito no ponto de contato e selecione **[!UICONTROL Criar segmento a partir do ponto de contato]**.

   ![O menu suspenso Ponto de Contato com a opção Criar segmento a partir do ponto de contato realçada.](assets/fallout-createsegment.png)

   O [!UICONTROL Construtor de segmentos] é aberto, preenchido previamente com o segmento sequencial pré-construído que corresponde ao ponto de contato selecionado:

   ![O Construtor de segmentos exibe o segmento sequencial pré-preenchido e pré-construído.](assets/fallout-definesegment.png)

1. Atribua um título e uma descrição ao segmento e salve-o.

   Agora é possível usar esse segmento em qualquer projeto.

## Adicionar um segmento como ponto de contato

Se quiser ver, por exemplo, a tendência dos seus usuários dos EUA e como eles afetam o fallout, basta arrastar o segmento de usuários dos EUA ao fallout:

![O segmento Usuários dos EUA foi selecionado e destacado para arrastar até o fallout.](assets/fallout-addfilter.png)

Ou você pode criar um ponto de contato AND arrastando o segmento de usuários dos EUA para outro ponto de verificação.

## Comparar segmentos no fallout

É possível comparar um número ilimitado de segmentos na visualização de Fallout.

1. Selecione os segmentos que você deseja comparar no painel [!UICONTROL Segmento] à esquerda. No exemplo, três segmentos são selecionados: *Detalhes do voo: Versão da página A*, *Detalhes do voo: Versão da página B* e *Detalhes do voo: Versão da página C*.
1. Arraste os três segmentos até a área de soltar Segmentos na parte superior da visualização.


1. Opcional: Você pode manter *Todas as Pessoas* como o contêiner padrão ou excluir o contêiner.

   ![O Fallout mostra Todas as Visitas juntamente com os dois segmentos arrastados na etapa anterior.](assets/fallout-multiplefilters.png)

1. Agora é possível comparar o fallout nos três segmentos, por exemplo, em que um segmento está com desempenho melhor que outro ou em outros insights.
