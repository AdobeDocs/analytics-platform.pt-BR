---
description: Saiba como comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
keywords: sequência de cliques;feed de dados;datafeed;Feed de dados
title: Comparar a funcionalidade de feeds de dados no Customer Journey Analytics e no Adobe Analytics
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 4872f0078640fbd358a60a6d7baeb3ea575d3559
workflow-type: tm+mt
source-wordcount: 1629
ht-degree: 0%

---

# Comparar feeds de dados no Customer Journey Analytics e no Adobe Analytics

{{release-limited-testing}}

Os feeds de dados no Customer Journey Analytics e no Adobe Analytics permitem exportar dados brutos para plataformas de terceiros.

Se você usou feeds de dados anteriormente no Adobe Analytics, use as seguintes informações para entender as diferenças nos recursos e conceitos disponíveis.

Para obter uma comparação dos feeds de dados com outros métodos de exportação do Customer Journey Analytics, como Exportação de tabela completa, consulte [Comparação de produtos do Analytics](/help/getting-started/analytics-product-comparison.md).

## Recursos disponíveis somente nos feeds de dados do Customer Journey Analytics

Os seguintes recursos estão disponíveis nos feeds de dados do Customer Journey Analytics, mas não nos feeds de dados do Adobe Analytics:

* **Campos derivados**: componentes personalizados criados a partir de transformações baseadas em regras que podem ser incluídos no esquema do feed de dados. <!-- add benefit -->

* **Compilação**: resolução de identidade entre dispositivos que vincula eventos entre dispositivos a uma única pessoa.

* **Modelo de dados estruturados**: os feeds são criados e entregues usando dados estruturados em vez de cadeias de caracteres simples, como post_product_list. Reflete a estrutura existente do esquema XDM e da visualização de dados.

* **Saída do Parquet**: os arquivos são entregues no formato Parquet, que suporta nativamente dados aninhados e estruturados complexos. Isso significa que é mais fácil acessar os dados em um banco de dados usando as práticas padrão do setor.

* **Segmentação**: os segmentos aplicados à visualização de dados são automaticamente herdados e segmentos adicionais podem ser aplicados diretamente ao feed.

* **Caminhos de partição de estilo Hive**: os arquivos de saída usam caminhos de estilo Hive para consulta eficiente em ambientes de data lake.

* **As atualizações de componentes se aplicam retroativamente**: as alterações nos componentes na visualização de dados são refletidas historicamente em preenchimentos retroativos.

* **Pesquisas**: as classificações não estão incluídas nos feeds de dados do Adobe Analytics. No Customer Journey Analytics, todas as pesquisas são incorporadas diretamente aos dados.

* **Interface familiar aos usuários do Analysis Workspace**: os componentes vêm diretamente da visualização de dados e também estão disponíveis no Analysis Workspace. É possível selecionar dimensões e métricas usando o mesmo painel de componentes do Analysis Workspace, em vez de uma lista estática de nomes de variáveis.

* **Mais modelos de persistência disponíveis**: há cinco modelos de persistência diferentes que podem ser usados nos feeds de dados do Customer Journey Analytics.

<!-- * Web MCP when it's added -->

