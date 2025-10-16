---
title: Análise da linha do tempo
description: Observe os eventos de sessão na camada dos usuários ao longo do tempo para encontrar padrões de experiência.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---

# Análise de [!UICONTROL linha do tempo] {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="Linha do tempo"
>abstract="Observe eventos de sessão no nível de usuário ao longo do tempo."

<!-- markdownlint-enable MD034 -->

A análise da ![Timeline](/help/assets/icons/Timeline.svg) **[!UICONTROL Linha do tempo]** permite observar eventos de sessão na camada dos usuários ao longo do tempo para encontrar padrões de experiência e contar melhores histórias de usuários. O painel esquerdo permite filtrar o fluxo por valores de propriedade e segmentos. O painel direito permite selecionar em uma lista aleatória de usuários que correspondem aos critérios do filtro. A área central mostra o fluxo do usuário selecionado por sessão, consistindo em carimbo de data/hora, valores de propriedade e duração. A duração não está disponível para o último evento de uma determinada sessão.


>[!NOTE]
>
>A análise da [!UICONTROL Linha do Tempo] exige que o componente padrão **[!UICONTROL ID de pessoa]** esteja disponível na [visualização de dados](/help/data-views/component-reference.md#optional). A inclusão do ID de pessoa em uma visualização de dados é gerenciada pelo administrador do Customer Journey Analytics, fornecendo à sua organização controle total da privacidade sobre quem pode acessar esses dados.
><br/>Se uma visualização de dados não tiver o componente [!UICONTROL ID de pessoa] adicionado, a seguinte mensagem será exibida:
>
>* **Administradores**: *a propriedade PersonID é necessária para esta análise. Adicione o ID de pessoa à visualização de dados.*
>* **Não administradores**: *a propriedade PersonID é necessária para esta análise. Colabore com o administrador do Customer Journey Analytics para adicionar um ID de pessoa à visualização de dados.*

>[!VIDEO](https://video.tv.adobe.com/v/3435772/?captions=por_br&quality=12&learn=on)



## Casos de uso

Os casos de uso desta análise incluem:

* **Exploração de atrito**: se você encontrar uma queda acentuada na [Análise de funil](funnel.md), poderá criar um segmento desses usuários e aplicar o segmento nessa análise para investigar as possíveis causas.
* **Comportamento de erro**: se os usuários encontrarem um erro do produto, você poderá explorar o que os usuários estavam fazendo antes ou depois de ver esse erro.
* **Validação da coleta de dados**: os administradores de dados podem filtrar esta análise com seu próprio ID de pessoa para conferir se a implementação de sua organização está funcionando como esperado.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Dimensão]**: a dimensão para a qual você deseja exibir os valores transmitidos. O fluxo no centro mostra os valores da dimensão selecionada. Também é possível aplicar filtros para restringir o fluxo a dados mais relevantes. Os operadores válidos para o filtro incluem [!UICONTROL Igual a], [!UICONTROL Não é igual a], [!UICONTROL Começa com], [!UICONTROL Termina com], [!UICONTROL Contém], [!UICONTROL Não contém], [!UICONTROL Existe] e [!UICONTROL Não existe].
* **[!UICONTROL Segmentos]**: o segmento que você deseja analisar. O segmento selecionado filtra os dados para se concentrar apenas nas pessoas que correspondem aos critérios do segmento. Se quiser restringir a análise a um ID de pessoa específico, você poderá filtrar com esse ID de pessoa no painel direito. Um segmento é permitido para essa análise.

### Configurações de gráficos

A análise da [!UICONTROL Linha do tempo] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Mostrar como]**: mostra os valores de propriedade desejados.
   * [!UICONTROL Mostrar tudo]: mostra todos os valores de propriedade de uma sessão.
   * [!UICONTROL Realçar]: destaca visualmente os valores de propriedade de uma sessão que correspondem aos filtros de consulta.
   * [!UICONTROL Exibir somente]: mostra somente valores de propriedade de uma sessão que correspondem aos filtros de consulta.

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de datas com a qual você deseja exibir os dados de tendência. Essa configuração não afeta análises de tendências, como a linha de tempo.
* **[!UICONTROL Data]**: as datas inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
