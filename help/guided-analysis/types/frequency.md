---
title: Análise de frequência
description: Meça o engajamento pela frequência de uso.
feature: Adobe Product Analytics, Guided Analysis
keywords: product analytics
exl-id: 27eaa7c7-f1e1-4cf1-9d59-67ac552eb430
role: User
TQID: https://experienceleague.adobe.com/q-egeF94DZ-kxHpVBJX7A-Th0N30t7ji-V2EoXMe1P4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 7f8ab656c7dbf508b2a78fd2022592faf883c56e
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 100%

---

# Análise de [!UICONTROL frequência] {#frequency}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_frequency_button"
>title="Frequência"
>abstract="Exiba a distribuição da atividade repetida do usuário para eventos específicos."

<!-- markdownlint-enable MD034 -->

A Análise de ![Frequência](/help/assets/icons/Histogram.svg) **[!UICONTROL frequência]** agrupa os dados de eventos de acordo com a constância com que os eventos ocorrem no produto. O eixo vertical dessa análise contém compartimentos que representam a frequência do evento. O eixo horizontal mede o número de usuários ou sessões para cada compartimento.

>[!VIDEO](https://video.tv.adobe.com/v/3435807/?captions=por_br&quality=12&learn=on)

## Casos de uso

Os casos de uso desta análise incluem:

* **Engajamento**: acompanhe o grau de engajamento dos usuários com qualquer evento no produto. Clique em qualquer parte do gráfico de barras para salvá-lo como um segmento. Os segmentos de compartimentos com baixo engajamento podem ajudar a determinar por que usuários não estão interagindo com o evento na frequência desejada. Os segmentos para compartimentos de alto engajamento podem ajudar a entender por que usuários interagem com o evento com frequência. A partir daí, é possível incentivar outros usuários a adotar um comportamento semelhante.
* **Fidelização do cliente**: defina o evento como Pedidos e a métrica como Usuários. Essa análise permite agrupar os usuários pela quantidade de vezes que fizeram uma compra no site dentro do intervalo de datas especificado.
* **Otimização do suporte**: visualize o número de chamadas do suporte ou casos abertos por usuário para obter informações sobre quais usuários encontram mais problemas. Você pode então criar um segmento concentrado em suas experiências para ajudar a identificar e resolver seus problemas.
* **Serviços de assinatura**: os usuários com baixo engajamento têm maior probabilidade de churn. Entender o comportamento de usuários altamente engajados pode ajudar a incentivar comportamentos semelhantes para usuários pouco engajados, tornando-os menos propensos a cancelar sua assinatura.

## Interface

Consulte [Interface](../overview.md#interface) para obter uma visão geral da interface de Análise guiada. As seguintes configurações são específicas dessa análise:

### Painel de consulta

O painel de consulta permite configurar os seguintes componentes:

* **[!UICONTROL Exibir]**: alterne entre esta análise e [Tendências](trends.md).
* **[!UICONTROL Eventos]**: os eventos que você deseja medir. Cada evento selecionado é representado como um gráfico separado. Uma linha que representa o evento de tendência é adicionada à tabela. É possível incluir até cinco eventos.
* **[!UICONTROL Contado como]**: o método de contagem que deseja aplicar aos eventos selecionados. As opções incluem [!UICONTROL Usuários], [!UICONTROL Sessões], [!UICONTROL Porcentagem de usuários] e [!UICONTROL Porcentagem de sessões]. O denominador das métricas baseadas em porcentagem nessa análise são os usuários ou sessões que realizaram os eventos selecionados, não todos os usuários ativos do produto.
* **[!UICONTROL Segmentos]**: os segmentos que você deseja medir. Cada segmento selecionado dobra o número de barras no gráfico e de linhas na tabela. É possível incluir até cinco segmentos.

### Configurações de gráficos

A Análise de [!UICONTROL frequência] oferece as seguintes configurações de gráfico, que podem ser ajustadas no menu acima do gráfico:

* **[!UICONTROL Tipo de gráfico]**: o tipo de visualização que deseja usar. As opções incluem [!UICONTROL Barra horizontal] e [!UICONTROL Barra empilhada].

### Configurações do compartimento

Determina como o evento é categorizado em grupos (compartimentos). Na exibição da tabela de tendências, os usuários são agrupados com base na frequência de uso no total e em cada intervalo, o que significa que um usuário pode contar para diferentes compartimentos em intervalos distintos.

* **[!UICONTROL Compartimentos automáticos]**: identifique automaticamente o tamanho ideal do compartimento com base na distribuição de dados.
* **[!UICONTROL Compartimentos personalizados]**: personalize como os dados são agrupados em compartimentos.
   * [!UICONTROL De]: o primeiro compartimento. A frequência menor que esse valor é excluída do relatório.
   * [!UICONTROL Para]: a frequência maior que este valor é agrupada no último compartimento.
   * [!UICONTROL Tamanho]: o intervalo do compartimento.

### Comparação de tempo

{{apply-time-comparison}}

### Intervalo de datas

O intervalo de datas desejado para a análise. Há dois componentes nesta configuração:

* **[!UICONTROL Intervalo]**: a granularidade de data com a qual você deseja exibir os dados de tendência. O gráfico e a tabela mostram dados agregados por padrão, com a opção de expandir a tabela para uma exibição de tendências. Na exibição de tendências, os usuários são agrupados com base na frequência de uso no total e em cada intervalo, o que significa que um usuário pode contar para diferentes compartimentos em intervalos distintos.
* **[!UICONTROL Data]**: as datas inicial e final. As predefinições de intervalo de datas contínuo e os intervalos personalizados salvos anteriormente estão disponíveis para fins de praticidade, ou você pode usar o seletor de calendário para escolher um intervalo de datas fixo.


<!--
## Example

See below foran example of the analysis.

![Frequency](../assets/frequency.png)

-->
