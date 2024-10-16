---
title: Conjuntos de dados de evento combinados
description: Saiba como o Customer Journey Analytics cria uma conexão combinando conjuntos de dados.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 8241bcc4a2653da456c1577eb95d5504ca118cd9
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 33%

---


# Conjuntos de dados de evento combinados

Ao criar uma conexão, o Customer Journey Analytics combina todos os conjuntos de dados de eventos em um único conjunto de dados. Esse conjunto de dados combinados de eventos é o que o Customer Journey Analytics usa para os relatórios (juntamente com conjuntos de dados de perfil e pesquisa). Ao incluir vários conjuntos de dados de eventos em uma conexão:

* Os dados de campos em conjuntos de dados baseados no **mesmo caminho de esquema** são mesclados em uma única coluna no conjunto de dados combinado.
* A coluna de ID de pessoa, especificada para cada conjunto de dados, é mesclada em uma única coluna no conjunto de dados combinado, **independentemente do nome**. Essa coluna é a base para identificar pessoas únicas no Customer Journey Analytics.
* As linhas são processadas com base no carimbo de data e hora.
* Os eventos são resolvidos até o nível de milissegundo.

## Exemplo

Considere o exemplo a seguir. Você tem dois conjuntos de dados de eventos, cada um com campos diferentes contendo dados diferentes.

>[!NOTE]
>
>A Adobe Experience Platform geralmente armazena um carimbo de data e hora em milissegundos do UNIX®. Neste exemplo, são usadas data e hora.

| example_id | carimbo de data e hora | string_color | string_animal | metric_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1 jan 7:02 AM | Vermelho | Fox | |
| user_310 | 1 jan 7:04 AM | | | 2 |
| user_310 | 1 Jan 7:08 AM | Azul | | 3 |
| user_847 | 12 de janeiro:31 | | Tartaruga | 4 |
| user_847 | 12 de janeiro:44 h | | | 2 |

| different_id | carimbo de data e hora | string_color | string_shape | metric_b |
| --- | --- | --- | --- | ---: |
| user_847 | 12 de janeiro:26 | Amarelo | Círculo | 8,5 |
| user_847 | 14 jan 1:01 PM | Vermelho | | |
| alternateid_656 | 2 Jan 8:58 PM | Vermelho | Quadrado | 4.2 |
| alternateid_656 | 14 de janeiro de 21:03 | | Triângulo | 3,1 |

Ao criar uma conexão usando esses dois conjuntos de dados de eventos e tiver identificado

* `example_id` como a ID de pessoa para o primeiro conjunto de dados e
* `different_id` como a ID de pessoa para o segundo conjunto de dados,

o conjunto de dados combinado a seguir é usado para os relatórios.

| id | carimbo de data e hora | string_color | string_animal | string_shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1 jan 7:02 AM | Vermelho | Fox | | | |
| user_310 | 1 jan 7:04 AM | | | | 2 | |
| user_310 | 1 Jan 7:08 AM | Azul | | | 3 | |
| user_847 | 12 de janeiro:26 | Amarelo | | Círculo | | 8,5 |
| user_847 | 12 de janeiro:31 | | Tartaruga | | 4 | |
| user_847 | 12 de janeiro:44 h | | | | 2 | |
| user_847 | 14 jan 1:01 PM | Vermelho | | | | |
| alternateid_656 | 2 Jan 8:58 PM | Vermelho | | Quadrado | | 4.2 |
| alternateid_656 | 14 de janeiro de 21:03 | | | Triângulo | | 3,1 |

Para ilustrar a importância dos caminhos de esquema, considere este cenário. No primeiro conjunto de dados, `string_color` é baseado no caminho de esquema `_experience.whatever.string_color` e no segundo conjunto de dados no caminho de esquema `_experience.somethingelse.string_color`. Neste cenário, os dados são **não** mesclados em uma coluna no conjunto de dados combinado resultante. Em vez disso, o resultado é duas colunas `string_color` no conjunto de dados combinado:

