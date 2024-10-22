---
title: Análise da linha do tempo
description: Observe os eventos de sessão no nível do usuário ao longo do tempo para encontrar padrões de experiência.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: aff01f4fc3520d461ca800382cc24d8d948d9cbc
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 1%

---

# Análise de [!UICONTROL Linha do tempo]

A análise da ![Linha do tempo](/help/assets/icons/Timeline.svg) **[!UICONTROL Linha do tempo]** permite observar eventos de sessão no nível do usuário ao longo do tempo, para encontrar padrões de experiência e contar melhores histórias de usuário. O painel esquerdo permite filtrar o fluxo por valores de propriedade e segmentos. O painel direito permite selecionar de uma lista aleatória de usuários que correspondem aos critérios do filtro. A área central mostra o fluxo do usuário selecionado por sessão, consistindo em carimbo de data e hora, valores de propriedade e duração. A duração não está disponível para o último evento em uma determinada sessão.


>[!NOTE]
>
>A análise da [!UICONTROL Linha do Tempo] exige que o componente padrão **[!UICONTROL ID de Pessoa]** esteja disponível na [exibição de dados](/help/data-views/component-reference.md#optional). A inclusão da ID de pessoa em uma visualização de dados é gerenciada pelo administrador do Customer Journey Analytics, fornecendo à sua organização controle total de privacidade sobre quem pode acessar esses dados.
><br/>Se uma visualização de dados não tiver o componente [!UICONTROL ID de pessoa] adicionado, a seguinte mensagem será exibida:
>
>* **Administradores**: *A propriedade PersonID é necessária para esta análise. Adicione a ID de pessoa à visualização de dados.*
>* **Não administradores**: *A propriedade PersonID é necessária para esta análise. Trabalhe com o administrador de Customer Journey Analytics para adicionar a ID de pessoa à visualização de dados.*

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)



## Casos de uso

Os casos de uso para esta análise incluem:

* **Exploração de atrito**: se você encontrar uma queda acentuada na análise [Análise de funil](funnel.md), poderá criar um segmento desses usuários e aplicar o segmento nessa análise para investigar possíveis causas.
* **Comportamento de erro**: se os usuários encontrarem um erro de produto, você poderá explorar o que os usuários estavam fazendo antes ou depois de verem esse erro.
* **Validação da coleção de dados**: os administradores de dados podem filtrar esta análise para sua própria ID de pessoa para validar se a implementação de sua organização está funcionando como esperado.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas para essa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Dimension]**: a dimensão para a qual você deseja exibir valores transmitidos. O fluxo no centro mostra valores para a dimensão selecionada. Também é possível aplicar filtros para restringir o fluxo a dados mais relevantes. Os operadores válidos para o filtro incluem [!UICONTROL Igual], [!UICONTROL Não é igual], [!UICONTROL Começa com], [!UICONTROL Termina com], [!UICONTROL Contém], [!UICONTROL Não contém], [!UICONTROL Existe] e [!UICONTROL Não existe].
* **[!UICONTROL Segmentos]**: o segmento que você deseja analisar. O segmento selecionado filtra os dados para se concentrar apenas nos indivíduos que correspondem aos critérios do segmento. Se quiser restringir a análise a uma ID de pessoa específica, você poderá filtrar para essa ID de pessoa no painel direito. Um segmento é compatível com essa análise.

### Configurações de gráficos

A análise da [!UICONTROL Linha do Tempo] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Mostrar como]**: mostra os valores de propriedade desejados.
   * [!UICONTROL Mostrar tudo]: mostra todos os valores de propriedade em uma sessão.
   * [!UICONTROL Destaque]: destaca visualmente os valores de propriedade em uma sessão que corresponde aos filtros de consulta.
   * [!UICONTROL Exibir somente]: mostrar somente valores de propriedade em uma sessão que corresponda aos filtros de consulta.

### Intervalo de datas

O intervalo de datas desejado para sua análise. Há dois componentes nessa configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data pela qual você deseja exibir dados de tendência. Essa configuração não afeta análises de tendências, como a Linha de tempo.
* **[!UICONTROL Data]**: a data inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para sua conveniência ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
