---
title: Segmentação em feeds de dados do Customer Journey Analytics
description: Saiba como aplicar segmentos aos feeds de dados do Customer Journey Analytics e entenda como os segmentos de intervalo de datas interagem com a janela de relatórios do feed.
keywords: sequência de cliques;feed de dados;feed de dados;segmentação;segmentos;intervalo de datas
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: f36723dab5500f728dd9ec267d97305aff604149
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---


# Segmentação em feeds de dados

{{release-limited-testing}}

Os feeds de dados no Customer Journey Analytics são compatíveis com a segmentação, permitindo filtrar quais linhas são incluídas em cada entrega de feed. Você pode aplicar segmentos no nível de visualização de dados, no nível de feed ou em ambos.

## Onde os segmentos são aplicados

Você pode aplicar segmentos a um feed de dados em dois lugares:

- **Visualização de dados**: um segmento configurado na visualização de dados que se aplica a todos os feeds que usam essa visualização de dados.
- **Feed de dados**: um segmento aplicado diretamente a um feed individual, além de qualquer segmento de visualização de dados.

Quando ambos são configurados, o Customer Journey Analytics os combina — somente as linhas que satisfazem ambos os segmentos são incluídas na saída do feed.

## Segmentos de intervalo de datas

Segmentos que fazem referência a intervalos de datas são aceitos em feeds de dados. No entanto, o comportamento difere do Analysis Workspace de forma importante: **as condições do intervalo de datas em um segmento não substituem o intervalo de datas do feed.**

No Analysis Workspace, a aplicação de um segmento de intervalo de datas altera a janela de relatório ativa para corresponder ao intervalo de datas do segmento. Nos feeds de dados, a janela de relatório é sempre definida pela entrega agendada do feed (por hora ou por dia). Um segmento com uma condição de intervalo de datas filtra linhas nessa janela — ele não desloca ou expande a própria janela.

Esse design é intencional. Permitir que os segmentos de intervalo de datas substituam a janela de relatórios pode fazer com que um feed por hora forneça uma janela de dados muito maior do que o esperado, resultando na duplicação de dados ou no volume de saída excessivo.

### Exemplos

**Exemplo 1 — Segmento que inclui eventos de uma data específica**

Suponha que você aplique um segmento que retorne somente eventos de 1º de julho e execute o feed de 22 de julho:

- A janela de entrega do feed permanece até 22 de julho.
- O segmento filtra todas as linhas, pois nenhum evento na janela de 22 de julho corresponde aos critérios de 1º de julho. O feed é executado, mas não fornece linhas.
- Se você executar um preenchimento retroativo para 1º de julho, o segmento se comporta conforme esperado — somente os eventos que correspondem aos critérios de 1º de julho são incluídos.

**Exemplo 2 — Segmento que exclui eventos de uma data específica**

Suponha que você aplique um segmento que exclua todos os eventos com uma ordem em 1º de julho e execute o feed de 22 de julho:

- O segmento se aplica aos dados de 22 de julho. Como não há eventos de 1° de julho na janela de 22 de julho, nada é excluído e todas as linhas são entregues.
- Se você executar um preenchimento retroativo para 1º de julho, o segmento excluirá as linhas relevantes, conforme esperado.

## Segmentos com várias condições

Para segmentos que combinam condições de intervalo de datas com outros critérios, o Customer Journey Analytics avalia a parte do intervalo de datas somente como um filtro de linha, não como uma substituição da janela de relatório. Todas as condições no segmento são honradas na janela de entrega do feed.

## Qualificação do segmento e o intervalo de datas da pesquisa

Para segmentos que usam um contêiner de Pessoa ou Sessão, a qualificação é determinada pela configuração **Intervalo de datas de retrospectiva**, não apenas pela janela de entrega. Se uma pessoa se qualificar dentro do intervalo de datas da retrospectiva, todos os eventos dessa pessoa na janela de distribuição serão incluídos. A configuração do contêiner determina o escopo:

- **Contêiner de eventos**: somente eventos que correspondem aos critérios do segmento na janela de entrega são incluídos.
- **Contêiner de sessão**: todos os eventos em sessões qualificadas dentro da janela de entrega são incluídos, onde a qualificação de sessão é avaliada durante o intervalo de datas da retrospectiva.
- **Contêiner de pessoa**: todos os eventos na janela de entrega são incluídos para qualquer pessoa que se qualifique durante o intervalo de datas da retrospectiva.

Para obter mais informações sobre o intervalo de datas da retrospectiva e como ele afeta a qualificação de segmento, consulte [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).

## Comparação com o Analysis Workspace

| Comportamento | Analysis Workspace | Feeds de dados |
|---|---|---|
| Janela de relatórios de sobreposições de segmento de intervalo de datas | Sim | Não |
| Linhas de filtros de segmento na janela de relatórios | Sim | Sim |
| O segmento de visualização de dados se aplica | Sim | Sim |
| Segmento adicional aplicado diretamente ao delivery | Não | Sim |

{style="table-layout:auto"}