| id | carimbo de data e hora | _experiência.<br/>seja o que for.<br/>cor_da_string | _experiência.<br/>algo mais.<br/>cor_da_string | string_animal | string_shape | metric_a | metric_b |
| --- | --- | --- | --- | --- | --- | ---: | ---:|
| user_310 | 1 jan 7:02 AM | Vermelho | | Fox | | | |
| user_310 | 1 jan 7:04 AM | | | | | 2 | |
| user_310 | 1 Jan 7:08 AM | Azul | | | | 3 | |
| user_847 | 12 de janeiro:26 | | Amarelo | | Círculo | | 8,5 |
| user_847 | 12 de janeiro:31 | | | Tartaruga |  | 4 | |
| user_847 | 12 de janeiro:44 h | | | | | 2 | |
| user_847 | 14 jan 1:01 PM | | Vermelho | | | | |
| alternateid_656 | 2 Jan 8:58 PM | | Vermelho | | Quadrado | | 4.2 |
| alternateid_656 | 14 de janeiro de 21:03 | | | | Triângulo | | 3,1 |

Esse conjunto de dados combinados de eventos é o que é usado nos relatórios. Não importa de que conjunto de dados uma linha é derivada. O Customer Journey Analytics trata todos os dados como se estivessem no mesmo conjunto de dados. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados, eles serão considerados a mesma pessoa única. Se uma ID de pessoa correspondente for exibida em ambos os conjuntos de dados com um carimbo de data e hora em 30 minutos, ela será considerada parte da mesma sessão. Os campos com caminhos de esquema idênticos são mesclados.

Este conceito também se aplica à atribuição. Não importa de que conjunto de dados uma linha é derivada; a atribuição funciona exatamente como se todos os eventos viessem de um único conjunto de dados. Usando as tabelas acima como exemplo:

Se sua conexão incluísse apenas a primeira tabela e não a segunda, puxar um relatório usando a dimensão `string_color` e a métrica `metric_a` usando a atribuição de último toque mostraria:

| string_color | metric_a |
| --- | ---: |
| Não especificado | 6 |
| Azul | 3 |
| Vermelho | 2 |

No entanto, se você incluiu ambas as tabelas em sua conexão, a atribuição será alterada, pois `user_847` está em ambos os conjuntos de dados. Uma linha do segundo conjunto de dados atribui `metric_a` como &#39;Amarelo&#39; onde eles não foram especificados anteriormente:

| string_color | metric_a |
| --- | ---: |
| Amarelo | 6 |
| Azul | 3 |
| Vermelho | 2 |

>[!NOTE]
>
>Se um campo mesclado for uma chave de pesquisa para um conjunto de dados de evento na conexão, o conjunto de dados de pesquisa associado enriquecerá **todos** valores desse campo. Não importa de que conjunto de dados de evento uma linha é derivada, pois a relação de pesquisa está associada ao caminho de esquema compartilhado.

## Análise entre canais

O próximo nível de combinação de conjuntos de dados é a análise entre canais, em que os conjuntos de dados de diferentes canais são combinados, com base em um identificador comum (ID de pessoa). A análise entre canais pode se beneficiar da funcionalidade de compilação, permitindo rechavear a ID de pessoa de um conjunto de dados para que o conjunto de dados seja atualizado corretamente e permita uma combinação contínua de vários conjuntos de dados. A compilação analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada.

A análise entre canais permite responder perguntas como:

* Quantas pessoas começam sua experiência em um canal e depois terminam em outro?
* Quantas pessoas interagem com a minha marca? Quantos e quais tipos de dispositivos eles usam? Como eles se sobrepõem?
* Com que frequência as pessoas iniciam uma tarefa em um dispositivo móvel e depois movem para um PC de desktop para concluí-la? Os click-throughs da campanha direcionados a um dispositivo levam para a conversão em outro lugar?
* O quanto muda minha compreensão da eficácia da campanha se eu considerar jornadas entre dispositivos? Como a minha análise de funil muda?
* Quais são os caminhos mais comuns que os usuários fazem de um dispositivo para outro? Onde eles desistem? Onde eles têm sucesso?
* Como o comportamento de usuários com vários dispositivos difere dos usuários com um único dispositivo?


Para obter mais informações sobre a análise entre canais, consulte o caso de uso específico:

* [Análise entre canais](../use-cases/cross-channel/cross-channel.md)

Para uma discussão mais detalhada da funcionalidade de compilação, acesse:

* [Visão geral da compilação](/help/stitching/overview.md)
* [Perguntas frequentes](/help/stitching/faq.md)

