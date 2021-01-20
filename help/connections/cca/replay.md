---
title: Como funcionam as repetições
description: Entenda o conceito de "repetição" no Cross-Canal Analytics
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 16%

---


# Como funcionam as repetições

O Cross-Canal Analytics envia dois dados em uma determinada conexão:

* **Arranque ao vivo**: O CCA tenta costurar cada ocorrência à medida que entra. Geralmente, os novos dispositivos da rede para o conjunto de dados que nunca fizeram logon não são agrupados nesse nível. Os dispositivos já reconhecidos são imediatamente compilados.
* **Reproduzir**: Dados de &quot;reproduz&quot; de CCA com base em identificadores únicos que ele aprendeu. Nesse estágio, novos dispositivos para a conexão se tornam costurados. Adobe oferta dois intervalos de repetição:
   * Diariamente: Os dados são reproduzidos todos os dias com uma janela de retrospectiva de 24 horas. Essa opção tem uma vantagem de que as respostas são muito mais frequentes, mas visitantes não autenticados devem ser autenticados no mesmo dia em que visitam site.
   * Semanalmente: Os dados são reproduzidos uma vez por semana com uma janela de retrospectiva de 7 dias. Essa opção tem uma vantagem que permite que sessões não autenticadas tenham um tempo muito mais leve para autenticação. No entanto, dados com menos de uma semana não são costurados.

## Etapa 1: costura ao vivo

O CCA tenta costurar cada evento durante a coleta para dispositivos e canais conhecidos. Considere o exemplo a seguir, onde Bob usa dois canais diferentes.

*Dados como aparecem no dia em que são coletados:*

| Carimbo de data e hora | ID persistente do conjunto de dados da Web | ID Transitório do Conjunto de Dados da Web | ID da pessoa do centro de atendimento | ID da pessoa usada | Explicação da ocorrência | Métrica de pessoas (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visita seu site em seu desktop, não autenticado | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob faz logon no desktop | `2` (246 e Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob faz uma chamada para o atendimento ao cliente | `2` (246 e Bob) |
| `4` | `3579` | - | - | `3579` | Bob acessa seu site em seu dispositivo móvel, não autenticado | `3` (246, Bob e 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob faz logon via celular | `3` (246, Bob e 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob faz outra chamada para o atendimento ao cliente | `3` (246, Bob e 3579) |
| `7` | `246` | - | - | `Bob` | Bob visita seu site em sua área de trabalho novamente, não autenticado | `3` (246, Bob e 3579) |

Eventos não autenticados e autenticados em novos dispositivos são contados como pessoas separadas (temporariamente). Eventos não autenticados em dispositivos reconhecidos são marcados ao vivo.

A atribuição funciona assim que a variável personalizada de identificação se vincula a um dispositivo. No exemplo acima, todos os eventos, com exceção dos eventos 1 e 4, são marcados ao vivo (todos usam o identificador `Bob`). A atribuição funciona nos eventos 1 e 4 após reproduzir a costura.

## Etapa 2: Reproduzir pontilhamento

Em intervalos regulares (uma vez por semana ou uma vez por dia, dependendo da janela de pesquisa escolhida), o CCA recalcula os dados históricos com base nos dispositivos que agora reconhece. Se um dispositivo enviar dados inicialmente sem autenticação e fizer logon, o CCA vinculará esses eventos não autenticados à pessoa correta. A tabela a seguir representa os mesmos dados acima, mas mostra números diferentes com base na repetição dos dados.

*Os mesmos dados após a repetição:*

| Carimbo de data e hora | ID persistente do conjunto de dados da Web | ID Transitório do Conjunto de Dados da Web | ID da pessoa do centro de atendimento | ID da pessoa usada | Explicação da ocorrência | Métrica de pessoas (cumulativa) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visita seu site em seu desktop, não autenticado | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob faz logon no desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob faz uma chamada para o atendimento ao cliente | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob acessa seu site em seu dispositivo móvel, não autenticado | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob faz logon via celular | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob faz outra chamada para o atendimento ao cliente | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visita seu site em sua área de trabalho novamente, não autenticado | `1` (Bob) |

## Recapitulação

* O CCA costuma colocar imediatamente dispositivos conhecidos, mas não costurar imediatamente dispositivos novos ou não reconhecidos.
* Os dados são reproduzidos em intervalos regulares e alteram os dados históricos na conexão com base nos dispositivos que eles aprenderam a identificar.