A tabela [Comparação de funcionalidade](#functionality-comparison) abaixo aborda detalhadamente cada um desses recursos, juntamente com as diferenças nos recursos existentes em ambos os produtos.


## Comparação de funcionalidade

A tabela a seguir compara os principais conceitos e opções de configuração entre os feeds de dados do Customer Journey Analytics e os feeds de dados do Adobe Analytics.

| **Conceitos e opções de configuração** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **Entrada de dados**<br/> O tipo de dados que pode ser coletado e incluído nos feeds de dados. | Suporta entrada de dados entre canais, incluindo dados da Web, dados da central de atendimento, dados de pontos de venda e muito mais. | Oferece suporte principalmente à entrada de dados da Web e móveis. Outros tipos de dados (como call center ou dados de ponto de venda) podem ser assimilados por meio de fontes de dados, mas com recursos de processamento muito limitados. |
| **Processamento de dados**<br/> Os dados são processados em estágios diferentes, dependendo do produto que você está usando. | Os dados são processados em **horário do relatório** e, portanto, muitos recursos de relatório podem ser usados para alterar dados históricos, como compilação, campos derivados e segmentação. | Os dados são processados no **momento da coleta** e, portanto, os recursos de relatório como regras de processamento e regras VISTA não afetam os dados históricos. |
| **Compilação**<br/> Resolução de identidade entre canais e dispositivos que vincula eventos a uma única pessoa. | Compatível. As identidades compiladas podem ser incluídas nas exportações do feed de dados quando a compilação é configurada na conexão. | Não suportado. A identidade do visitante é determinada no momento da coleta dos cookies de ID do visitante; nenhuma resolução entre dispositivos pós-coleta está disponível. |
| **Frequência de entrega**<br/> Determina a frequência com que o feed de dados é enviado e a janela de tempo incluída no feed. | **Diariamente** (da meia-noite à meia-noite no fuso horário da visualização de dados) ou **Por hora**. | **Diariamente** (da meia-noite à meia-noite no fuso horário do conjunto de relatórios) ou **Por hora**. <p>Os feeds de 15 minutos são possíveis, mas não estão disponíveis por padrão.</p> |
| **Ocorrências de chegada tardia**<br/> Ocorrências cujos carimbos de data/hora pertencem a uma janela de frequência de entrega anterior, mas chegam após o término dessa janela. <p>Por exemplo, as ocorrências de chegada tardia podem vir de um aplicativo móvel que armazena eventos em buffer enquanto está offline e os envia quando ele se reconecta.</p> | A configuração **Atraso de processamento** controla quanto tempo o sistema aguarda depois que a janela de frequência é fechada antes de acionar a exportação, reservando mais tempo para que os dados atrasados cheguem. | As ocorrências de chegada tardia podem ser **incluídas ou excluídas** por meio da opção de configuração **Ocorrências de chegada tardia**. <p>A configuração **Janela de pesquisa** controla até que ponto o sistema alcança para incluir dados atrasados.</p> |
| **Ocorrências fora de ordem**<br/> Ocorrências cujos carimbos de data/hora não correspondem à ordem em que foram recebidas. | Como o Customer Journey Analytics aceita transmissão e dados em lote, não há garantia de que os eventos de uma determinada pessoa chegarão na ordem de carimbo de data e hora. Embora o Customer Journey Analytics seja reordenado por carimbo de data e hora por pessoa, ele só pode exportar os dados recebidos. Isso significa que as ocorrências de chegada tardia podem ser exportadas após as ocorrências com um carimbo de data e hora posterior.<p>A configuração **Atraso de processamento** ajuda a reduzir eventos fora de ordem na saída do feed de dados, dando mais tempo para que os dados em lote cheguem antes da exportação. A ordenação de eventos no delivery não é garantida.</p><p>**Importante**: o consumidor final dos dados do feed de dados deve ser capaz de lidar com carimbos de data/hora que estejam fora de ordem, por pessoa, pois a ordem de ocorrências na entrega do feed de dados não é garantida.</p> | O Adobe Analytics exige que os dados cheguem em ordem por visitante no momento da coleta, mas a ordem de ocorrência na entrega do feed de dados não é garantida. |
| **Janela de preenchimento retroativo**<br/> Exporta dados históricos entre duas datas anteriores. | Limitado à janela de dados contínuos da conexão. | Limitado ao limite de retenção de dados do conjunto de relatórios: **25 meses** por padrão. |
| **Esquema**<br/> O esquema de feed de dados determina quais colunas estão disponíveis para inclusão em um feed de dados. | O esquema do feed de dados é baseado na configuração da visualização de dados.  Os componentes disponíveis para inclusão no esquema de feed de dados são um subconjunto dos componentes disponíveis na configuração da visualização de dados. | Uma lista estática predefinida de ~1.100+ variáveis. Muitas colunas são exportadas como **pares pré e pós-processados** (por exemplo, `eVar1` / `post_eVar1`), o que responde por grande parte da contagem de colunas. |
| **Construtor de feed de dados**<br/> A interface usada para configurar quais colunas são incluídas em um feed de dados. | Usa um painel de componentes com as mesmas dimensões e métricas nomeadas disponíveis na visualização de dados, que corresponde à experiência do Analysis Workspace. | Usa uma lista simples de nomes de variáveis brutas (como `eVar1`, `prop5`) selecionados de um conjunto predefinido de ~1.100+ colunas. Os componentes não são nomeados ou descritos além do identificador de variável. |
| **Campos derivados**<br/> Componentes personalizados definidos com o uso de transformações baseadas em regras aplicadas no momento do relatório. | Compatível. Os componentes de campo derivados podem ser incluídos no esquema de feed de dados ao lado de dimensões e métricas padrão. | Não suportado. |
| **Atualizações de componentes**<br/> Se as alterações na configuração de componentes se refletem na saída de feeds de dados passada e futura. | As alterações nos componentes na visualização de dados (como renomear ou remover uma dimensão) se propagam para feeds de dados futuros e também são refletidas em preenchimentos retroativos. | As alterações nos componentes do conjunto de relatórios se aplicam apenas aos dados coletados no futuro. |
| **Pesquisas**<br/> Os conjuntos de dados de pesquisa no Customer Journey Analytics são equivalentes às classificações no Adobe Analytics. | Todas as pesquisas são incorporadas diretamente aos dados. | As classificações não estão incluídas nos feeds de dados do Adobe Analytics. |
| **Definição de sessão**<br/> Como um limite de visita ou sessão é definido, o que afeta como os eventos são agrupados e atribuídos. | Definido na visualização de dados. | Definido no momento da coleta. |
| **Segmentação**<br/> A capacidade de filtrar a saída do feed de dados usando segmentos. | Os segmentos aplicados à visualização de dados são herdados automaticamente pelo feed de dados. Segmentos adicionais também podem ser aplicados diretamente a um feed de dados individual. Para obter mais informações, consulte [Segmentação em feeds de dados](/help/components/exports/cja-data-feeds/df-segmentation.md). | Não suportado. Os feeds de dados exportam todos os dados coletados sem filtragem de segmento. |
| **Métricas calculadas**<br/> As métricas personalizadas que você pode criar a partir das métricas existentes. | Não suportado | Não suportado |
| **Modelo de persistência**<br/> Como ou se os valores de dimensão persistem de um evento para o próximo. | Flexível. As configurações de persistência da visualização de dados (alocação e expiração) são aplicadas no momento do relatório em que o feed é gerado. Dá suporte a todas as configurações de alocação disponíveis em uma visualização de dados: **Original**, **Mais Recente**, **Todos**, **Primeiro Conhecido** e **Último Conhecido**. | Somente **os modelos de atribuição mais recentes (último contato)** e **valores originais (primeiro contato)** são representados. A alocação linear é tratada da mesma forma que o último contato. |
| **Formato de arquivo de saída**<br/> O formato usado para arquivos de saída de feed de dados entregues ao seu destino de nuvem. | Parquet<p>Suporta nativamente dados complexos aninhados e estruturados. Campos como `post_product_list` são representados como matrizes estruturadas/objetos aninhados. </p><p>Requer uma ferramenta sensível ao Parquet para leitura, como BigQuery, Snowflake ou Apache Spark.</p><p>A estrutura do schema é incorporada no arquivo de saída.</p> | TSV<p>Linhas planas legíveis por humanos. Não é compatível nativamente com dados estruturados; campos complexos, como listas de produtos, devem ser codificados como strings delimitadas proprietárias que exigem lógica de análise personalizada.</p> |
| **Caminhos do arquivo de saída**<br/> A estrutura de diretório usada para os arquivos de saída entregues. | Usa **caminhos de partição no estilo Hive** (por exemplo, `year=2024/month=01/day=15/`), permitindo a remoção eficiente de partições ao consultar dados em ambientes de data lake, como Databricks ou Apache Spark. | Usa uma estrutura de diretório simples. Os caminhos de estilo Hive não são compatíveis. |
| **Destinos de entrega**<br/> Os locais de armazenamento na nuvem para os quais os arquivos de saída do feed de dados podem ser enviados. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. | Amazon S3, Azure RBAC, Azure SAS, Google Cloud Platform. <p>Também suporta **SFTP**.</p> |
| **Semelhança com o Analysis Workspace**<br/> Se o construtor de feed de dados usa os mesmos componentes e terminologia que o Analysis Workspace. | O painel esquerdo nos feeds de dados é semelhante ao painel esquerdo do Workspace, e os componentes disponíveis nos feeds de dados também estão disponíveis no Workspace. | Uma lista estática de nomes de variáveis que não correspondem necessariamente ao que você vê no Analysis Workspace. |
| **Disponibilidade do modelo de persistência**<br/> Os modelos de persistência disponíveis para dimensões em um feed de dados. | Cinco modelos de persistência estão disponíveis para feeds de dados: Original, Mais recente, Todos, Primeiro conhecido, Último conhecido | Dois modelos de persistência estão disponíveis para feeds de dados: primeiro e último contato |

{style="table-layout:auto"}

