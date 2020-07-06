---
description: Exemplos de casos de uso da análise de coorte.
keywords: Analysis Workspace
title: Casos de uso da análise de coorte
topic: Reports and analytics
uuid: 5ec46f84-5702-4bc1-a796-874a3abe87c9
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 75%

---


# [!UICONTROL Casos de uso de Análise] de coorte

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html)tradicional. [Saiba mais...](/help/getting-started/cja-aa.md)

Use case examples for [!UICONTROL Cohort Analysis].

## Caso de uso sobre interação com o aplicativo

Suponha que você queira analisar o modo como os usuários usam o aplicativo instalado. Eles instalam e nunca usam o aplicativo? Eles usam por um tempo e depois desistem? Ou eles continuam usando ao longo do tempo?

You can create a six-month [!UICONTROL Cohort Analysis]:

**Granularidade**: mensalmente, de janeiro a junho de 2015

**Métrica de inclusão**: instalações de aplicativos

**Métrica de retorno**: sessões ou inicializações

Os visitantes não contam como *`engaged`* nos meses seguintes, a menos que tenham uma sessão ou, pelo menos, inicializem o aplicativo. [!UICONTROL A Análise] de coorte mostraria padrões de uso em que *`App Install`* sempre ocorre no Mês 0. Você pode notar que o uso diminui no Mês 2, independentemente de quando os usuários instalaram o aplicativo. (Para os usuários que instalaram o aplicativo em janeiro de 2015, o Mês 2 é março de 2015. Para aqueles que instalaram o aplicativo em fevereiro de 2015, o Mês 2 é abril de 2015 e, assim por diante.) Essa análise permite que você envie um email ou uma mensagem automática para todos os usuários durante o segundo mês após a instalação para lembrá-los de usar o aplicativo.

## Caso de uso de assinatura

Você trabalha na Adobe.com e oferece uma assinatura gratuita da Creative Cloud. O objetivo é que os usuários atualizem da versão gratuita para a versão de avaliação de 30 dias ou, em última análise, para a versão paga.

**Granularidade**: mensal

**Métrica de inclusão**: link de download

**Métrica de retorno**: compra paga da Creative Cloud

Using this [!UICONTROL Cohort Analysis], you could see, for example, that anywhere between 8% and 10% of free Creative Cloud users upgrade in the first month after installation, regardless of when they installed. De 12 a 15% atualizam no segundo mês de uso. Depois disso, a atualização diminui significativamente: de 4 a 5% no terceiro mês, de 3 a 4% no quatro mês e de 1 a 2% no quinto mês.

Ao reconhecer que não pode perder os possíveis clientes em três meses, você configura uma campanha de email projetada para ser enviada no meio do terceiro mês para uma amostra de clientes, oferecendo um cupom de US$ 50 aos usuários que ainda não fizeram a atualização.

Verifique novamente o seu relatório de análise de coorte alguns meses depois. Para os grupos formados após o lançamento da campanha, a conversão para assinaturas pagas da Creative Cloud no terceiro mês subiu de 4-5% para 13-14%, resultando em centenas de milhares de dólares por coorte, para cada coorte mensal que atingir três meses a partir desse ponto em diante.

## Caso de uso de segmentos de coorte complexos

Uma grande cadeia de hotéis tem como alvo vários grupos de clientes para promoções e os monitora em relação ao desempenho. Para identificar os melhores grupos de coortes de usuário para fins de direcionamento, deve-se criar grupos de coorte muito específicos. Using the augmented [!UICONTROL Inclusion] and [!UICONTROL Return] Criteria within [!UICONTROL Cohort] Tables, they are able to define just the right cohort groupings with multiple metrics and segments to identify underperforming customers groups in order to target them with promotions and deals to increase bookings.

## Caso de uso de preferência de versão do aplicativo

Uma grande empresa de seguros impulsiona muito engajamento de cliente por meio de seu aplicativo para dispositivos móveis. Entretanto, conforme novos recursos são adicionados ao aplicativo, é de enorme importância que os clientes atualizem para a versão mais recente. They can analyze and compare all of their app versions side-by-side using [!UICONTROL Custom Dimension] Cohort to see which customers on which app version to target. Além disso, pode-se monitorar a retenção e o churn para ver se versões específicas do aplicativo estão causando a interrupção do uso do aplicativo ao longo do tempo. Por meio de mensagens em dispositivos móveis, a empresa pode voltar a engajar esses clientes para que atualizem para a versão mais recente e aproveitem os últimos recursos.

## Caso de uso de adesão de campanha

Uma empresa de mídia multinacional usa campanhas direcionadas para direcionar usuários a suas várias plataformas para gerar engajamento. O gasto com anúncios por plataforma baseia-se no engajamento e na retenção do cliente. Portanto, campanhas bem-sucedidas são essenciais para o sucesso dos negócios. They use our new [!UICONTROL Custom Dimension] Cohort feature in [!UICONTROL Cohort] Tables to compare various campaigns side-by-side to identify which campaigns are most effective at acquiring and retaining users to increase engagement. Podem identificar quais aspectos tornam uma campanha bem-sucedida e aplicá-los a outras campanhas para aumentar o engajamento nas várias plataformas.

## Caso de uso de lançamento de produto

Uma grande varejista de vestuário tem muitos segmentos de clientes específicos que geram grandes parcelas de receita para seus negócios. Cada segmento tem produtos específicos projetados e criados com o segmento em mente. A cada lançamento de produto, a empresa quer saber como o novo produto impulsionou as vendas para vários coortes ao longo do tempo. Using the new [!UICONTROL Latency Table] setting in [!UICONTROL Cohort Analysis], they are able to analyze a given customer segment&#39;s pre-launch and post-launch behavior and revenue. Usando essas informações, pode-se identificar quais produtos estão gerando novas receitas e quais não estão ganhando força com os clientes.

## Caso de uso de adesão individual: usuários mais fiéis

Uma grande companhia aérea obtém a maior parte de seu sucesso e receita por meio de clientes repetidos e fiéis. Em muitos casos, seus viajantes fiéis compõem a maior parte de sua receita e manter esses clientes é fundamental para o sucesso a longo prazo. Identificar os clientes mais leais e consistentes pode ser difícil. However, using the new [!UICONTROL Rolling Calculation] setting in [!UICONTROL Cohort Analysis], they were able to analyze loyal customer segments and find out which travelers were repeat purchasers month-over-month. Então, foi possível direcionar a esses viajantes recompensas e benefícios por sua fidelidade. Além disso, ao alternar o tipo de coorte de retenção para rotatividade (churn), também pode-se identificar quais clientes não eram compradores recorrentes mês a mês e direcionar esses segmentos com promoções, a fim de retomar o engajamento e garantir que permanecessem fiéis no futuro.
