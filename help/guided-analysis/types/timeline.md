---
title: Exibição da linha do tempo
description: Observe os eventos de sessão no nível do usuário ao longo do tempo para encontrar padrões de experiência.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: e9721eaf993175dd46e9d8edf9176d7c00308e8c
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# [!UICONTROL Linha do tempo] exibir

A variável **[!UICONTROL Linha do tempo]** permite observar eventos de sessão no nível do usuário ao longo do tempo para encontrar padrões de experiência e contar melhores histórias de usuário. O painel esquerdo permite filtrar o fluxo por valores de propriedade e segmentos. O painel direito permite selecionar de uma lista aleatória de usuários que correspondem aos critérios do filtro. A área central mostra o fluxo do usuário selecionado por sessão, consistindo em carimbo de data e hora, valores de propriedade e duração. A duração não está disponível para o último evento em uma determinada sessão.

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>A exibição Linha do tempo exige que o **[!UICONTROL ID de pessoa]** componente padrão esteja disponível no [visualização de dados](/help/data-views/component-reference.md#optional). A inclusão da ID de pessoa em uma visualização de dados é gerenciada pelo administrador do Customer Journey Analytics, fornecendo à sua organização controle total de privacidade sobre quem pode acessar esses dados.

Se uma visualização de dados não tiver o [!UICONTROL ID de pessoa] componente adicionado, a seguinte mensagem será exibida:

* **Administradores**: *A propriedade PersonID é necessária para esta análise. Adicione a ID de pessoa à visualização de dados.*
* **Não administradores**: *A propriedade PersonID é necessária para esta análise. Trabalhe com o administrador de Customer Journey Analytics para adicionar a ID de pessoa à visualização de dados.*

## Casos de uso

Os casos de uso para esse tipo de exibição incluem:

* **Exploração de atrito**: Se você encontrar uma queda acentuada no [Fricção](friction.md) , você pode criar um segmento desses usuários e aplicá-lo nessa visualização para investigar possíveis causas.
* **Comportamento de erro**: se os usuários encontrarem um erro de produto, você poderá explorar o que os usuários estavam fazendo antes ou depois de ver esse erro.
* **Validação da coleção de dados**: os administradores de dados podem filtrar essa exibição para sua própria ID de pessoa para validar se a implementação de sua organização está funcionando como esperado.

## Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Propriedade]**: a propriedade na qual você deseja exibir os valores transmitidos. O fluxo no centro mostra valores para a propriedade selecionada. Também é possível aplicar filtros para restringir o fluxo a dados mais relevantes. Os operadores válidos para o filtro incluem [!UICONTROL Igual a], [!UICONTROL Não é igual a], [!UICONTROL Começa com], [!UICONTROL Termina com], [!UICONTROL Contém], [!UICONTROL Não contém], [!UICONTROL Existe], e [!UICONTROL Não existe].
* **[!UICONTROL Segmentos]**: o segmento que você deseja analisar. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento. Se você quiser restringir a exibição para uma ID de pessoa específica, é possível filtrar para essa ID de pessoa aqui. Há suporte para um segmento nesta exibição.

## Configurações de gráficos

A variável [!UICONTROL Linha do tempo] view oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Mostrar como]**: mostra os valores de propriedade desejados.
   * [!UICONTROL Mostrar tudo]: mostra todos os valores de propriedade em uma sessão.
   * [!UICONTROL Realce]: destaca visualmente os valores de propriedade em uma sessão que corresponde aos filtros de consulta.
   * [!UICONTROL Exibir apenas]: mostrar apenas valores de propriedade em uma sessão que corresponde aos filtros de consulta.

## Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Interval]**: a granularidade de data pela qual você deseja exibir dados de tendência. Essa configuração não afeta exibições sem tendências, como a Linha do tempo.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.
