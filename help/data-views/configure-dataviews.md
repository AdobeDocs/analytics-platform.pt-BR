---
title: Configurar exibições de dados e atribuição
description: Descreve como criar uma visualização de dados para um conjunto de dados da plataforma no Customer Journey Analytics
translation-type: ht
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: ht
source-wordcount: '1523'
ht-degree: 100%

---


# Configurações de componente e atribuição

eVars, props e eventos no sentido tradicional do Adobe Analytics não existem mais no Customer Journey Analytics. Em vez disso, você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Todas as configurações de atribuição usadas para aplicar a eVars e props durante o processo de coleta de dados agora são aplicadas no momento do query - também conhecido como processamento no tempo do relatório.

Clique [aqui](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) para obter uma visão geral do vídeo.

Lembre-se disso antes de aplicar as configurações de atribuição:

* Na interface do usuário das visualizações de dados, especifique a atribuição padrão. **Observação**: posteriormente, você poderá substituir essas configurações em projetos do Workspace. No entanto, essa funcionalidade não está disponível no momento.

* As configurações de atribuição no Customer Journey Analytics não são destrutivas e retroativas. Em outras palavras, você não pode prejudicar irreparavelmente seus conjuntos de dados no Customer Journey Analytics. Mesmo que você exclua algo acidentalmente, sempre é possível voltar à [!UICONTROL Experience Platform] e trazer o conjunto de dados de volta. (Tenha em mente, no entanto, que trazer o conjunto de dados de volta implica custos adicionais.)

* Se você quiser ter uma dimensão &quot;comporte-se&quot; como um eVar tradicional (variável de conversão), configure-a com a atribuição &quot;Visita de último toque&quot; por padrão.

* Se você quiser ter uma dimensão &quot;comporte-se&quot; como uma prop tradicional (variável de tráfego), configure-a com a atribuição &quot;Mesmo toque&quot; por padrão.

* Se você quiser ter uma métrica &quot;comporte-se&quot; como uma métrica padrão, não é necessário alterar nada.

* As configurações de atribuição de métricas substituem as configurações de atribuição de dimensões.

## Especificar configurações de componente e atribuição

Depois de [definir e salvar configurações de visualização de dados](/help/data-views/create-dataview.md) e componentes adicionados, você estará pronto para especificar configurações de atribuição, se optar por fazê-lo. Você pode especificar configurações de atribuição/expiração/pesquisa para dimensões e métricas. Se, por exemplo, você quiser que a atribuição de uma dimensão persista, você provavelmente desejará definir um tempo de expiração personalizado. Por exemplo, se você quiser que uma dimensão &quot;Código de rastreamento&quot; (uma variável de campanha) seja definida como uma atribuição &quot;Último contato&quot; para persistir por uma semana, adicione uma expiração personalizada de uma semana.

>[!IMPORTANT]
>Você pode optar por não definir a alocação/expiração. Nesse caso, as dimensões se comportarão como props (modelo de atribuição &quot;Mesmo toque&quot;). As métricas sem configurações de atribuição definidas herdarão as configurações da dimensão à qual essa métrica é aplicada.

![](assets/edit-component.png)

1. Especifique as configurações de componente e atribuição para dimensões e métricas. Consulte a seção abaixo para obter informações sobre configurações individuais.

1. Clique em **[!UICONTROL Salvar]** para salvar a visualização de dados.


### Configuração do componente

É possível alterar o nome da métrica ou da dimensão para algo mais simples. Observe que o nome subjacente não é alterado, apenas o nome de exibição.

### Modelo de atribuição

O modelo descreve a distribuição de conversões para os eventos em um grupo. Por exemplo, primeiro ou último contato. Determina como o Customer Journey Analytics atribuirá crédito por um evento bem-sucedido se uma variável receber vários valores antes do evento.

