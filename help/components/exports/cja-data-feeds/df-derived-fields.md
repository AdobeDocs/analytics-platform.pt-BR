---
title: Aplicar transformações de dados para feeds de dados
description: Saiba mais sobre as diferentes maneiras de transformar dados do feed de dados, usando configurações de componente, campos derivados ou SQL.
hide: true
feature: Components
source-git-commit: 082927c1d511ba0831beba08aaaac0e2d0d9fbf6
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 5%
---
# Aplicar transformações de dados para feeds de dados

{{release-limited-testing}}

Você pode transformar os dados do feed de dados usando um dos seguintes métodos:

* [Configurações do componente de visualização de dados](/help/data-views/component-settings/overview.md), usando

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

* SQL

Às vezes, o método escolhido é uma questão de preferência. A tabela a seguir compara as compensações.

## Comparar métodos de transformação de dados

A tabela a seguir compara as vantagens e desvantagens de cada método em geral.

| Método | Vantagens | Desvantagens |
| --- | --- | --- |
| **Configurações de componente** | <ul><li>Aplicado no momento do relatório, antes que seu feed de dados seja entregue.</li><li>A mesma lógica se aplica de forma consistente na saída do Analysis Workspace e do feed de dados.</li><li>Não usa um dos campos derivados limitados da sua conta.</li><li>Algumas transformações, como persistência e desduplicação de métrica, são difíceis de replicar no SQL e, no momento, a persistência também não é possível com um campo derivado.</li></ul> | <ul><li>Disponível somente para o conjunto específico de configurações que cada componente aceita, não tão flexível quanto criar uma lógica personalizada com um campo derivado.</li><li>Se uma configuração afeta a saída do feed de dados ainda está sendo confirmada para algumas configurações. Consulte a tabela abaixo.</li></ul> |
| **Campos derivados** | <ul><li>Aplicado no momento do relatório, antes que seu feed de dados seja entregue.</li><li>A mesma lógica se aplica de forma consistente na saída do Analysis Workspace e do feed de dados.</li><li>Suporta lógica mais flexível e personalizada do que qualquer configuração de componente único, como regras condicionais encadeadas.</li><li>Algumas transformações, particularmente aquelas que dependem de uma configuração de Escopo ou que analisam um URL, são difíceis de replicar no SQL.</li></ul> | <ul><li>Adiciona sobrecarga de processamento, o que pode afetar o desempenho de entrega do feed de dados.<!--Under a future usage-based pricing model, this could also add cost.--></li><li>Usa um dos campos derivados limitados da sua conta. Se uma configuração de componente puder fazer o mesmo trabalho, prefira isso.</li></ul> |
| **SQL** | <ul><li>Não limitado pelos limites de função e operador que se aplicam aos campos derivados.</li><li>Não afeta o desempenho de entrega do feed de dados.</li></ul> | <ul><li>Aplicado depois que seu feed de dados já foi entregue.</li><li>A lógica não se aplica ao Analysis Workspace, portanto, seria necessário duplicá-la separadamente.</li><li>Algumas transformações, particularmente aquelas que dependem de uma configuração de Escopo, que analisam um URL ou que desduplicam ou persistem um valor em um escopo, são difíceis ou impraticáveis de replicar.</li></ul> |

{style="table-layout:auto"}

## Transformações de dados

A tabela a seguir lista transformações de dados específicas, mostrando qual(is) método(s) pode(m) executar cada um, quão difícil seria replicar no SQL e qual método usar. <!--A few transformations are still being confirmed with the engineering team and are marked as open questions — don't treat those as confirmed to affect data feed output until that's resolved.-->

