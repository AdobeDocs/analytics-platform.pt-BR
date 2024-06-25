---
title: Conjuntos de dados de evento combinados
description: Saiba como o Customer Journey Analytics cria uma conexão combinando conjuntos de dados.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 80d5a864e063911b46ff248f2ea89c1ed0d14e32
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 61%

---


# Conjuntos de dados de evento combinados

Ao criar uma conexão, o Customer Journey Analytics combina todos os esquemas e conjuntos de dados em um único conjunto de dados. Esse &quot;conjunto de dados combinados&quot; é o que o Customer Journey Analytics usa para os relatórios. Ao incluir vários esquemas ou conjuntos de dados em uma conexão:

* Os esquemas são combinados. Os campos de esquema duplicados são unidos.
* A coluna &quot;ID de pessoa&quot; de cada conjunto de dados é unida em uma única coluna, independentemente do nome. Essa coluna é a base para identificar pessoas únicas no Customer Journey Analytics.
* As linhas são processadas com base no carimbo de data e hora.
* Os eventos são resolvidos até o nível de milissegundo.

## Exemplo

Considere o exemplo a seguir. Você tem dois conjuntos de dados de eventos, cada um com campos diferentes contendo dados diferentes.

>[!NOTE]
>
>A Adobe Experience Platform normalmente armazena o carimbo de data e hora em milissegundos do Unix. Neste exemplo, são usadas data e hora.

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

Ao criar uma conexão usando esses dois conjuntos de dados de eventos, a tabela a seguir é usada para os relatórios.

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

Esse conjunto de dados combinados de eventos é o que é usado nos relatórios. Não importa de que conjunto de dados uma linha é derivada; o Customer Journey Analytics trata todos os dados como se estivessem no mesmo conjunto de dados. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados, eles serão considerados a mesma pessoa única. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados com um carimbo de data e hora em 30 minutos, ela será considerada parte da mesma sessão.

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

## Análise entre canais

O próximo nível de combinação de conjuntos de dados é a análise entre canais, em que os conjuntos de dados de diferentes canais são combinados, com base em um identificador comum (ID de pessoa). A análise entre canais pode se beneficiar da funcionalidade de compilação, permitindo rechavear a ID de pessoa de um conjunto de dados para que o conjunto de dados seja atualizado corretamente e possibilite uma combinação perfeita de vários conjuntos de dados. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada.

A análise entre canais permite responder perguntas como:

* Quantas pessoas começam sua experiência em um canal e depois terminam em outro?
* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu considerar jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?


Para obter mais informações sobre a análise entre canais, consulte o caso de uso específico:

* [Análise entre canais](../use-cases/cross-channel/cross-channel.md)

Para obter uma funcionalidade de compilação de discussão mais detalhada, acesse:

* [Visão geral da compilação](/help/stitching/overview.md)
* [Perguntas frequentes](/help/stitching/faq.md)

