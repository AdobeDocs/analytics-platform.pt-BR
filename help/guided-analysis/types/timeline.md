---
title: Exibição da linha do tempo
description: Explore padrões na atividade da sessão.
feature: Guided Analysis
keywords: análise do produto
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# [!UICONTROL Linha do tempo] exibir

A variável **[!UICONTROL Linha do tempo]** permite analisar sessões individuais para determinar padrões de comportamento. O painel direito permite selecionar a ID de pessoa que deseja analisar. A área central mostra a hora, o valor da propriedade selecionada e a duração de cada evento dessa pessoa.

Essa análise exige que você adicione a variável **[!UICONTROL ID de pessoa]** componente padrão para o [visualização de dados](/help/data-views/component-reference.md#optional). Se você não tiver o [!UICONTROL ID de pessoa] componente adicionado à visualização de dados, a seguinte mensagem é exibida:

> A propriedade PersonID é necessária para esta análise. Adicione PersonID à visualização de dados.

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Exploração de atrito**: Se você encontrar uma queda acentuada no [Fricção](friction.md) dessa exibição, é possível investigar as possíveis causas desse descarte usando essa exibição.
* **Comportamento de erro**: se os usuários encontrarem um erro em seu produto, você poderá explorar o que os usuários farão antes ou depois de verem esse erro.
* **Validação da coleção de dados**: os administradores de dados podem filtrar essa visualização para se isolar. Essa visualização fornece uma maneira sólida de garantir que a implementação de sua organização esteja funcionando como esperado.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Propriedade]**: a propriedade na qual você deseja exibir valores. A análise de sessão no centro mostra valores para a propriedade selecionada aqui. Você também pode filtrar dados pela propriedade selecionada. Os operadores válidos para o filtro incluem [!UICONTROL Igual a], [!UICONTROL Não é igual a], [!UICONTROL Começa com], [!UICONTROL Termina com], [!UICONTROL Contém], [!UICONTROL Não contém], [!UICONTROL Existe], e [!UICONTROL Não existe].
* **[!UICONTROL Segmentos]**: o segmento que você deseja medir. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento. Há suporte para um segmento nesta exibição.

## Configurações de gráficos

A variável [!UICONTROL Linha do tempo] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Mostrar como]**: mostra os valores de propriedade desejados.
   * [!UICONTROL Exibir tudo]
   * [!UICONTROL Realce]
   * [!UICONTROL Exibir apenas]

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendência. Essa configuração não afeta exibições sem tendências, como a Linha do tempo.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
