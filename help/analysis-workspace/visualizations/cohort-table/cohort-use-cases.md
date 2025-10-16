---
description: Saiba mais sobre alguns exemplos de casos de uso para análise de coorte.
keywords: Analysis Workspace
title: Xases de uso da análise de coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 21%

---

# Casos de uso da análise de coorte

Este artigo descreve alguns exemplos de casos de uso da análise de coorte.

## Caso de uso sobre interação com o aplicativo

Suponha que você queira analisar como os usuários que instalam seu aplicativo se envolvem com ele ao longo do tempo. Eles o instalam e nunca o usam? Eles usam por um tempo, depois caem? Ou eles permanecem engajados ao longo do tempo?

Você pode criar uma análise de coorte de seis meses.

**Granularidade**: mensalmente, de janeiro a junho de 2015

**Métrica de inclusão**: instalações de aplicativos

**Retornar métrica**: sessões ou inicializações

As pessoas não contam como *engajadas* nos meses seguintes, a menos que tenham uma sessão ou, pelo menos, inicializem o aplicativo. A [!UICONTROL Análise de coorte] mostraria padrões de uso em que a *Instalação do aplicativo* sempre ocorre no Mês 0. Você pode notar que o uso diminui no Mês 2, independentemente de quando os usuários instalaram o aplicativo. (Para os usuários que instalaram o aplicativo em janeiro de 2015, o Mês 2 é março de 2015. Para as pessoas que instalaram o aplicativo em fevereiro de 2015, o Mês 2 é abril de 2015 e assim por diante.) Essa análise permite enviar um email ou uma mensagem por push a todos os usuários durante o segundo mês após a instalação do aplicativo, para lembrá-los de usar o aplicativo.

## Caso de uso de assinatura

Você trabalha em Adobe.com e oferece uma assinatura gratuita do Creative Cloud. O objetivo é que os usuários atualizem da versão gratuita para a versão de avaliação de 30 dias ou, em última análise, a versão paga.

**Granularidade**: mensalmente

**Métrica de inclusão**: link de download

**Métrica de retorno**: Compre o Creative Cloud pago

Com a [!UICONTROL Análise de coorte], você pode observar, por exemplo, que entre 8% e 10% dos usuários gratuitos do Creative Cloud atualizam no primeiro mês após a instalação. Independentemente de quando os usuários instalaram o. Atualização de 12 a 15% no segundo mês de uso. Depois disso, a atualização diminui significativamente: 4-5% no terceiro mês, 3-4% no quarto mês e 1-2% no quinto mês.

Você não deseja perder clientes em potencial no terceiro mês. Assim, você configurou uma campanha de email projetada para sair no meio do terceiro mês para uma amostra de usuários. Oferecer um cupom de US$ 50 para usuários que ainda não atualizaram.

Verifique com seus relatórios de análise de coorte alguns meses depois. Para coortes formados após o lançamento da campanha, a conversão para assinaturas pagas do Creative Cloud no terceiro mês aumentou de 4-5% para 13-14%. Esse aumento na conversão resulta em centenas de milhares de dólares por coorte para cada coorte mensal que chega ao terceiro mês a partir desse ponto.

## Caso de uso de segmentos de coorte complexos

Uma grande cadeia de hotéis tem como alvo vários grupos de clientes para promoções e controles contra o desempenho. Para identificar os melhores grupos de coortes de usuários a serem direcionados, é necessário criar grupos de coorte muito específicos. Usando os critérios aumentados de [!UICONTROL Inclusão] e [!UICONTROL Retorno] nas Tabelas de [!UICONTROL Coorte], a cadeia de hotéis pode definir os grupos de coorte ideais com várias métricas e segmentos. Assim, a cadeia de hotéis pode identificar grupos de clientes com baixo desempenho para direcionar clientes com promoções e ofertas para aumentar as reservas.

## Caso de uso de preferência de versão do aplicativo

Uma grande empresa de seguros promove o engajamento do cliente por meio do uso de seu aplicativo móvel. No entanto, à medida que novos recursos são adicionados ao aplicativo, é importante que os clientes atualizem para a versão mais recente do aplicativo. É possível analisar e comparar todas as versões do aplicativo lado a lado usando o Coorte de [!UICONTROL dimensão personalizado] para ver quais clientes e suas respectivas versões do aplicativo para direcionar. Além disso, eles podem rastrear a retenção e a rotatividade para ver se versões específicas do aplicativo estão afastando os clientes do uso do aplicativo ao longo do tempo. Por meio de esforços de mensagens móveis, eles podem reengajar com esses usuários para atualizá-los para a versão mais recente e aproveitar seus recursos mais recentes.

## Caso de uso de adesão de campanha

Uma empresa multinacional de mídia usa campanhas direcionadas para direcionar os usuários para suas várias plataformas, gerando engajamento. O gasto de anúncios por plataforma baseia-se no envolvimento e na retenção do cliente; portanto, campanhas bem-sucedidas são essenciais para o sucesso dos negócios. Eles usam o novo recurso de Coorte do [!UICONTROL Dimension] personalizado em Tabelas de [!UICONTROL Coorte] para comparar várias campanhas lado a lado, para identificar quais campanhas são mais eficazes para conquistar e reter usuários para aumentar o engajamento. Podem identificar quais aspectos tornam uma campanha bem-sucedida e aplicá-los a outras campanhas para aumentar o engajamento nas várias plataformas.

## Caso de uso de lançamento de produto

Uma grande retailer de vestuário tem muitos segmentos específicos de clientes que geram grandes parcelas de receita para seus negócios. Cada segmento tem produtos específicos projetados e criados com o segmento em mente. A cada lançamento de produto, a empresa quer saber como o novo produto impulsionou as vendas para vários coortes ao longo do tempo. Usando a nova configuração de [!UICONTROL Tabela de latência] na [!UICONTROL Análise de coorte], é possível analisar o comportamento e a receita de pré-lançamento e pós-lançamento de um determinado segmento de cliente. Usando essas informações, pode-se identificar quais produtos estão gerando novas receitas e quais não estão ganhando força com os clientes.

## Caso de uso de adesão individual: usuários mais fiéis

Uma grande companhia aérea obtém a maior parte de seu sucesso e receita por meio de clientes repetidos e fiéis. Em muitos casos, seus viajantes fiéis compõem a maior parte de sua receita e manter esses clientes é fundamental para o sucesso a longo prazo. Identificar os clientes mais leais e consistentes pode ser difícil. Entretanto, usando a nova configuração [!UICONTROL Cálculo contínuo] em [!UICONTROL Análise de coorte], a companhia aérea pode analisar segmentos de clientes fiéis e descobrir quais viajantes eram compradores recorrentes mês a mês. A companhia aérea também é capaz de direcionar a esses viajantes recompensas e benefícios por sua fidelidade. Além disso, ao alternar o tipo de coorte de retenção para churn, a companhia aérea pode identificar quais clientes não são compradores recorrentes mês a mês e direcionar esses clientes com promoções. Assim, a companhia aérea pode reengajar-se com esses clientes e garantir que eles permaneçam fiéis no futuro.
