---
title: Como funcionam as repetições
description: Entenda o conceito de “repetição” na Cross-Channel Analytics
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
solution: Customer Journey Analytics
hide: true
hidefromtoc: true
source-git-commit: 4c6e968272b554188243b772bd159fe8174b3c3b
workflow-type: ht
source-wordcount: '578'
ht-degree: 100%

---


# Como funcionam as repetições

A Cross-Channel Analytics faz duas passagens de dados em uma determinada conexão:

* **Compilação em tempo real**: o CCA tenta compilar cada evento assim que eles chegam. Os novos dispositivos de rede para o conjunto de dados que nunca se conectaram normalmente não são compilados neste nível. Os dispositivos já reconhecidos são imediatamente compilados.
* **Repetição**: a CCA “repete” dados com base em identificadores exclusivos que ele aprendeu. É nesse estágio que os novos dispositivos da conexão são compilados. A Adobe oferece dois intervalos de repetição:
   * Diariamente: os dados são repetidos todos os dias com uma janela de retrospectiva de 24 horas. Essa opção tem a vantagem das repetições serem muito mais frequentes, mas as pessoas não autenticadas devem se autenticar no mesmo dia em que visitam o site.
   * Semanalmente: os dados são repetidos uma vez por semana com uma janela de retrospectiva de sete dias. Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais tolerante para autenticação. No entanto, dados com menos de uma semana não são compilados.

Os dados além da janela de pesquisa não são repetidos. Uma pessoa deve se autenticar em uma determinada janela de retrospectiva para que uma visita não autenticada e uma visita autenticada sejam identificadas em conjunto. Depois que um dispositivo é reconhecido, ele é compilado em tempo real a partir desse ponto.

## Etapa 1: compilação em tempo real

A CCA tenta compilar cada evento após a coleção em dispositivos e canais conhecidos. Considere o exemplo a seguir, em que Bob usa dois canais diferentes.

*Dados como aparecem no dia em que são coletados:*

| Carimbo de data e hora | ID persistente do conjunto de dados da Web | ID transitória do conjunto de dados da Web | ID da pessoa da central de atendimento | ID de pessoa usada | Explicação do evento | Métrica de pessoas (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita seu site no desktop dele, não autenticado | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob faz logon no desktop | `2` (246 e Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob liga para o serviço do cliente | `2` (246 e Bob) |
| `4` | `3579` | - | - | `3579` | Bob acessa seu site no dispositivo móvel dele, não autenticado | `3` (246, Bob e 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob faz logon via celular | `3` (246, Bob e 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob liga para o serviço do cliente novamente | `3` (246, Bob e 3579) |
| `7` | `246` | - | - | `Bob` | Bob acessa seu site novamente no desktop dele, não autenticado | `3` (246, Bob e 3579) |

Os eventos não autenticados e autenticados em novos dispositivos são contados como pessoas separadas (temporariamente). Eventos não autenticados em dispositivos reconhecidos são compilados em tempo real.

A atribuição funciona assim que a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todos os eventos, exceto o 1 e o 4, são compilados em tempo real (todos eles usam o identificador `Bob`). A atribuição funciona nos eventos 1 e 4 após a repetição da compilação.

## Etapa 2: Repetir a compilação

Em intervalos regulares (uma vez por semana ou uma vez por dia, dependendo da janela de pesquisa escolhida), a CCA recalcula os dados históricos com base nos dispositivos que agora ele reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, a CCA vinculará esses eventos não autenticados à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Carimbo de data e hora | ID persistente do conjunto de dados da Web | ID transitória do conjunto de dados da Web | ID da pessoa da central de atendimento | ID de pessoa usada | Explicação do evento | Métrica de pessoas (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita seu site no desktop dele, não autenticado | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob faz logon no desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob liga para o serviço do cliente | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob acessa seu site no dispositivo móvel dele, não autenticado | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob faz logon via celular | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob liga para o serviço do cliente novamente | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob acessa seu site novamente no desktop dele, não autenticado | `1` (Bob) |

>[!NOTE]
>
>Os dados são repetidos somente para o conjunto de dados do site. O conjunto de dados da central de atendimento permanece inalterado, mas é compatível quando a ID de pessoa correta é usada.

## Recapitulação

* A CCA costuma compilar imediatamente dispositivos conhecidos, mas não compila imediatamente dispositivos novos ou não reconhecidos.
* Os dados são repetidos em intervalos regulares e alteram os dados históricos na conexão com base nos dispositivos que eles aprenderam a identificar.
