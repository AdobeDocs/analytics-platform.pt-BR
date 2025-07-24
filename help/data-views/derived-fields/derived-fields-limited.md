---
title: Campos derivados
description: Um campo derivado especifica a manipulação de tempo do relatório de campos do esquema e/ou componentes padrão por meio de um conjunto de funções e modelos de função disponíveis.
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 27%

---


# Campos derivados (teste limitado){#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>Esta é a documentação preliminar de novas funções de campo derivadas que ainda não estão geralmente disponíveis. Use essas informações para saber mais sobre as novas funções de campo derivadas. Esta documentação ainda está sujeita a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>><br/>Consulte [Campos derivados](derived-fields.md) para obter informações sobre a funcionalidade dos campos derivados em geral e sobre as funções e os modelos de função atualmente disponíveis.
>

## Referência da função

{{select-package}}

Para cada função compatível, confira os detalhes abaixo sobre:

- especificações:
   - tipo de dado de entrada: tipo de dado compatível,
   - entrada: valores possíveis para a entrada,
   - operadores inclusos: operadores compatíveis com esta função (se houver),
   - limitações: limitações aplicáveis a esta função específica,
   - saída.

- casos de uso, incluindo:
   - (opcional) dados antes de definir o campo derivado,
   - como definir o campo derivado,
   - (opcional) dados após definir o campo derivado.

- restrições (se aplicável).



<!-- DATE MATH -->

### Matemática de datas {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="Matemática de datas"
>abstract="Essa função fornece a capacidade de retornar a diferença entre dois campos de data ou data e hora."

Retorna a diferença entre dois campos de datas ou de data e hora.

+++ Detalhes

## Especificações {#datemath-io}

| Tipo de dado de entrada | Entrada | Operadores inclusos | Limitações | Saída |
|---|---|---|---|---|
| <ul><li>Data</li><li>Data-hora</li></ul> | <ul><li>[!UICONTROL Escopo]<ul><li>Evento</li><li>Sessão</li><li>Pessoa</li></ul></li><li>[!UICONTROL Valor]:<ul><li>Data</li><li>Data/hora</li><li>Data estática (entrada do usuário)</li><li>Data e hora estáticas (entrada do usuário)</li><li>Data dinâmica<ul><li>Hoje</li></ul></li><li>Data e hora dinâmicas<ul><li>Agora</li></ul></li></ul></li><li>[!UICONTROL Granularidade]:<ul><li>Seconds</li><li>Minutes</li><li>Horas</li><li>Days</li><li>Weeks</li><li>Months</li><li>Trimestres</li><li>Anos</li></ul></li><li>Para cada retorno de Data ou Data e hora:<ul><li>Primeiro (dentro da sessão ou pessoa)</li><li>Último (dentro da sessão ou pessoa)</li></ul></li></ul> | <p>N/A</p> | <p>Duas funções por campo derivado</p> | <p>Novo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#datemath-uc1}

Como analista de marketing de uma empresa de hotéis, você gostaria de entender a diferença do número de dias entre as datas de check-in dos clientes e as datas de reserva na última semana.


### Campo derivado {#datemath-uc1-derivedfield}

Você define um campo derivado de `Days between booking and check-in`. Use a função [!UICONTROL DATA MATH] para definir uma regra para calcular os dias do [!UICONTROL Escopo] [!DNL Person] entre a [!UICONTROL Data de Reserva] e a [!UICONTROL Data de Check-in]. Você seleciona [!UICONTROL Dia] como [!UICONTROL Granularidade da saída]. E você seleciona [!UICONTROL Retornar o último] para [!UICONTROL Data da reserva] e [!UICONTROL Data de check-in] para garantir que o valor de escopo da última pessoa seja usado no cálculo.

![Captura de tela da regra de Matemática de Datas](assets/datemath-1.png)


## Caso de uso 2 {#datemath-uc2}

Como analista de marketing de uma loja física, você quer entender quantos dias atrás foi a última visita de um cliente à loja. Você usa a funcionalidade de geolocalização em um aplicativo móvel e beacons na loja para capturar visitas físicas de clientes.

### Campo derivado {#datemath-uc2-derivedfield}

Você define um novo campo derivado de `Days Since Visit To Shop`. Use a função [!UICONTROL DATA MATH] para definir uma regra para calcular os dias entre uma Data-Hora Personalizada (que você especifica em [!UICONTROL Data]) e a [!UICONTROL Hora Local] (do grupo de campos [!UICONTROL placeContext] do conjunto de dados do evento) com um [!UICONTROL Escopo de desduplicação] de [!UICONTROL Pessoa]. Você seleciona [!UICONTROL Retornar o(s) último(s)] para garantir que o valor de escopo da última pessoa para [!UICONTROL Hora local] seja usado no cálculo. Você seleciona Dia como a [!UICONTROL Granularidade da saída].

![Captura de tela da regra de Matemática de Datas 2](assets/datemath-2.png)


## Caso de uso 3 {#datemath-uc3}

Você quer entender o tempo de pesquisa em minutos antes que um cliente em uma sessão faça um pedido.

