---
title: Usar campos derivados em feeds de dados
description: Saiba como usar campos derivados em feeds de dados.
hide: true
feature: Components
source-git-commit: a9f53472d57a3a26004bd5ca583a43134bbdba7e
workflow-type: tm+mt
source-wordcount: '1286'
ht-degree: 2%

---

# Usar campos derivados em feeds de dados

{{release-limited-testing}}

Você pode executar transformações nos dados do feed de dados usando [campos derivados](/help/data-views/derived-fields/derived-fields.md).

Muitas funções de campo derivadas executam transformações que também podem ser aplicadas usando SQL, como a substituição de valores, a combinação de campos ou a conversão do tipo de dados de um campo. Portanto, o método escolhido às vezes é uma questão de preferência.

## Campos derivados vs. SQL

A tabela a seguir compara as vantagens e desvantagens do uso de campos derivados ou SQL.

| Método | Vantagens | Desvantagens |
| --- | --- | --- |
| **Campos derivados** | <ul><li>A mesma lógica se aplica de forma consistente na Analysis Workspace e na saída do feed de dados, pois os campos derivados são incluídos como componentes no esquema do feed de dados, junto com dimensões e métricas padrão.</li><li>Algumas transformações, particularmente aquelas que dependem de uma configuração de Escopo ou que analisam um URL, são difíceis de replicar no SQL.</li></ul> | Adiciona sobrecarga de processamento, o que pode afetar o desempenho de entrega do feed de dados.<!--Under a future usage-based pricing model, this could also add cost.--> |
| **SQL** | <ul><li>Não limitado pelos limites de função e operador que se aplicam aos campos derivados.</li><li>Não afeta o desempenho de entrega do feed de dados.</li></ul> | <ul><li>A lógica não se aplica ao Analysis Workspace, portanto, seria necessário duplicá-la separadamente.</li><li>Algumas transformações, particularmente aquelas que dependem de uma configuração de Escopo ou que analisam um URL, são difíceis ou impraticáveis de replicar.</li></ul> |

{style="table-layout:auto"}

## Funções de campo derivadas

A tabela a seguir descreve cada função de campo derivado, se ela é mais adequada para um campo derivado ou para SQL, e quaisquer considerações que devem ser levadas em conta antes de usá-la.

