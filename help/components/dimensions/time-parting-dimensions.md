---
description: A separação de tempo coleta o carimbo de data e hora de ocorrências coletadas e o divide em dimensões mais significativas, como "Horas do dia" ou "Dias de semana".
title: Dimensões de separação de tempo
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 100%

---


# Dimensões de separação de tempo

A separação de tempo coleta o carimbo de data e hora de ocorrências coletadas e o divide em dimensões mais significativas, como &quot;Horas do dia&quot; ou &quot;Dias de semana&quot;.

As dimensões de separação de tempo são baseadas no fuso horário do conjunto de relatórios ou do conjunto de relatórios virtual. Essas dimensões estão disponíveis no Analysis Workspace e podem ajudar nas seguintes questões:

* Em um intervalo de dados grande, qual é o horário de mais acessos de visitantes ao meu site ou aplicativo?
* Há dias da semana ou horas do dia nas quais a conversão é mais alta no meu site ou aplicativo?
* Como minhas vendas de fim de semana se comparam com as da semana?
* Determinada campanha de marketing gera conversões maiores pela manhã ou à tarde?

>[!NOTE]
>
>As dimensões de separação de tempo só estão disponíveis no Analysis Workspace. Para usar dimensões de separação de tempo em outras soluções do Analysis Workspace, é possível implementar o [plug-in getTimeParting](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/plugins/gettimeparting.html).

As dimensões de separação de tempo no Analysis Workspace incluem:

| Dimensão | Valores de exemplo |
|--- |--- |
| Hora do dia | 0-23 |
| AM/PM | AM, PM |
| Dia da semana | Segunda, terça, quarta, quinta, sexta, sábado, domingo |
| Final de semana/Dia da semana | Final de semana, Dia da semana |
| Dia do mês | 1-31 |
| Mês do ano | Janeiro - Dezembro |
| Dia do ano | 1-366 |
| Trimestre do ano | T1, T2, T3, T4 |
