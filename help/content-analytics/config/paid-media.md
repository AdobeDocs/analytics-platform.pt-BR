---
title: Configuração automática de mídia paga do Content Analytics
description: Saiba mais sobre a configuração automática de conjuntos de dados, conexão, visualizações de dados e muito mais.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: 2727dce145b996192ac873dd43d5106b011ff736
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 4%
---
# Configuração automática de mídia paga

Ao ativar o Canal de mídia paga no Content Analytics e salvar a configuração, o Adobe atualiza a conexão selecionada e as visualizações de dados com a configuração de relatórios para os conjuntos de dados de mídia paga. Você não precisa recriar as dimensões, as métricas, a lógica de pesquisa ou os grupos de dados de resumo por conta própria.

Três camadas de objetos são criadas:

| Objetos | Contém | Propósito |
| --- | --- | --- |
| Conjuntos de dados de resumo | Dados de desempenho da rede Advertising em nível de anúncio, colocação de experiência ou ativo, com detalhamentos demográficos/geográficos separados, quando suportados. | Permite medir a entrega, os cliques, os gastos e os resultados relatados pela rede de publicidade |
| Conjuntos de dados de pesquisa de metadados e atributo | Conta, campanha, grupo de anúncios, anúncio, experiência e detalhes do ativo; atributos criativos da Content Analytics. | Permitem relatar usando nomes reconhecíveis, detalhes criativos, miniaturas e atributos de conteúdo em vez de identificadores. |
| Componentes e configuração da visualização de dados | Dimensões, métricas, métricas calculadas, campos derivados e grupos de dados de resumo. | Permitem criar análises do Workspace sem reconstruir manualmente as relações entre esses conjuntos de dados. |

A ativação da mídia paga não conecta automaticamente os dados de mídia paga aos pedidos, reservas ou receita do site. A correlação entre os dados do evento de experiência e os dados de mídia paga requer uma configuração de mapeamento e relatórios de chaves de rastreamento específica do cliente.

## Conjuntos de dados de resumo

A ilustração abaixo mostra como os conjuntos de dados de resumo são gerados quando você habilita o canal de mídia paga no Content Analytics para uma ou mais de suas redes de anúncios. As APIs relevantes das redes de anúncios disponíveis são usadas para baixar e transformar dados de experiências, ativos e anúncios em possivelmente seis conjuntos de dados de resumo.

![Geração de mídia paga de conjuntos de dados de resumo](/help/content-analytics/assets/paid-media-generation-of-datasets.svg)

Os conjuntos de dados de resumo criados são determinados pela rede de anúncios específica. Nem toda rede de anúncios, para a qual você configurou um conector de origem, gera todos os seis conjuntos de dados de resumo possíveis. Consulte a tabela abaixo para obter uma visão geral dos conjuntos de dados de resumo com as seguintes informações:

* Nome do conjunto de dados de resumo, tipo de evento e sufixo do componente
* Entidade
* Detalhamentos
* Quais conjuntos de dados estão preenchidos ![Marca de seleção](/help/assets/icons2/Checkmark.svg) para as seguintes redes:
  * ![MetaSolid](/help/assets/icons2/MetaSolid.svg) Meta
  * Google ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg)
  * Pinterest ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg)
  * ![Snapchat](/help/assets/icons2/Snapchat.svg) Snapchat
  * TikTok ![TikTok](/help/assets/icons2/TikTok.svg)

    >[!AVAILABILITY]
    >
    >O Pinterest, o Snapchat e o TikTok estão na fase de Teste limitado da versão e podem ainda não estar disponíveis em seu ambiente. Essa observação será removida quando a funcionalidade estiver em disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md)
    >


* o que cada linha em um conjunto de dados de resumo representa.

| Conjunto de dados de resumo<br/>Tipo de evento<br/>Sufixo do componente | Entidade | Detalhamento | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Cada linha representa |
|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Publicidade | None | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio sem detalhamentos demográficos ou geográficos. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Publicidade | idade, sexo | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio, detalhado por idade e sexo. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Publicidade | país, região | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio, detalhado por país e região. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experiência | plataforma, posição | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário associado à experiência criativa de um anúncio, detalhado por plataforma e posição. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Ativo | None | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário no nível do ativo no contexto de anúncios/campanhas, sem detalhamento demográfico ou geográfico. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Ativo | idade, sexo | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | | | Desempenho diário do nível do ativo no contexto do anúncio/campanha, detalhado por idade e sexo. |


