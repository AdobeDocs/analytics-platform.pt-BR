---
title: Dimensões de alta cardinalidade
description: Explica como o Customer Journey Analytics lida com dimensões com muitos valores únicos.
feature: Dimensions
solution: Customer Journey Analytics
exl-id: 17b275a5-c2c2-48ee-b663-e7fe76f79456
role: User
TQID: https://experienceleague.adobe.com/cDOJq7Dc6x301enIo7h-cm8pGphmnvQAihnLoYGIr-A
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 622
ht-degree: 11%

---

# Dimensões de alta cardinalidade

Ao usar uma dimensão que contém muitos valores únicos, o relatório resultante pode conter muitos itens de dimensão únicos para exibir ou calcular. Os resultados são truncados com a remoção dos itens de dimensão considerados menos importantes. Essas otimizações são feitas para manter o desempenho do projeto e do produto.

Quando você solicita um relatório que contém uma dimensão com um excesso de valores exclusivos, o Analysis Workspace exibe um indicador no cabeçalho da dimensão para informar que nem todos os itens da dimensão estão incluídos. Por exemplo, **[!UICONTROL Linhas: 1-50 de mais de 22.343.156]**. A palavra-chave **[!UICONTROL more than]** indica que alguma otimização foi aplicada ao relatório para retornar os itens de dimensão mais importantes.

![Tabela de forma livre no Workspace mostrando a palavra-chave &quot;mais de&quot; para mostrar 1-50 de mais de 22.343.156](assets/high-cardinality.png)

## Determinar quais itens de dimensão exibir

O Customer Journey Analytics processa relatórios no momento em que são executados, distribuindo o conjunto de dados combinado a vários servidores. O tamanho da solicitação de dados e a quantidade de hardware Adobe disponível são dois dos muitos fatores que ajudam a determinar o número de servidores atribuídos para processar um relatório. Como os servidores são atribuídos dinamicamente e não são visíveis na interface, não há uma maneira de ver ou controlar o número de servidores que processam um relatório.

Os dados por servidor de processamento são agrupados pela ID de pessoa, o que significa que um único servidor de processamento contém todos os dados de uma determinada pessoa. Depois que um servidor termina o processamento, ele entrega seu subconjunto de dados processados a um servidor agregador. Todos os subconjuntos de dados processados são combinados e retornados no formato de um relatório do Workspace.

Se qualquer servidor individual processar dados que excedam um limite exclusivo, ele truncará os resultados antes de retornar o subconjunto de dados processado. Os itens de dimensão truncados são determinados com base na métrica usada para classificação.

Se a métrica de classificação for uma métrica calculada, o servidor utilizará as métricas contidas na métrica calculada para determinar quais itens de dimensão serão truncados. Como as métricas calculadas podem conter várias métricas de importância variável, os resultados podem ser menos precisos. Por exemplo, ao calcular &quot;Receita por pessoa&quot;, o valor total da receita e o número total de pessoas são retornados e agregados antes de fazer a divisão. Como resultado, cada servidor de processamento individual escolhe quais itens serão removidos sem saber como seus resultados afetam a classificação geral.

Embora alguns itens de dimensão individuais possam estar ausentes nos relatórios de alta cardinalidade, os totais da coluna são precisos e não se baseiam em dados truncados. A função de métrica calculada [[!UICONTROL Contagem distinta aproximada]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct) também não é afetada por itens de dimensão truncados.

## Práticas recomendadas para dimensões de alta cardinalidade

A melhor maneira de acomodar dimensões de alta cardinalidade é limitar o número de itens de dimensão que um relatório processa. Como todos os relatórios são processados no momento em que são solicitados, você pode ajustar os parâmetros do relatório para resultados imediatos. A Adobe recomenda qualquer uma das seguintes otimizações para dimensões de alta cardinalidade:

* Use um [segmento](/help/components/segments/seg-create.md). Os segmentos são aplicados no momento em que cada servidor processa um subconjunto de dados.
* Use uma pesquisa. Os itens de Dimension excluídos do termo de pesquisa são removidos dos resultados do relatório, tornando mais provável que você veja os itens de dimensão desejados.
* Use uma dimensão de conjunto de dados de pesquisa. As dimensões do conjunto de dados de pesquisa combinam itens de dimensão do conjunto de dados do evento, que limitam o número de valores únicos retornados.
* Use a configuração de componente [Incluir/excluir](/help/data-views/component-settings/include-exclude-values.md) no gerenciador de visualização de dados.
* Diminua o intervalo de datas da solicitação. Se muitos valores únicos se acumularem ao longo do tempo, a redução do intervalo de datas do relatório do Workspace pode limitar o número de valores únicos a serem processados pelos servidores.
* Considere usar [Exportação de Tabela Completa](/help/analysis-workspace/export/export-cloud.md) para retornar todas as linhas da tabela.
* Se o número de valores únicos for o foco principal, use a função de métrica calculada [[!UICONTROL Contagem distinta aproximada]](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct).