Você define um novo campo derivado `Time Between Search And Order In Minutes` que é o resultado de duas funções [[!UICONTROL CASE WHEN]](#case-when) para definir valores de [!UICONTROL Tempo de Pesquisa] e [!UICONTROL Tempo de Pedido].
Em seguida, use esses dois valores para calcular a diferença com uma função [!UICONTROL DATE MATH] com [!UICONTROL Scope] definido como [!UICONTROL Session], valores definidos como [!UICONTROL Tempo de Pesquisa] e [!UICONTROL Tempo de Ordem] e [!UICONTROL Granularidade de saída] definidos como [!UICONTROL Minuto]. Para ambos os valores, selecione [!UICONTROL Retornar o primeiro] para garantir que o primeiro [!UICONTROL Tempo de Pesquisa] e o [!UICONTROL Tempo de Pedido] sejam retornados.

![Captura de tela da regra de Matemática de Datas 3](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Profundidade {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Profundidade"
>abstract="Essa função fornece a capacidade de retornar a profundidade de qualquer campo, sendo semelhante à funcionalidade do componente padrão de profundidade de evento."

Retorna a profundidade de um campo, semelhante ao que é possível com a [dimensão Profundidade do Evento padrão](/help/components/dimensions/overview.md#standard-dimensions) predefinida.

+++ Detalhes

## Especificações {#depth-io}

| Tipo de dado de entrada | Entrada | Operadores inclusos | Limitações | Saída |
|---|---|---|---|---|
| Qualquer | Qualquer campo | N/A | Três funções por campo derivado | Novo campo derivado |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## Caso de uso {#depth-uc1}

Você deseja compreender a profundidade da pesquisa (que também pode ser interpretada como o número de pesquisas). Portanto, você pode usar essa profundidade de pesquisa posteriormente para pesquisar o termo de pesquisa associado a uma profundidade de pesquisa específica.


### Campo derivado {#depth-uc1-derivedfield}

Você define um novo campo derivado de `Search Depth`. Use a função [!UICONTROL DEPTH] para definir uma regra para recuperar a profundidade da [!UICONTROL Pesquisa] e armazená-la em um novo campo derivado.

![Captura de tela da regra de Profundidade](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Conversão de tipo {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Conversão de tipo"
>abstract="Essa função permite alterar o tipo de campo a qualquer momento para disponibilizá-lo para transformações adicionais no Customer Journey Analytics."

Altere o tipo de campo de um campo para disponibilizá-lo para transformações adicionais no Customer Journey Analytics.

+++ Detalhes

## Especificações {#typecast-io}

| Tipo de dado de entrada | Entrada | Operadores inclusos | Limite | Saída |
|---|---|---|---|---|
| <ul><li>Numérico</li><li>Data</li><li>Data-hora</li><li>String</li></ul> | <ul><li>[!UICONTROL Campo] | <p><ul><li>Número inteiro<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong></li></ul></li><li>Dupla<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong><ul><li>Incluir o número de casas decimais a serem herdadas (máx. 5?)</li></ul></li><li>Para Inteiro <strong>(Should)</strong></li></ul></li><li>Byte<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong></li></ul></li><li>Longo<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong></li></ul></li><li>Data<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong><ul><li>Fornecer a capacidade de definir o formato de saída</li></ul></li><li>Exemplos<ul><li>Data (exemplo de 7 de janeiro de 2025)<ul><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-25-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01-2025-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07/01/25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 07/01/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01/2025/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD/MM/AA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. 01/25/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD de MMM de AAAA<ul><li data-stringify-indent="2" data-stringify-border="0">Ex. quarta-feira, 7 de janeiro de 2025</li></ul></li></ul></li></ul></li></ul></li><li>Data-hora<ul><li>Para a Cadeia de Caracteres <strong>(Must)</strong><ul><li>Fornecer a capacidade de definir o formato de saída</li></ul></li><li>Exemplos<ul><li data-stringify-indent="0" data-stringify-border="0">Data e hora (exemplo de 7 de janeiro de 2025 em 1:30pm, 52 segundos)<ul><li data-stringify-indent="2" data-stringify-border="0">DD-MM-AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">hhmmss de MM-DD-YYYY<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">hhmmss DD-MM-AA<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-AA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-25-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/AA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07/01/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07/01/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD/MM/AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01/2025/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">AA/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 01/25/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD de MMM de AAAA hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">Ex. 07 de janeiro de 2025 13:30:52</li></ul></li></ul></li></ul></li><li>String<ul><li>Para numérico <strong>(Should)</strong><ul><li>Se tivermos valores que não são de natureza numérica, eles retornarão null.</li><li>Precisaremos que o usuário insira a precisão e a localidade a serem usadas. </li></ul></li></ul></li></ul></li></ul></p> | <p>Três funções por campo derivado</p> | <p>Novo campo derivado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#typecast-uc1}

Você tem um campo inteiro, altura da tela (por exemplo, device.screenHeight do conjunto de dados do evento), que gostaria de usar como uma dimensão baseada em sequência.


### Campo derivado {#typecast-uc1-derivedfield}

Você define um campo derivado `Screen Height`. Você usa a função [!UICONTROL TYPECAST] para definir uma regra para [!UICONTROL Typecast para] [!UICONTROL Cadeia de caracteres] o campo [!UICONTROL Altura da tela] e armazená-lo no novo campo derivado.

![Captura de tela da regra Typecast 1](assets/typecast-1.png)



## Caso de uso 2 {#typecast-uc2}

Você deseja usar Receita em uma tabela de Coorte (que só suporta números inteiros), mas o campo Receita tem um tipo Duplo.

![Captura de tela da regra Typecast 2](assets/typecast-2.png)


### Campo derivado {#typecast-uc2-derivedfield}

Você define um campo derivado `Revenue (integer)`. Você usa a função [!UICONTROL TYPECAST] para definir uma regra para [!UICONTROL Typecast para] [!UICONTROL Integer] o campo [!UICONTROL Revenue] e armazená-lo no novo campo derivado.


+++