Essa tabela descreve a cobertura do conjunto de dados, não uma garantia de que cada métrica ou campo de metadados seja preenchido por uma rede específica. Verifique os campos necessários para a análise. Um campo indisponível ou um detalhamento não compatível não é o mesmo que um valor zero medido para um campo.

Conjuntos de dados de pesquisa separados descrevem Conta, Campanha, Grupo de publicidade, Anúncio, Experiência e Ativo. Eles fornecem nomes e metadados usando GUIDs de entidade. Não existe emparelhamento um para um entre os conjuntos de dados de resumo e os seis conjuntos de dados de pesquisa.

O agrupamento de dados de resumo reúne dimensões equivalentes; o agrupamento não totaliza os seis totais de métricas de desempenho.

## Componentes

O canal de mídia paga da Content Analytics, uma vez ativado, também gera vários componentes de visualização de dados. Esses componentes são fornecidos com um sufixo de componente para distinguir componentes nomeados semelhantes entre si.

### Métricas

Redes de anúncios diferentes retornam detalhamentos de desempenho diferentes. O Content Analytics preserva essas distinções em vez de tratar cada versão de uma métrica como intercambiável.

Por exemplo:

| Componente | Significado | Análise inicial adequada |
| --- | --- | --- |
| Cliques \| Resumo do anúncio | Cliques relatados no nível sem detalhamento do anúncio | Desempenho da campanha ou do anúncio |
| Cliques \| Resumo do ativo | Cliques relatados no nível do ativo | Desempenho do ativo Creative |
| Cliques \| Ad Geo | Cliques no relatório ad-geography | Desempenho por país ou região |
| Cliques \| Posicionamento da experiência | Cliques no relatório de posicionamento de experiência | Desempenho do Creative por posicionamento |

Cada componente de métrica de cliques serve a um contexto de relatório diferente. Não é possível simplesmente totalizar esses componentes de métrica em um total geral. A mesma atividade publicitária subjacente pode ser representada em mais de um conjunto de dados de resumo.

### Dimensões

Cada conjunto de dados de resumo contém IDs e GUIDs. A ID é a identidade (para conta, campanha, grupo de anúncios, anúncio, experiência e ativo) fornecida pela rede de anúncios e é exclusiva **em** os dados da rede de anúncios. O GUID é uma identidade fornecida pela Adobe (para conta, campanha, grupo de anúncios, anúncio, experiência e ativo) e é exclusiva **em** redes de anúncios. IDs e GUIDs são usados para pesquisar os nomes e metadados correspondentes.

### Campos derivados

Os campos derivados fazem parte da configuração de relatórios automáticos. Os campos derivados traduzem identificadores em nomes e metadados, expõem atributos criativos e oferecem suporte às dimensões equivalentes usadas em fontes de relatórios. Eles não criam atividade de publicidade adicional ou atribuem automaticamente uma conversão de site.

Use o mesmo detalhamento para as métricas em uma análise e as dimensões compatíveis com esse detalhamento. Esteja ciente de que os totais demográficos e geográficos não são necessariamente iguais aos totais sem detalhamento para uma rede de anúncios e não implicam uma falha de assimilação.

## Relatórios e análises

Depois de concluir a configuração e a assimilação da mídia paga do Content Analytics, você pode começar com os relatórios e a análise. Consulte a tabela abaixo para obter alguns exemplos. Use as dimensões agrupadas canônicas quando disponíveis e escolha métricas no nível de relatório correspondente.

