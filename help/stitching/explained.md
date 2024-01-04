---
title: Como funciona a compilação
description: Entenda o conceito de compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 20%

---

# Como funciona a compilação

A compilação faz um mínimo de duas passagens de dados em um determinado conjunto de dados:

* **Compilação em tempo real**: tenta compilar cada ocorrência (evento) à medida que ela chega. As ocorrências de dispositivos que são &quot;novas&quot; para o conjunto de dados (nunca foram autenticadas) normalmente não são compiladas neste nível. As ocorrências de dispositivos já reconhecidos são compiladas imediatamente.

* **Reproduzir compilação novamente**: &quot;repete&quot; dados com base em identificadores exclusivos (IDs transitórias) que ele aprendeu. É nesse estágio que as ocorrências de dispositivos desconhecidos anteriormente (IDs persistentes) são compiladas (em IDs transitórias). A Adobe oferece dois intervalos de repetição:
   * **Diariamente**: os dados são repetidos todos os dias com uma janela de retrospectiva de 24 horas. Essa opção tem a vantagem de que as repetições são muito mais frequentes, mas os visitantes não autenticados devem se autenticar no mesmo dia em que visitam o site.
   * **Semanalmente**: os dados são repetidos uma vez por semana com uma janela de retrospectiva de sete dias. Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, os dados não compilados com menos de uma semana não são reprocessados até a próxima repetição semanal.

* **Privacidade (opcional)**: quando solicitações relacionadas à privacidade são recebidas, além de remover a identidade solicitada, qualquer compilação dessa identidade em eventos não autenticados deve ser desfeita.

Os dados além da janela de pesquisa não são repetidos. Um visitante deve se autenticar em uma determinada janela de pesquisa para que uma visita não autenticada e uma visita autenticada sejam identificadas juntas. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

## Etapa 1: compilação em tempo real

A compilação em tempo real tenta compilar cada evento após a coleção em dispositivos e canais conhecidos. Considere o exemplo a seguir, em que Bob registra eventos diferentes como parte de um conjunto de dados de evento.

*Dados como aparecem no dia em que são coletados:*

| Evento  | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246, Bob, 3579, 81911 |

Os eventos não autenticados e autenticados em novos dispositivos são contados como pessoas separadas (temporariamente). Eventos não autenticados em dispositivos reconhecidos são compilados em tempo real.

A atribuição funciona quando a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todos os eventos, exceto o 1, 8, 9 e 10, são compilados em tempo real (todos eles usam o `Bob` identificador). A compilação em tempo real &quot;resolve&quot; a ID compilada para o evento 4, 6 e 12.

Os dados atrasados (dados com um carimbo de data e hora superior a 24 horas) são tratados com base no &quot;melhor esforço&quot;, priorizando a compilação de dados atuais para obter a mais alta qualidade.

## Etapa 2: Repetir a compilação

Em intervalos regulares (uma vez por semana ou uma vez por dia, dependendo da janela de pesquisa escolhida), a repetição da compilação recalcula os dados históricos com base nos dispositivos que agora ela reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, a repetição da compilação vinculará esses eventos não autenticados à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Evento  | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246, Bob, 3579, 81911 | **2 pessoas**:<br/>Bob, 3579 |

{style="table-layout:auto"}

A atribuição funciona quando a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, o evento 1 e 10 são compilados como resultado da repetição, deixando apenas o evento 8 e o 9 não compilados. E reduzindo a métrica de pessoas (cumulativa) para 2.

## Etapa 3: Solicitação de privacidade

Ao receber uma solicitação de privacidade, a linha que contém as informações originais do usuário é removida, juntamente com as IDs compiladas que contêm essas mesmas informações da pessoa. A tabela a seguir representa os mesmos dados acima, mas mostra o efeito que uma solicitação de privacidade para Bob tem nos dados após o processamento. As linhas em que Bob autenticado é removido (2, 3, 5, 7 e 11) juntamente com a remoção de Bob como uma ID transitória para outras linhas.

*Os mesmos dados após uma solicitação de privacidade para Bob:*

| Evento  | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória (ID de logon) | ID compilada (após compilação em tempo real) | ID compilada (após repetição) | ID transitória (ID de logon) | ID com título (após solicitação de privacidade) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 12:07 | 246 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 12:09 | 3579 ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Seta para a direita](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Seta para baixo](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Seta para cima](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 dispositivos** | | **4 pessoas**:<br/>246, Bob, 3579, 81911 | **2 pessoas**:<br/>Bob, 3579 |  | **3 pessoas**:<br/>246, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Resumo

* A compilação imediata compila os eventos de dispositivos conhecidos, mas não compila imediatamente os eventos de dispositivos novos ou não reconhecidos.
* Os dados são repetidos em intervalos regulares e alteram os dados históricos na conexão com base nos dispositivos que eles aprenderam a identificar.
* A compilação em tempo real e a repetição da compilação são executadas em um conjunto de dados. O resultado é um novo conjunto de dados elevado que é mais adequado para ser usado quando combinado com outros conjuntos de dados (por exemplo, dados da central de atendimento) para executar análise entre canais.
* As solicitações de privacidade removem identidades que foram propagadas para linhas não autenticadas.
