---
title: Conjuntos de dados de evento combinados
description: Saiba como Customer Journey Analytics cria uma conexão combinando conjuntos de dados.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 3389c141105ff71ed26abe4384fe3bb930448d43
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 35%

---


# Conjuntos de dados de evento combinados

Ao criar uma conexão, o Customer Journey Analytics combina todos os conjuntos de dados de eventos em um único conjunto de dados. Essa evento conjunto de dados combinada é o que Customer Journey Analytics usa para relatórios (junto com conjuntos de dados de perfil e pesquisa). Ao incluir vários conjuntos de dados de eventos em uma conexão:

* Os dados dos campos em conjuntos de dados com base na **mesma schema caminho** são unidos em uma única coluna na conjunto de dados combinada.
* A coluna ID da pessoa, especificada para cada conjunto de dados, é mesclada em uma única coluna na conjunto de dados combinada, **independentemente do nome**. Essa coluna é a base da identificação de pessoas únicas no Customer Journey Analytics.
* As linhas são processadas com base no carimbo de data e hora.
* Os eventos são resolvidos até o nível de milissegundo.

## Exemplo

Considere o exemplo a seguir. Você tem dois conjuntos de dados de eventos, cada um com campos diferentes contendo dados diferentes.

>[!NOTE]
>
>Adobe Experience Platform normalmente armazena um carimbo de data e hora em milissegundos UNIX®. Para leitura neste exemplo, data e hora são usadas.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

Ao criar uma conexão usando esses dois conjuntos de dados evento, e identificar

* `example_id` como a ID de pessoa para o primeiro conjunto de dados e
* `different_id` como A ID da pessoa para o segundo conjunto de dados,

a conjunto de dados combinada a seguir é usada para relatórios.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Para ilustrar a importância dos schema caminhos, considere este cenário. No primeiro conjunto de dados, `string_color` baseia-se schema caminho `_experience.whatever.string_color` e na segunda conjunto de dados em schema caminho  `_experience.somethingelse.string_color`. Nesse cenário, os dados não **são** unidos em uma coluna no conjunto de conjunto de dados resultante. Em vez disso, o resultado é duas `string_color` colunas na conjunto de dados combinada.

Esse conjunto de dados combinados de eventos é o que é usado nos relatórios. Não importa de qual conjunto de dados linha. Customer Journey Analytics trata todos os dados como se estivesse na mesma conjunto de dados. Se uma ID de pessoa correspondente aparecer em ambos os conjuntos de dados, elas serão consideradas as mesmas único usuário. Se uma ID de pessoa correspondente aparecer em ambos os conjuntos de dados com um carimbo de data e hora em 30 minutos, elas serão consideradas parte da mesma sessão. Campos com caminhos de schema idênticos são unidos.

Este conceito também se aplica à atribuição. Não importa de que conjunto de dados uma linha é derivada; a atribuição funciona exatamente como se todos os eventos viessem de um único conjunto de dados. Usando as tabelas acima como exemplo:

Se sua conexão incluísse apenas a primeira tabela e não a segunda, puxar um relatório usando a dimensão `string_color` e a métrica `metric_a` usando a atribuição de último toque mostraria:

| string_color | metric_a |
| --- | --- |
| Não especificado | 6 |
| Azul | 3 |
| Vermelho | 2 |

No entanto, se você incluiu ambas as tabelas em sua conexão, a atribuição será alterada, pois `user_847` está em ambos os conjuntos de dados. Uma linha do segundo conjunto de dados atribui `metric_a` como &#39;Amarelo&#39; onde eles não foram especificados anteriormente:

| string_color | metric_a |
| --- | --- |
| Amarelo | 6 |
| Azul | 3 |
| Vermelho | 2 |

>[!NOTE]
>
>Se um campo mesclado for uma chave de pesquisa para um conjunto de dados de evento na conexão, o conjunto de dados de pesquisa associado será enriquecido *all* valores desse campo. Não importa de que conjunto de dados de evento uma linha é derivada, pois a relação de pesquisa está associada ao caminho de esquema compartilhado.

## Análise entre canais

O próximo nível de combinação de conjuntos de dados é a análise entre canais, em que os conjuntos de dados de diferentes canais são combinados, com base em um identificador comum (ID de pessoa). A análise entre canais pode se beneficiar da funcionalidade de compilação, permitindo rechavear a ID de pessoa de um conjunto de dados para que o conjunto de dados seja atualizado corretamente e permita uma combinação contínua de vários conjuntos de dados. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada.

A canal análise permite que você responda a perguntas como:

* Quantas pessoas começam sua experiência em um canal e depois terminam em outro?
* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* Como minha compreensão de campanha eficácia muda se eu considerar jornadas entre dispositivo? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?


Para obter mais informações sobre análise entre canais, consulte o caso de uso específico:

* [Entre canal análise](../use-cases/cross-channel/cross-channel.md)

Para uma discussão mais aprofundada sobre a costura de funcionalidade, acesse:

* [Visão geral da costura](/help/stitching/overview.md)
* [Perguntas frequentes](/help/stitching/faq.md)