| Transformação | Configuração do componente | Campo derivado | Dificuldade no SQL | Melhor ajuste | Considerações |
| --- | --- | --- | --- | --- | --- |
| **Aplicar lógica condicional ou filtrar valores por critérios** | [Incluir/excluir valores](/help/data-views/component-settings/include-exclude-values.md) | [Caso Quando](/help/data-views/derived-fields/derived-fields.md#casewhen) | Fácil para strings; moderado a difícil para métricas | Para cadeias de caracteres; configuração de componente para métricas | Para valores de sequências de caracteres, comparáveis em todos os três — em grande parte, uma questão de preferência. Para métricas, o SQL requer uma instrução `CASE` combinada com um `COUNT`, o que é viável, mas mais complexo, de modo que a configuração do componente é o caminho mais fácil. |
| **Atribuir crédito por um evento bem-sucedido** | [Atribuição](/help/data-views/component-settings/attribution.md) | Não disponível | Não aplicável | Não aplicável | Não aplicado a métricas em feeds de dados. Não há comportamento do feed de dados a ser replicado, no SQL ou de outra forma. |
| **Valores numéricos de bloco em intervalos** | [Classificação de valor](/help/data-views/component-settings/value-bucketing.md) | Ocorrência quando (manual) | Difícil | Configuração do componente | A complexidade aumenta da configuração de componentes (mais fácil) para o campo derivado (moderado, usando um caso manual quando) para o SQL (mais complexo). |
| **Classificar valores usando um mapeamento de estilo de pesquisa** | Não disponível | [Classificar](/help/data-views/derived-fields/derived-fields.md#classify) | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| **Combinar valores de campo com um delimitador** | Não disponível | [Concatenar](/help/data-views/derived-fields/derived-fields.md#concatenate) | Fácil de moderar | Ou | Espelha a funcionalidade de adicionar várias colunas de dimensão a uma tabela de forma livre, que é limitada à Exportação de tabela completa. Um campo derivado disponibiliza saídas semelhantes em um feed de dados. |
| **Converter o tipo de dados de um campo** | Não disponível | [Typecast](/help/data-views/derived-fields/derived-fields.md#typecast) | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| **Contar ocorrências de métrica (valores vs. instâncias)** | [Comportamento](/help/data-views/component-settings/behavior.md) | Solução alternativa personalizada com base em matemática | Fácil de moderar | Ou | Todas as três abordagens funcionam; se você puder fazer isso nativamente no Customer Journey Analytics, há poucos motivos para não fazê-lo. |
| **Desduplicar um valor dentro de um escopo** | [Desduplicação de métrica](/help/data-views/component-settings/metric-deduplication.md) | [Desduplicar](/help/data-views/derived-fields/derived-fields.md#dedup) | Difícil | Configuração de componente ou campo derivado | Depende de uma configuração de Escopo. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings). A configuração do componente e o campo derivado são aproximadamente equivalentes, mas preferem a configuração do componente, pois não usa um de seus campos derivados limitados. |
| **Determinar a profundidade de um campo em uma sessão** | Não disponível | [Profundidade](/help/data-views/derived-fields/derived-fields.md#depth) | Difícil | Campo derivado | Usa sessão como escopo e não é configurável. <!-- Open question as of 2026-09-09: does the Depth counter carry over across an hourly/daily feed boundary using lookback-window context, or does it restart? Pending confirmation from engineering (Ron Fulkerson / Nate Purser). --> A forma como o contador se comporta quando uma sessão passa por um limite de entrega de feed ainda está sendo confirmada com a engenharia. Depende de uma configuração de Escopo. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings). |
| **Localizar e substituir um valor literal** | Não disponível | [Localizar e Substituir](/help/data-views/derived-fields/derived-fields.md#find-and-replace) | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| **Formatar um valor para exibição** | [Formato](/help/data-views/component-settings/format.md) | Não disponível | Difícil | Configuração do componente | A formatação de data e hora ainda não é refletida na saída do feed de dados — atualmente, os feeds mostram o carimbo de data e hora padrão, independentemente dessa configuração, embora a Adobe planeje oferecer suporte a isso para disponibilidade geral. Ainda está sendo confirmado com a equipe se os formatos numéricos (decimal, moeda, porcentagem) nas métricas afetam a saída do feed de dados. |
| **Dimensões de grupo dos conjuntos de dados de resumo** | [Grupo de dados de resumo](/help/data-views/component-settings/summary-data-group.md) | Não disponível | Abrir pergunta | Abrir pergunta | Ainda não discutido com a equipe. Não suponha que isso afete a saída do feed de dados até que seja confirmado. |
| **Manipular um campo em branco (&quot;nenhum valor&quot;)** | [Sem opções de valor](/help/data-views/component-settings/no-value-options.md) | Não disponível | Abrir pergunta | Abrir pergunta | Se isso afetar a saída do feed de dados — incluindo se um valor em branco é enviado como nulo e se &quot;Tratar como um valor&quot; altera os dados subjacentes — ainda está sendo revisado com a equipe. |
| **Pesquisar um valor de um conjunto de dados de pesquisa** | Não disponível | [Pesquisa](/help/data-views/derived-fields/derived-fields.md#lookup) | Fácil de moderar | Ou | O SQL funciona se uma tabela de pesquisa já existir. |
| **Letra minúscula de uma cadeia de caracteres** | [Comportamento](/help/data-views/component-settings/behavior.md) | [Minúsculas](/help/data-views/derived-fields/derived-fields.md#lowercase) | Fácil de moderar | Configuração de componente ou campo derivado | Ambos são equivalentes, mas preferem a configuração do componente, pois ele não usa um de seus campos derivados limitados. |
| **Mesclar vários campos em um** | Não disponível | [Mesclar Campos](/help/data-views/derived-fields/derived-fields.md#merge) | Fácil de moderar | Ou | — |
| **Analisar uma URL em seus componentes** | [Substring](/help/data-views/component-settings/substring.md) (método de análise de URL) | [Análise de URL](/help/data-views/derived-fields/derived-fields.md#urlparse) | Difícil | Configuração de componente ou campo derivado | O SQL requer análise de sequência personalizada para extrair os mesmos componentes. <!-- Possible discrepancy: in the component settings meeting, Matt and Derek described all Substring methods, including URL parse, as roughly interchangeable across component setting, derived field, and SQL ("either one would work... maybe a preference"), which is a looser SQL-difficulty read than "Difficult." Flagged for Luke to reconcile; not changed without confirmation. --> |
| **Realizar matemática básica em campos numéricos** | Não disponível | [Matemática](/help/data-views/derived-fields/derived-fields.md#math) | Fácil de moderar | Ou | Reproduzível em SQL, mas usar um campo derivado mantém a mesma lógica aplicada consistentemente na saída do Analysis Workspace e do feed de dados. |
| **Persistir um valor de dimensão em vários eventos** | [Persistência](/help/data-views/component-settings/persistence.md) | <!-- Derek: considering adding this to FDL and surfacing it in derived fields; not currently possible. --> não disponível no momento | Difícil | Configuração do componente | É muito mais fácil usar a configuração do componente do que replicar essa lógica no SQL. Já confirmado para interagir com o intervalo de datas de retrospectiva da mesma forma que as funções de campo derivadas dependentes de escopo. Consulte [Entender o intervalo de datas da pesquisa](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range). |
| **Substituir um valor usando uma expressão regular** | [Substring](/help/data-views/component-settings/substring.md) (método Regex) | [Substituição de Regex](/help/data-views/derived-fields/derived-fields.md#regex-replace) | Fácil de moderar | Ou | Todas as três abordagens produzem o mesmo resultado; é uma questão de preferência. |
| **Resolver o valor seguinte ou anterior em uma sessão** | Não disponível | [Próximo ou Anterior](/help/data-views/derived-fields/derived-fields.md#next-previous) | Difícil | Campo derivado | Depende de uma configuração de Escopo. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings). |
| **Retornar a diferença entre duas datas** | Não disponível | [Matemática da Data](/help/data-views/derived-fields/derived-fields.md#datemath) | Difícil | Campo derivado | Complexo para replicar no SQL. Depende de uma configuração de Escopo. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings). |
| **Definir o escopo de uma métrica como baseada em evento, perfil ou total** | [Escopo](/help/data-views/component-settings/scope.md) | Não disponível | Abrir pergunta | Abrir pergunta | Ainda não discutido com a equipe. Não suponha que isso afete a saída do feed de dados até que seja confirmado. |
| **Dividir um valor delimitado** | [Substring](/help/data-views/component-settings/substring.md) (Delimitador ou método Da esquerda/direita) | [Dividir](/help/data-views/derived-fields/derived-fields.md#split) | Fácil de moderar | Ou | Todas as três abordagens produzem o mesmo resultado; é uma questão de preferência. |
| **Resumir ou agregar um valor em um escopo** | Não disponível | [Resumir](/help/data-views/derived-fields/derived-fields.md#summarize) | Difícil | Campo derivado | Depende de uma configuração de Escopo. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings). |
| **Cortar caracteres de uma cadeia de caracteres** | [Substring](/help/data-views/component-settings/substring.md) (método Trim) | [Cortar](/help/data-views/derived-fields/derived-fields.md#trim) | Fácil de moderar | Ou | Todas as três abordagens produzem o mesmo resultado; é uma questão de preferência. |

{style="table-layout:auto"}

### Como as configurações de Escopo afetam os feeds de dados {#scope-settings}

As opções Matemática de Data, Desduplicar, Próximo ou Anterior e Resumir dependem de uma configuração de [!UICONTROL **Escopo**] de Evento, Sessão ou Pessoa (as opções disponíveis variam de acordo com a função). A Profundidade não tem um campo Escopo configurável, mas está inerentemente vinculada à sessão, semelhante à dimensão Profundidade do evento padrão. Qualquer campo com um escopo grava o mesmo valor em todas as linhas dentro desse escopo, e esse valor depende dos dados dentro do intervalo de datas da retrospectiva.
<!-- Open question as of 2026-09-09: is the lookback date range boundary anchored to a fixed point (e.g., midnight), or does it float with the feed run time, and is this configurable? Pending confirmation from Ron Fulkerson. -->

Como o [intervalo de datas de retrospectiva](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-lookback-date-range) avança com cada entrega de feed de dados, o mesmo campo pode retornar um valor diferente em uma entrega posterior, mesmo para eventos que já ocorreram.

O risco aumenta com o tamanho do escopo: o escopo de pessoa traz mais risco do que o escopo de Sessão, porque o histórico de uma pessoa não tem limite de tempo natural em uma execução de feed.

## Modelos de função de campo derivados

[Os modelos de função de campo derivado](/help/data-views/derived-fields/derived-fields.md#templates) permitem criar rapidamente um campo derivado para um caso de uso específico, como criar canais de marketing, detectar bots ou extrair um parâmetro UTM de uma URL. Como um modelo é criado a partir de uma cadeia de regras pré-criadas, usar uma é quase sempre preferível a reproduzir a mesma lógica em SQL do zero.

Se um modelo incluir uma função que dependa de uma configuração de Escopo, o modelo herdará o cuidado de escopo dessa função. Consulte [Como as configurações de Escopo afetam os feeds de dados](#scope-settings).