| Função de campo derivado | Dificuldade em replicar usando SQL | Melhor ajuste (campo derivado ou SQL) | Considerações |
| --- | --- | --- | --- |
| [**Case When**](/help/data-views/derived-fields/derived-fields.md#casewhen)<br/> Aplica condicionais com base em critérios de um ou mais campos e define o valor de saída com base na condição correspondente. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. Isso é especialmente útil quando um grande número de regras está envolvido, como uma classificação de canal de marketing. |
| [**Classificar**](/help/data-views/derived-fields/derived-fields.md#classify)<br/> Define um conjunto de valores que são substituídos por valores correspondentes em um novo campo derivado. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Concatenar**](/help/data-views/derived-fields/derived-fields.md#concatenate)<br/> Combina valores de campo em um único campo derivado novo usando delimitadores definidos (por exemplo, nome de página e canal de marketing). | Fácil de moderar | Ou | Espelha a funcionalidade de adicionar várias colunas de dimensão a uma tabela de forma livre, que é limitada à Exportação de tabela completa. Um campo derivado disponibiliza saídas semelhantes em um feed de dados. |
| [**Correspondência de Data**](/help/data-views/derived-fields/derived-fields.md#datemath)<br/> Retorna a diferença entre dois campos de data ou data e hora (por exemplo, dias entre uma data de reserva e uma data de check-in), com um Escopo de Evento, Sessão ou Pessoa. | Difícil | Campo derivado | Complexo para replicar no SQL. Esta função depende de uma configuração Escopo. Para obter mais informações, consulte [Como as configurações de Escopo em funções afetam os feeds de dados](#scope-settings). |
| [**Desduplicar**](/help/data-views/derived-fields/derived-fields.md#dedup)<br/> Impede a contagem de um valor várias vezes, com um Escopo de Pessoa ou Sessão (por exemplo, desduplicar uma ID de confirmação de reserva). | Difícil | Campo derivado | Esta função depende de uma configuração Escopo. Para obter mais informações, consulte [Como as configurações de Escopo em funções afetam os feeds de dados](#scope-settings). |
| [**Profundidade**](/help/data-views/derived-fields/derived-fields.md#depth)<br/> Retorna a profundidade de um campo, semelhante à dimensão Profundidade do Evento padrão (por exemplo, profundidade de pesquisa interna). | Difícil | Campo derivado | Usa sessão como escopo e não é configurável. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> A forma como o contador se comporta quando uma sessão passa por um limite de entrega de feed ainda está sendo confirmada com a engenharia. Esta função depende de uma configuração Escopo. Para obter mais informações, consulte [Como as configurações de Escopo em funções afetam os feeds de dados](#scope-settings). |
| [**Localizar e Substituir**](/help/data-views/derived-fields/derived-fields.md#find-and-replace)<br/> Localiza todos os valores em um campo selecionado e os substitui por um valor diferente. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Pesquisa**](/help/data-views/derived-fields/derived-fields.md#lookup)<br/> Pesquisa um valor de um conjunto de dados de pesquisa usando uma chave correspondente e o retorna em um novo campo derivado. | Fácil de moderar | Ou | O SQL funciona se uma tabela de pesquisa já existir. |
| [**Minúsculas**](/help/data-views/derived-fields/derived-fields.md#lowercase)<br/> Converte valores de um campo em minúsculas. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Matemática**](/help/data-views/derived-fields/derived-fields.md#math)<br/> Aplica operadores matemáticos básicos (adicionar, subtrair, multiplicar, dividir ou elevar a uma potência) a campos numéricos, avaliados ocorrência por ocorrência. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Mesclar Campos**](/help/data-views/derived-fields/derived-fields.md#merge)<br/> Verifica se o primeiro de dois ou mais campos tem um valor; caso contrário, usa o próximo campo e assim por diante. | Fácil de moderar | Ou | Nenhum |
| [**Próximo ou Anterior**](/help/data-views/derived-fields/derived-fields.md#next-previous)<br/> Resolve o valor seguinte ou anterior de um campo de tabela Visita ou Evento, com um Escopo de Pessoa ou Sessão. | Difícil | Campo derivado | Esta função depende de uma configuração Escopo. Para obter mais informações, consulte [Como as configurações de Escopo em funções afetam os feeds de dados](#scope-settings). |
| [**Substituição de Regex**](/help/data-views/derived-fields/derived-fields.md#regex-replace)<br/> Substitui um valor de um campo usando uma expressão regular. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Dividir**](/help/data-views/derived-fields/derived-fields.md#split)<br/> Divide um valor de um campo em um novo campo derivado (por exemplo, convertendo uma lista delimitada em uma matriz). | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Resumir**](/help/data-views/derived-fields/derived-fields.md#summarize)<br/> Aplica funções de agregação (como soma, contagem ou mais comuns) a um campo, com um Escopo de Evento, Sessão ou Pessoa. | Difícil | Campo derivado | Esta função depende de uma configuração Escopo. Para obter mais informações, consulte [Como as configurações de Escopo em funções afetam os feeds de dados](#scope-settings). |
| [**Cortar**](/help/data-views/derived-fields/derived-fields.md#trim)<br/> Corta espaços em branco, caracteres especiais ou um número definido de caracteres do início ou do fim dos valores de um campo. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Typecast**](/help/data-views/derived-fields/derived-fields.md#typecast)<br/> Altera o tipo de dados de um campo para disponibilizá-lo para transformações adicionais. | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| [**Análise de URL**](/help/data-views/derived-fields/derived-fields.md#urlparse)<br/> Analisa partes de uma URL, incluindo o protocolo, o host, o caminho, o parâmetro da cadeia de caracteres de consulta ou o valor de hash. | Difícil | Campo derivado | O SQL requer análise de sequência personalizada para extrair os mesmos componentes. |

{style="table-layout:auto"}

### Como as configurações de Escopo em funções afetam os feeds de dados {#scope-settings}

[!UICONTROL **Correspondência de Data**], [!UICONTROL **Desduplicar**], [!UICONTROL **Próximo ou Anterior**] e [!UICONTROL **Resumir**] dependem de uma configuração de [!UICONTROL **Escopo**] de Evento, Sessão ou Pessoa (as opções disponíveis variam de acordo com a função). [!UICONTROL **Profundidade**] não tem um campo Escopo configurável, mas está inerentemente vinculado à sessão, semelhante à dimensão Profundidade do Evento padrão. Qualquer campo com um escopo grava o mesmo valor em todas as linhas dentro desse escopo, e esse valor depende dos dados dentro do intervalo de datas da retrospectiva.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Como o intervalo de datas da retrospectiva desliza para a frente com cada delivery de feed de dados, o mesmo campo pode retornar um valor diferente em um delivery posterior, mesmo para eventos que já ocorreram.

O risco aumenta com o tamanho do escopo: o escopo de pessoa traz mais risco do que o escopo de Sessão, porque o histórico de uma pessoa não tem limite de tempo natural em uma execução de feed.

## Modelos de função de campo derivados

[Os modelos de função de campo derivado](/help/data-views/derived-fields/derived-fields.md#templates) permitem criar rapidamente um campo derivado para um caso de uso específico, como criar canais de marketing, detectar bots ou extrair um parâmetro UTM de uma URL. Como um modelo é criado a partir de uma cadeia de regras pré-criadas, usar uma é quase sempre preferível a reproduzir a mesma lógica em SQL do zero.

Se um modelo incluir uma função que dependa de uma configuração de Escopo, o modelo herdará o cuidado de escopo dessa função. Consulte [Como as configurações de Escopo nas funções afetam os feeds de dados](#scope-settings).

