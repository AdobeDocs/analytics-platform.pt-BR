---
title: Conjuntos de dados combinados
description: Saiba como o CJA cria uma conexão combinando conjuntos de dados.
translation-type: tm+mt
source-git-commit: fa354af31237c4963ba0affa89652bfdeae45ea0
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 6%

---


# Conjuntos de dados combinados

Quando você cria uma conexão, o CJA combina todos os schemas e conjuntos de dados em um único conjunto de dados. Esse &quot;conjunto de dados combinado&quot; é o que o CJA usa para o relatórios. Ao incluir vários schemas ou conjuntos de dados em uma conexão:

* Schemas são combinados. Os campos de schema do Duplicado são unidos.
* A coluna &quot;ID da pessoa&quot; de cada conjunto de dados é unida em uma única coluna, independentemente do nome. Essa coluna é a base para identificar visitantes únicos no CJA.
* As linhas são processadas com base no carimbo de data e hora.

## Exemplo

Considere o exemplo a seguir. Você tem dois conjuntos de dados, cada um com campos diferentes contendo dados diferentes.

>[!NOTE] A Adobe Experience Platform normalmente armazena o carimbo de data e hora em milissegundos do Unix. Para leitura neste exemplo, data e hora são usadas.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

Quando você cria uma conexão usando esses dois conjuntos de dados, a tabela a seguir é usada para o relatórios.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Esse conjunto de dados combinado é o que é usado no relatórios. Não importa de que conjunto de dados uma linha provém; O CJA trata todos os dados como se estivessem no mesmo conjunto de dados. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados, eles serão considerados o mesmo visitante exclusivo. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados com um carimbo de data e hora em 30 minutos, ela será considerada parte da mesma sessão.

Este conceito também se aplica à atribuição. Não importa de que conjunto de dados uma linha provém; a atribuição funciona exatamente como se todos os eventos viessem de um único conjunto de dados. Usando as tabelas acima como exemplo:

Se sua conexão incluísse apenas a primeira tabela e não a segunda, puxar um relatório usando a `string_color` `metric_a` dimensão e a métrica usando a atribuição de último toque mostraria:

| string_color | metric_a |
| --- | --- |
| Não especificado | 6 |
| Azul  | 3 |
| Vermelho  | 2 |

No entanto, se você incluiu ambas as tabelas em sua conexão, a atribuição será alterada, pois `user_847` está em ambos os conjuntos de dados. Uma linha dos atributos do segundo conjunto de dados `metric_a` para &#39;Amarelo&#39;, onde não foram especificados anteriormente:

| string_color | metric_a |
| --- | --- |
| Amarelo | 6 |
| Azul  | 3 |
| Vermelho  | 2 |
