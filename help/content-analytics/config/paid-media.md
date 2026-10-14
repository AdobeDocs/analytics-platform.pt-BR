---
title: Configuração automática de mídia paga do Content Analytics
description: Saiba mais sobre a configuração automática de conjuntos de dados, conexão, visualizações de dados e muito mais.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 2a788aa5cf007a434e5b40c65aea0c887bc357e3
workflow-type: tm+mt
source-wordcount: '2545'
ht-degree: 2%
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

A ilustração abaixo mostra como os conjuntos de dados de resumo são gerados ao configurar o primeiro conector de anúncio de mídia pago (por exemplo, para Google Ads ou Meta Ads) no Experience Platform. As APIs relevantes das redes de anúncios disponíveis são usadas para baixar dados de experiência, ativos e anúncios. Esses dados são normalizados em uma estrutura de dados comum e armazenados em seis conjuntos de dados de resumo.

![Geração de mídia paga de conjuntos de dados de resumo](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

Todos os seis conjuntos de dados de resumo são criados por padrão. Se cada conjunto de dados é preenchido com dados depende da rede de anúncios.

Consulte a tabela abaixo para obter uma visão geral dos conjuntos de dados de resumo com as seguintes informações:

* Nome do conjunto de dados de resumo, sufixo do componente, entidade (e detalhamentos).
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


* O que cada linha em um conjunto de dados de resumo representa.

| Conjunto de dados de resumo <br/>`Component suffix`<br/>*Entidade (detalhamentos)* | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Cada linha representa |
|---|:---:|:---:|:---:|:---:|:---:|---|
| **Resumo do anúncio**<br/>`\| Ad Summary`<br/>* Anúncio (nenhum)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio sem detalhamentos demográficos ou geográficos. |
| **Demonstração do anúncio**<br/> `ad.demographics`<br/>`\| Ad Demo`<br/>*Anúncio (idade, gênero)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio<br/>dividido por idade e sexo. |
| **Geografia do anúncio**<br/>`\| Ad Geo`<br/>* Anúncio (país, região)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio<br/>dividido por país e região. |
| **Posicionamento da experiência**<br/>`\| Experience Placement`<br/>* Experiência (plataforma, posição)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário associado<br/>à experiência criativa de um anúncio,<br/>detalhado por plataforma e posição. |
| **Resumo do ativo**<br/>`\| Asset Summary`</br>* Ativo (nenhum)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário no nível do ativo<br/>em contexto de anúncio/campanha<br/>sem detalhamento demográfico ou geográfico. |
| **Demonstração do Assets**<br/>`\| Asset Demo`<br/>* Ativo (idade, gênero)* | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | | | Desempenho diário no nível do ativo<br/>em contexto de anúncio/campanha<br/>detalhado por idade e sexo. |

Essa tabela descreve a cobertura do conjunto de dados, não uma garantia de que uma rede específica preencha cada métrica ou campo de metadados. Verifique os campos necessários para a análise. Um campo indisponível ou um detalhamento não compatível não é o mesmo que um valor zero medido para um campo.

O agrupamento de dados de resumo reúne dimensões equivalentes; o agrupamento não totaliza os seis totais de métricas de desempenho.

## Conjuntos de dados de pesquisa

Conjuntos de dados de pesquisa separados descrevem Conta, Campanha, Grupo de publicidade, Anúncio, Experiência e Ativo. Eles fornecem nomes e metadados usando GUIDs de entidade. Não existe emparelhamento um para um entre os conjuntos de dados de resumo e os seis conjuntos de dados de pesquisa.

Os conjuntos de dados de pesquisa compartilham um bloco de construção comum que contém metadados principais de mídia paga. Esse bloco contém uma chave global gerada pela Adobe e uma ID nativa da plataforma para cada entidade; por exemplo: `accountID` e `accountGUID`, `campaignID` e `campaignGUID` e muito mais. O bloco também armazena campos descritivos comuns, como nome, status, objetivo, meta de otimização, estratégia de licitação, tipo de orçamento, valores de orçamento, moeda, fuso horário, status de atendimento, datas, rede de anúncios, canal, caminho de hierarquia, rede e identificadores de portfólio.

| Conjunto de dados de pesquisa | Conteúdo principal |
|---|---|
| Pesquisa de conta | Metadados a nível de conta, como nome, moeda, fuso horário, status, limite de gastos e datas de criação |
| Pesquisa de campanha | Configurações de campanha para orçamento, agendamento, direcionamento, rastreamento de conversão, atribuição, posicionamentos, objetos promovidos, objetivo e IDs de catálogo ou armazenamento |
| Pesquisa de grupo de anúncios | Metadados do grupo de anúncios, como vinculação de campanha, status, orçamento, metas de otimização e direcionamento |
| Pesquisa de anúncio | Adicionar detalhes criativos, como ativos, variantes, dimensões, URLs de rastreamento, call to action, corpo de texto, títulos, URL de destino, status do delivery e status de revisão |
| Pesquisa de ativo | Propriedades de ativos, como dimensões, detalhes do arquivo, propriedades de imagem, URLs de mídia, metadados de uso, metadados de vídeo, descrição, subtipo, título e tipo |
| Pesquisa de experiência | Agrupamentos criativos de nível de experiência, como ID de experiência, ativos, título, descrição e call to action |


## Componentes

Depois de ativar o Canal de mídia paga no Content Analytics, vários componentes de visualização de dados são gerados. Esses componentes são fornecidos com um sufixo de componente para distinguir componentes nomeados semelhantes entre si.

### Métricas

Redes de anúncios diferentes retornam detalhamentos de desempenho diferentes. O Content Analytics preserva essas distinções em vez de tratar cada versão de uma métrica como intercambiável.

Por exemplo:

| Componente | Conjunto de dados | Análise inicial adequada |
| --- | --- | --- |
| Cliques \| Resumo do anúncio | Cliques relatados no nível sem detalhamento do anúncio | Desempenho da campanha ou do anúncio |
| Cliques \| Resumo do ativo | Cliques relatados no nível do ativo | Desempenho do ativo Creative |
| Cliques \| Ad Geo | Cliques no relatório ad-geography | Desempenho por país ou região |
| Cliques \| Posicionamento da experiência | Cliques no relatório de posicionamento de experiência | Desempenho do Creative por posicionamento |

Cada componente de métrica de cliques serve a um contexto de relatório diferente. Não é possível totalizar esses componentes de métrica em um total geral. A mesma atividade publicitária subjacente pode ser representada em mais de um conjunto de dados de resumo. Devido ao comportamento de relatório das redes de publicidade, os valores de agregação das linhas do conjunto de dados de detalhamento geográfico ou demográfico podem não ser iguais aos valores de agregação do conjunto de dados de não detalhamento. Esse é o motivo para conjuntos de dados resumidos de detalhamento separados.

### Dimensões

Cada conjunto de dados de resumo contém IDs e GUIDs. A ID é a identidade (para conta, campanha, grupo de anúncios, anúncio, experiência e ativo) fornecida pela rede de anúncios e é exclusiva **em** os dados da rede de anúncios. O GUID é uma identidade fornecida pela Adobe (para conta, campanha, grupo de anúncios, anúncio, experiência e ativo) e é exclusiva **em** redes de anúncios. As GUIDs são usadas para pesquisar os nomes e metadados correspondentes.

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

### Exemplos

Abaixo estão exemplos de como relatar e analisar o desempenho de mídia paga e como combinar dados de experiência e ativos do Content Analytics com dados de mídia paga.

#### Desempenho da campanha publicitária

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

#### Identificação dos anúncios com melhor desempenho

Você quer entender qual é o melhor desempenho dos seus anúncios do Meta?

Para investigar, use detalhamentos adicionais para geografia e demografia. Use o Nome da campanha ou o Nome do anúncio como a dimensão e use as métricas conforme descrito na tabela abaixo. Cada métrica tem o mesmo sufixo de componente.

| Métricas | Nível de relatório |
| --- | --- |
| Impressões | Geografia do anúncio |
| Cliques | Geografia do anúncio |
| Gastos | Geografia do anúncio |
| Índice de click-through | Geografia do anúncio |
| Custo por clique | Geografia do anúncio |


#### Associar dados de mídia paga com dados de evento de experiência

Junte o desempenho de mídia paga com dados comportamentais no site para entender como as campanhas e os anúncios são associados ao envolvimento do site, às conversões e à receita. Por exemplo, compare os cliques e os gastos da rede de publicidade com os pedidos atribuídos às visitas da mesma campanha.

Para configurar esse relatório, inclua os conjuntos de dados de resumo de mídia paga e o conjunto de dados de evento no site na mesma conexão do Customer Journey Analytics. Capture identificadores estáveis de campanha, anúncio ou ativo suportado de parâmetros de URL da página inicial ou campos de evento existentes. Use campos derivados conforme necessário para analisar e mapear esses valores para os identificadores de mídia paga correspondentes, preservando o contexto de rede e conta necessário. Manter identificadores como cadeias de caracteres. Para associar o evento correspondente e as dimensões de resumo, configure um Grupo de dados de resumo na visualização de dados. Habilitar o canal Mídia paga não configura automaticamente esse rastreamento e mapeamento de URL específico da implementação.


| Opção de rastreamento | Considerações |
|---|---|
| Anúncios do Meta | Configure parâmetros de URL de destino usando identificadores dinâmicos como `campaign.id`, `adset.id` e `ad.id`, onde houver suporte. Capture os valores resolvidos em seu site. Habilitar o conector não adiciona automaticamente esses parâmetros aos URLs de anúncios. |
| Google Ads | |
| Ativos individuais | Os relatórios no nível do ativo de resultados downstream exigem um identificador capturado que mapeia para o ativo específico associado ao clique. Um parâmetro de URL personalizado pode suportar isso quando o formato do anúncio permite o rastreamento específico do ativo. Um identificador de anúncio por si só não pode distinguir vários ativos em um anúncio, e um parâmetro de ativo estático aplicado a um anúncio de vários ativos inteiro não identifica qual ativo foi associado ao clique. |

No Analysis Workspace, use as métricas do **[!UICONTROL Resumo de anúncios]** para comparações de campanhas ou anúncios e as métricas do **[!UICONTROL Resumo de ativos]** para comparações de ativos com suporte. Aplique um modelo de atribuição e uma janela de retrospectiva às métricas de conversão no site que refletem sua pergunta de relatório.

Observe que:

* Os dados de mídia paga são dados de resumo agregados sem uma ID de pessoa. O comportamento no local são os dados do evento.
* O agrupamento de dimensões correspondentes permite a geração de relatórios nessas fontes, mas não corresponde conversões de anúncios individuais de rede para conversões de site nem executa a compilação em nível de pessoa.
* A comparação mostra uma associação, não um aumento causal.
* Os resultados podem diferir devido às definições de conversão, janelas de atribuição, conversões de view-through ou modeladas, consentimento e datas ou fusos horários dos relatórios.
* Valide a origem de visitas com tags de campanha quando os parâmetros de rastreamento forem reutilizados em canais.


#### Comparar o desempenho da campanha com pedidos no local

Um URL de página de aterrissagem pode conter vários parâmetros de rastreamento. Neste exemplo, a ID da campanha em `utm_id` é usada para comparar os gastos da campanha com os pedidos de sites.

https://www.example.com/offer?utm_source=facebook&utm_medium=paid_social&utm_campaign=autumn_offer&utm_id=120218706543980215

O parâmetro usado para esta comparação: `utm_id=120218706543980215`. Os outros parâmetros descrevem a origem, o meio e o rótulo da campanha, mas não são usados como um campo correspondente usado neste exemplo.

Se o URL for capturado nos dados do evento do site, o conjunto de dados do evento do site e os conjuntos de dados de mídia paga farão parte da mesma conexão do Customer Journey Analytics:

1. Identifique a campanha. Use um campo derivado para ler `utm_id` da URL e mapear o valor para o identificador de campanha correspondente nos dados de mídia paga.
1. Agrupe as dimensões correspondentes. Na visualização de dados, adicione a dimensão de campanha do site à dimensão de campanha paga `Summary Data Group`, preservando todos os membros existentes.
1. Comparar gastos e pedidos. No Analysis Workspace, use a dimensão de campanha agrupada como as linhas de uma tabela de forma livre. Adicione o gasto de `Ad Summary` e o site `Orders` como colunas. Defina o modelo de atribuição e a janela de retrospectiva para `Orders`.


A tabela de forma livre mostra os gastos da rede de anúncios junto com os pedidos do site atribuídos a cada campanha. Duas campanhas com gastos de anúncio semelhantes têm números diferentes de ações downstream atribuídas do site. Use essa comparação para identificar campanhas e experiências de página de aterrissagem para investigação ou testes adicionais, em vez de avaliar o desempenho somente com base nas métricas de publicidade.

O exemplo usa uma ID de campanha, mas a mesma abordagem pode usar grupos de anúncios, anúncios ou identificadores de ativos quando valores correspondentes podem ser capturados. Os atributos do Content Analytics, como **[!UICONTROL Cores de primeiro plano do ativo]**, permitem comparar as características criativas com o desempenho da mídia paga. Com o rastreamento específico do ativo e as dimensões de atributo de correspondência configuradas em ambas as fontes, é possível estender essa comparação para pedidos de sites atribuídos e usar os resultados para orientar testes criativos.

#### Combinar o desempenho dos ativos com os dados da Web

Se quiser relatar e analisar o desempenho do ativo relacionado aos investimentos em mídia paga, considere adicionar um parâmetro UTM de ativo específico na configuração de mídia paga da rede de anúncios. Por exemplo, além dos parâmetros dinâmicos padrão como s`ite_source_name`, `campaign.id`, `adset.id` ou `placement`, adicione parâmetros estáticos personalizados, como `aca_asset_id=999999`.

Esse parâmetro personalizado é adicionado ao URL da página inicial. Por exemplo: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&amp;aca_id_2=8888888&amp;utm_medium=paid&amp;utm_source=fb&amp;utm_id=120241705099830539&amp;utm_term=120241705099840539&amp;utm_campaign=120241705099830539

Agora você tem uma relação entre um ativo em uma página e seus dados de mídia paga. Use essa relação no Analysis Workspace para ver como os metadados de ativos do Content Analytics (por exemplo, **[!UICONTROL Cores de primeiro plano do ativo]**) contribuem para o sucesso da campanha de mídia paga.