| Pergunta comercial | Nível inicial | Linhas e divisões | Métricas iniciais | Limite importante |
| --- | --- | --- | --- | --- |
| Como está o desempenho de minhas campanhas e anúncios? | Resumo do anúncio | Nome da campanha, Nome do grupo de anúncios, Nome do anúncio; opcionalmente, Rede de publicidade e Nome da conta | Impressões \| Resumo do anúncio, cliques \| Resumo do anúncio, gastos \| Resumo do anúncio, CTR e CPC correspondentes | Usar um nível para totais de entrega/gastos; validar moeda antes de combinar contas |
| Quais ativos criativos obtêm a resposta mais forte? | Resumo do ativo | Nome do ativo (mídia paga), identidade do ativo; opcionalmente, Rede de publicidade | Impressões \| Resumo do ativo, cliques \| Resumo do ativo, taxa de click-through \| Resumo do ativo | Esse é o desempenho do ativo relatado pela rede, não a prova de uma conversão posterior no site |
| Quais características de imagem estão associadas ao desempenho? | Resumo do ativo | Tags de ativos, Objetos de ativos, Categorias de pessoas de ativos, Cenas de ativos ou outros atributos de ativos disponíveis | Impressões, cliques e CTR do resumo do ativo | A extração de atributos deve estar disponível; categorias de atributos com vários valores podem se sobrepor |
| Quais características de mensagens estão associadas ao desempenho pago? | Posicionamento da experiência | Palavras-chave de experiência, tons de experiência, estratégias de persuasão de experiência ou outros atributos de experiência disponíveis; opcionalmente, Plataforma e posicionamento | Impressões \| Posicionamento da experiência, cliques \| Posicionamento da experiência, CTR correspondente | Requer atributos de experiência preenchidos; os resultados são específicos da disposição e descrevem a associação, não o impacto causal |
| Quais posicionamentos têm melhor desempenho? | Posicionamento da experiência | Nome da experiência, Plataforma, Posicionamento | Impressões \| Posicionamento da experiência, cliques \| Posicionamento da experiência, CTR correspondente | As definições de posicionamento e os valores disponíveis variam de acordo com a rede de publicidade |
| Como os anúncios/ativos/experiências do Meta e do Google se comparam? | Resumo de anúncios, Resumo de ativos ou Posicionamento de experiência, escolhidos para a pergunta | Rede de publicidade com a dimensão de campanha, ativo ou experiência apropriada | A mesma definição de nível e métrica para ambas as redes | Comparar apenas campos preenchidos por ambas as redes; o Google não preenche os três resumos demográficos/geográficos neste modelo |

Esses relatórios podem revelar associações entre atributos criativos e desempenho, não provar que um atributo causou um resultado.

Evite combinações incompatíveis: o Nome do ativo (mídia paga) com as métricas do Resumo de anúncios não substitui um relatório de ativos. Use as métricas de Resumo de ativos para a análise de ativos e as métricas de Geografia de anúncios para a análise de regiões. Células vazias ou zero de um emparelhamento incompatível não devem ser interpretadas como prova de ausência de atividade.

### Exemplo de desempenho da campanha publicitária

Você deseja relatar o desempenho da campanha no nível do anúncio. No Analysis Workspace, use o Nome da campanha como a dimensão (linhas) e use as métricas conforme descrito na tabela abaixo. Cada métrica tem o mesmo sufixo de componente.

| Métricas | Nível de relatório |
| --- | --- |
| Impressões | Resumo do anúncio |
| Cliques | Resumo do anúncio |
| Gastos | Resumo do anúncio |
| Índice de click-through | Resumo do anúncio |
| Custo por clique | Resumo do anúncio |

Opcionalmente, analise o Nome da campanha por Nome do anúncio, mas mantenha todas as cinco colunas no nível do Resumo do anúncio.

Para investigar ativos individuais, use uma tabela separada com o Nome do ativo (mídia paga) e as colunas correspondentes do Resumo do ativo. Não adicione os totais das duas tabelas juntas.

### Exemplo de anúncios com melhor desempenho de rede

Você quer entender qual é o melhor desempenho dos seus anúncios do Meta?

Para investigar, use detalhamentos adicionais para geografia e demografia. Use o Nome da campanha ou o Nome do anúncio como a dimensão e use as métricas conforme descrito na tabela abaixo. Cada métrica tem o mesmo sufixo de componente.

| Métricas | Nível de relatório |
| --- | --- |
| Impressões | Geografia do anúncio |
| Cliques | Geografia do anúncio |
| Gastos | Resumo do anúncio |
| Índice de click-through | Geografia do anúncio |
| Custo por clique | Resumo do anúncio |


