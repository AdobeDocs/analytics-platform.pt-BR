---
description: Saiba mais sobre exemplos de casos de uso para análise de coorte.
keywords: Analysis Workspace
title: Casos de uso da análise de coorte
feature: Visualizations
exl-id: f559d4b4-b682-4306-b111-22acb26fe0a0
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 99%

---

# Casos de uso da [!UICONTROL análise de coorte]

Exemplos de casos de uso da [!UICONTROL análise de coorte].

## Caso de uso sobre interação com o aplicativo

Suponha que você queira analisar o modo como os usuários usam o aplicativo instalado. Eles instalam e nunca usam o aplicativo? Eles usam por um tempo e depois desistem? Ou eles continuam usando ao longo do tempo?

Você pode criar uma [!UICONTROL análise de coorte] de seis meses:

**Granularidade**: mensalmente, de janeiro a junho de 2015

**Métrica de inclusão**: instalações de aplicativos

**Métrica de retorno**: sessões ou inicializações

Os visitantes não contam como *`engaged`* nos meses seguintes, a menos que tenham uma sessão ou, pelo menos, inicializem o aplicativo. A [!UICONTROL análise de coorte] mostraria padrões de uso em que sempre *`App Install`* ocorre no Mês 0. Você pode notar que o uso diminui no Mês 2, independentemente de quando os usuários instalaram o aplicativo. (Para os usuários que instalaram o aplicativo em janeiro de 2015, o Mês 2 é março de 2015. Para aqueles que instalaram o aplicativo em fevereiro de 2015, o Mês 2 é abril de 2015 e, assim por diante.) Essa análise permite que você envie um email ou uma mensagem automática para todos os usuários durante o segundo mês após a instalação para lembrá-los de usar o aplicativo.

## Caso de uso de assinatura

Você trabalha na Adobe.com e oferece uma assinatura gratuita da Creative Cloud. O objetivo é que os usuários atualizem da versão gratuita para a versão de avaliação de 30 dias ou, em última análise, para a versão paga.

**Granularidade**: mensal

**Métrica de inclusão**: link de download

**Métrica de retorno**: compra paga da Creative Cloud

Com essa [!UICONTROL análise de coorte], você pode observar, por exemplo, que entre 8% e 10% dos usuários gratuitos da Creative Cloud atualizam no primeiro mês após a instalação, independentemente de quando ela foi feita. De 12 a 15% atualizam no segundo mês de uso. Depois disso, a atualização diminui significativamente: de 4 a 5% no terceiro mês, de 3 a 4% no quatro mês e de 1 a 2% no quinto mês.

Ao reconhecer que não pode perder os possíveis clientes em três meses, você configura uma campanha de email projetada para ser enviada no meio do terceiro mês para uma amostra de clientes, oferecendo um cupom de US$ 50 aos usuários que ainda não fizeram a atualização.

Verifique novamente o seu relatório de análise de coorte alguns meses depois. Para os grupos formados após o lançamento da campanha, a conversão para assinaturas pagas da Creative Cloud no terceiro mês subiu de 4-5% para 13-14%, resultando em centenas de milhares de dólares por coorte, para cada coorte mensal que atingir três meses a partir desse ponto em diante.

## Caso de uso de filtros de coorte complexos

Uma grande cadeia de hotéis tem como alvo vários grupos de clientes para promoções e os monitora em relação ao desempenho. Para identificar os melhores grupos de coortes de usuário para fins de direcionamento, deve-se criar grupos de coorte muito específicos. Usando os critérios aumentados de [!UICONTROL Inclusão] e [!UICONTROL Retorno] em Tabelas de [!UICONTROL coorte], é possível definir os grupos de coorte ideais com várias métricas e filtros para identificar grupos de clientes com baixo desempenho e assim direcionar a tais grupos promoções e ofertas para aumentar a taxa de reservas.

## Caso de uso de preferência de versão do aplicativo

Uma grande empresa de seguros impulsiona muito engajamento de cliente por meio de seu aplicativo para dispositivos móveis. Entretanto, conforme novos recursos são adicionados ao aplicativo, é de enorme importância que os clientes atualizem para a versão mais recente. É possível analisar e comparar todas as versões do aplicativo lado a lado usando o Coorte de [!UICONTROL dimensão personalizado] para ver quais clientes e suas respectivas versões do aplicativo para direcionar. Além disso, pode-se monitorar a retenção e o churn para ver se versões específicas do aplicativo estão causando a interrupção do uso do aplicativo ao longo do tempo. Por meio de mensagens em dispositivos móveis, a empresa pode voltar a engajar esses clientes para que atualizem para a versão mais recente e aproveitem os últimos recursos.

## Caso de uso de adesão de campanha

Uma empresa de mídia multinacional usa campanhas direcionadas para direcionar usuários a suas várias plataformas para gerar engajamento. O gasto com anúncios por plataforma baseia-se no engajamento e na retenção do cliente. Portanto, campanhas bem-sucedidas são essenciais para o sucesso dos negócios. A empresa usa nosso novo recurso [!UICONTROL Coorte de dimensão] personalizado em Tabelas de [!UICONTROL coorte] para comparar várias campanhas lado a lado, para identificar quais campanhas são mais eficazes para conquistar e reter usuários para aumentar o engajamento. Podem identificar quais aspectos tornam uma campanha bem-sucedida e aplicá-los a outras campanhas para aumentar o engajamento nas várias plataformas.

## Caso de uso de lançamento de produto

Uma grande varejista de vestuário tem muitos filtros de clientes específicos que geram grandes parcelas de receita para seus negócios. Cada filtro tem produtos específicos projetados e criados com o filtro em mente. A cada lançamento de produto, a empresa quer saber como o novo produto impulsionou as vendas para vários coortes ao longo do tempo. Usando a nova configuração de [!UICONTROL Tabela de latência] na [!UICONTROL Análise de coorte], é possível analisar o comportamento e a receita de pré-lançamento e pós-lançamento de um determinado filtro de cliente. Usando essas informações, pode-se identificar quais produtos estão gerando novas receitas e quais não estão ganhando força com os clientes.

## Caso de uso de adesão individual: usuários mais fiéis

Uma grande companhia aérea obtém a maior parte de seu sucesso e receita por meio de clientes repetidos e fiéis. Em muitos casos, seus viajantes fiéis compõem a maior parte de sua receita e manter esses clientes é fundamental para o sucesso a longo prazo. Identificar os clientes mais leais e consistentes pode ser difícil. Entretanto, usando a nova configuração [!UICONTROL Cálculo contínuo] na [!UICONTROL Análise de coorte], foi possível analisar filtros de clientes fiéis e descobrir quais viajantes eram compradores recorrentes mês a mês. Então, foi possível direcionar recompensas e benefícios a esses viajantes por sua fidelidade. Além disso, ao alternar o tipo de coorte desde a retenção até o churn, também pode-se identificar quais clientes não eram compradores recorrentes mês a mês e direcionar esses filtros com promoções, a fim de retomar o engajamento e garantir que permanecessem fiéis no futuro.
