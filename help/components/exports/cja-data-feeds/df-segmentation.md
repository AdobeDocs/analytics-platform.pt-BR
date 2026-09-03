---
title: Segmentação em feeds de dados
description: Saiba como aplicar segmentos aos feeds de dados do Customer Journey Analytics e entenda como os segmentos de intervalo de datas interagem com a janela de relatórios do feed.
keywords: sequência de cliques;feed de dados;feed de dados;segmentação;segmentos;intervalo de datas
feature: Components
hide: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: c7fc5df2a0fd7393b48bfe6bdfa7dccdfffde46c
workflow-type: tm+mt
source-wordcount: 357
ht-degree: 0%

---


# Segmentação em feeds de dados

{{release-limited-testing}}

Os feeds de dados no Customer Journey Analytics são compatíveis com a segmentação, permitindo filtrar quais linhas são incluídas em cada entrega de feed. Você pode aplicar segmentos no nível de visualização de dados, no nível de feed ou em ambos.

## Onde os segmentos são aplicados

Você pode aplicar segmentos a um feed de dados em dois lugares:

- **Visualização de dados**: um segmento configurado na visualização de dados que se aplica a todos os feeds que usam essa visualização de dados.
- **Feed de dados**: um segmento aplicado diretamente a um feed individual, além de qualquer segmento de visualização de dados.

Quando ambos são configurados, o Customer Journey Analytics os combina — somente as linhas que satisfazem ambos os segmentos são incluídas na saída do feed.

## Segmentos que incluem um intervalo de datas

Você pode usar segmentos que incluem intervalos de datas em um feed de dados. No entanto, a janela de relatório é sempre definida pelo delivery agendado do feed (por hora ou por dia). Se um segmento contiver um intervalo de datas, ele filtrará as linhas na janela do feed de dados sem alterar ou expandir a própria janela.

Isso é diferente do Analysis Workspace, onde a aplicação de um segmento que inclui um intervalo de datas altera a janela de relatório ativa para corresponder ao intervalo de datas do segmento.

## Qualificação do segmento e o intervalo de datas da pesquisa

Para segmentos que usam um contêiner de Pessoa ou Sessão, a qualificação é determinada pela configuração **Intervalo de datas de retrospectiva**, não apenas pela janela de entrega. Se uma pessoa se qualificar dentro do intervalo de datas da retrospectiva, todos os eventos dessa pessoa na janela de distribuição serão incluídos. A configuração do contêiner determina o escopo:

- **Contêiner de eventos**: somente eventos que correspondem aos critérios do segmento na janela de entrega são incluídos.
- **Contêiner de sessão**: todos os eventos em sessões qualificadas dentro da janela de entrega são incluídos, onde a qualificação de sessão é avaliada durante o intervalo de datas da retrospectiva.
- **Contêiner de pessoa**: todos os eventos na janela de entrega são incluídos para qualquer pessoa que se qualifique durante o intervalo de datas da retrospectiva.

Para obter mais informações sobre o intervalo de datas da retrospectiva e como ele afeta a qualificação de segmento, consulte [Criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).