| Ícone da interface do usuário | Modelo de atribuição | Definição | Quando usar |
| --- | --- | --- | --- |
| ![Último contato](assets/last_touch1.png) | Último contato | Dá 100% de crédito ao ponto de contato mais recente antes da conversão. | É o modelo de atribuição mais básico e comum. É utilizado com frequência para conversões com um ciclo de curto consideração. O modelo Último contato é usado por equipes responsáveis por gerenciar marketing de pesquisa ou analisar palavras-chave de pesquisa interna. |
| ![Primeiro contato](assets/first_touch.png) | Primeiro contato | Dá 100% de crédito ao primeiro ponto de contato visto na janela de retrospectiva de atribuição. | Também é um modelo de atribuição comum e útil para analisar canais de marketing com o fim de impulsionar a percepção da marca ou a conquista de clientes. O modelo Primeiro contato é usado com frequência por equipes de marketing de exibição ou de marketing social, mas também é útil para avaliar a eficiência das recomendações locais de produtos. |
| ![Mesmo contato](assets/same_touch.png) | Mesmo contato | Dá 100% de crédito à ocorrência em que ocorreu a conversão. Se o ponto de contato e a conversão não estiverem relacionados com a mesma ocorrência, o ponto de contato será agrupado em “Nenhum”. | Este modelo é útil para avaliar o conteúdo ou a experiência do usuário apresentados no momento da conversão. Equipes de produto ou de design geralmente usam esse modelo para avaliar a eficácia de uma página na qual ocorre a conversão. |
| ![Linear](assets/linear.png) | Linear | Dá crédito igual a todos os pontos de contato que resultem em uma conversão. | Este modelo é útil para conversões com ciclos de consideração mais longos ou experiências do usuário que requerem um engajamento do cliente mais frequente. A atribuição linear é usada com frequência por equipes de produtos com base em assinatura ou responsáveis por medir a eficácia de notificações de aplicativos móveis. |
| ![Forma de U](assets/u_shaped.png) | Forma de U | Dá crédito de 40% à primeira interação, de 40% à última interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 50% para ambos. | É um ótimo modelo para quem valoriza as interações que introduziram ou concluíram uma conversão, mas ainda quer reconhecer as interações de assistência. O modelo em Forma de U é usado com frequência por equipes que têm uma abordagem mais equilibrada, mas desejam atribuir mais crédito a canais que introduziram ou concluíram uma conversão. |
| ![Forma de J](assets/j_shaped.png) | Forma de J | Dá crédito de 60% à última interação, de 20% à primeira interação, e divide os 20% restantes para os pontos de contato entre as duas. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a última interação e de 25% para a primeira. | Esse modelo é excelente para quem prioriza a descoberta e a conclusão de conversões, mas quer se concentrar em interações de conclusão. A atribuição em Forma de J é frequentemente usada por equipes com uma abordagem mais equilibrada, que desejam atribuir mais crédito a canais que concluíram uma conversão. |
| ![Forma de J invertido](assets/inverse_j.png) | J invertido | Dá 60% de crédito ao primeiro ponto de contato, 20% de crédito ao último ponto de contato e divide os 20% restantes para os pontos de contato entre os dois. Para conversões com um só ponto de contato, o crédito é de 100%. Para conversões com dois pontos de contato, o crédito é de 75% para a primeira interação e de 25% para a última. | Esse modelo é ideal para quem prioriza a descoberta e a conclusão de conversões, mas quer focalizar a descoberta de interações. A atribuição em forma de J invertido é frequentemente usada por equipes com uma abordagem mais equilibrada, que desejam atribuir mais crédito a canais que iniciaram uma conversão. |
| ![Personalizado](assets/custom.png) | Personalizado | Permite que você especifique os pesos que deseja atribuir ao primeiro, ao último e ao resto de pontos de contato. Os valores especificados são regularizados para 100% mesmo se os números inseridos, quando somados, não resultarem em 100. Para conversões com um só ponto de contato, o crédito é de 100%. Para interações com dois pontos de contato, o parâmetro intermediário é ignorado. O primeiro e o último ponto de contato são normalizados para 100% e o crédito é atribuído em conformidade. | Esse modelo é perfeito para quem quer controle total sobre seu modelo de atribuição e tem necessidades específicas que outros modelos de atribuição não atendem. |
| ![Declínio de tempo](assets/time_decay.png) | Declínio de tempo | Segue um declínio exponencial com um parâmetro personalizado de meia-vida e padrão de 7 dias. O peso de cada canal depende da quantidade de tempo decorrido entre a iniciação do ponto de contato e a conversão final. A fórmula usada para determinar o crédito é `2`<sup>`(-t/halflife)`</sup>, em que `t` é o tempo entre um ponto de contato e uma conversão. Todos os pontos de contato são normalizados para 100%. | Ideal para equipes que fazem publicidade em vídeos ou marketing para eventos com data predeterminada. Quanto mais tarde ocorrer uma conversão após um evento de marketing, menos crédito será dado. |
| ![Participação](assets/participation.png) | Participação | Dá 100% de crédito a todos os pontos de contato exclusivos. O número total de conversões aumenta em comparação com outros modelos de atribuição. A participação remove a duplicação de canais que são vistos várias vezes. | Excelente para identificar a quem os clientes são expostos com frequência em uma determinada interação. As organizações de mídia usam esse modelo frequentemente para calcular a velocidade do conteúdo. As varejistas geralmente usam esse modelo para identificar as partes do site que são essenciais para a conversão. |

### Expiração

Especifica o período ou evento após o qual o item de dimensão expira (não recebe mais crédito por eventos bem-sucedidos). Você pode definir a expiração da atribuição no nível da sessão, pessoa ou personalizado.

| Configuração | Definição |
|---|---|
| Sessão | Anteriormente conhecido como o nível de &quot;Visita&quot;. Os eventos de conversão além da exibição de página ou da sessão não estão associados à dimensão ou métrica. |
| Pessoa (Janela Relatórios) | Anteriormente conhecido como o nível &quot;Visitante&quot;. Eventos de conversão não vinculados a essa pessoa não estão associados à dimensão ou métrica. |
| Tempo personalizado | Especifique os minutos, horas, dias, meses ou trimestres personalizados. Os eventos de conversão além do período especificado não estão associados à dimensão ou métrica. |

Para obter mais informações, consulte o [documento Attribution IQ](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/attribution/models.html).

### Janela de lookback

As janelas de retrospectiva representam quanto tempo uma conversão deve retroceder para incluir pontos de contato. Os modelos de atribuição que dão mais crédito às primeiras interações veem diferenças maiores ao exibir diferentes janelas de retrospectiva.

* **Sessão:** retroage até o início de uma sessão em que ocorreu uma conversão. As janelas de retrospectiva de visita são pequenas, pois não consideram nada além da sessão. As janelas de retrospectiva de sessão respeitam a definição de visita modificada nas visualizações de dados.
* **Pessoa (janela de relatórios):** verifica todas as sessões até o primeiro dia do mês do intervalo de datas atual. As janelas de retrospectiva de pessoa são amplas, pois podem abranger muitas sessões. Por exemplo, se o intervalo de datas de um relatório for de 15 a 30 de setembro, o intervalo de datas da retrospectiva da pessoa será de 1º a 30 de setembro.
