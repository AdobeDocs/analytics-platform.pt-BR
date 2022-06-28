---
title: Entradas e saídas do painel Tempo gasto com reprodução de mídia
description: Quais são as configurações de entrada e saída do Tempo gasto com reprodução de mídia?
feature: Panels
role: User, Admin
exl-id: 8130e870-9ea6-4f1c-b434-0cbe135e8b68
source-git-commit: a9ba9def94a2f156f6d2d8e59c0155a492c3978c
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 100%

---

# Entradas e saídas do painel Tempo gasto com reprodução de mídia {#Inputs-and-outputs}

É possível personalizar o painel Tempo gasto com reprodução de mídia usando as seguintes configurações de entrada e saída.

## Entradas do painel {#Input}

Você pode configurar o painel Tempo gasto com a reprodução de mídia usando estas configurações de entrada:

| Configuração | Descrição |
|---|---|
| Intervalo de datas do painel | O padrão do intervalo de datas do painel é Hoje. Você pode editá-lo para exibir um único dia ou muitos meses de cada vez.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Granularidade | O padrão de granularidade é Minuto.<br>Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
| Números de resumo do painel | Para visualizar os detalhes de data ou hora do tempo gasto com a reprodução, um número de resumo está disponível. O Máximo mostra detalhes para a simultaneidade de pico. O Mínimo mostra detalhes para o vale. O total soma o tempo total gasto com a reprodução para a seleção. O padrão do painel mostra somente o Máximo, mas você pode alterá-lo para mostrar Mínimo, Total ou qualquer combinação dos três.<br>Se você estiver usando detalhamentos, um número de resumo será exibido para cada um. |
| Detalhamento por séries | Como opção, você pode detalhar sua visualização por segmentos, dimensões, itens de dimensão ou intervalos de datas.<p>- É possível exibir até 10 linhas por vez. Os detalhamentos são limitados a um único nível.</p><p>- Ao arrastar uma dimensão, os itens de dimensão principais serão selecionados automaticamente com base no intervalo de datas do painel selecionado.</p>- Para comparar intervalos de datas, arraste dois ou mais intervalos de datas para o filtro de detalhamento por séries. |
| Formato de tempo | Você pode visualizar o tempo gasto com a reprodução em Horas:Minutes:Segundos (padrão) ou em Minutos (que é exibido em números inteiros, arredondados para .5). |
| Exibição da sequência de data | Se você tiver colocado pelo menos dois segmentos de intervalo de datas como detalhamentos de séries, verá a opção de selecionar sobreposição (padrão) ou sequencial. A sobreposição exibirá as linhas com um início comum do eixo x para que sejam executadas em paralelo, enquanto as sequenciais exibirão as linhas com seu início específico do eixo x. Se os dados se alinharem (por exemplo, o segmento 1 termina às 20h44 e o segmento 2 começa às 20h45), as linhas serão exibidas em sequência. |

### Visualização padrão

![Visualização padrão](../assets/mpts_default_view.png)

## Saída do painel {#Output}

O painel Tempo gasto com a reprodução de mídia retorna um gráfico de linhas e números de resumo para incluir detalhes sobre o tempo máximo, mínimo e/ou a soma do tempo gasto com a reprodução. Na parte superior do painel, uma linha de resumo é fornecida para lembrar das configurações do painel que você selecionou.

A qualquer momento, você pode editar e reconstruir o painel clicando no lápis de edição na parte superior direita.

Se você selecionou o detalhamento por séries, uma linha no gráfico de linha e um número de resumo é exibida para cada:

![saída do tempo gasto com a reprodução de mídia](../assets/mpts_outputs1.png)

### Fonte de dados

A única métrica que pode ser usada nesse painel é Tempo gasto com a reprodução.

| Métrica | Descrição |
|---|---|
| Tempo gasto com a reprodução | Total de horas:minutes:segundos (ou minutos) do conteúdo exibido durante a granularidade selecionada, incluindo pausa, buffer e tempo para iniciar. |
