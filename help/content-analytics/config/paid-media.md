---
title: Configuração automática de mídia paga do Content Analytics
description: Saiba mais sobre a configuração automática de conjuntos de dados, conexão, visualizações de dados e muito mais.
solution: Customer Journey Analytics
feature: Content Analytics
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '2502'
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

A ilustração abaixo mostra como os conjuntos de dados de resumo são gerados ao habilitar o canal de mídia paga no Content Analytics para uma ou mais de suas redes de anúncios. As APIs relevantes das redes de anúncios disponíveis são usadas para baixar e transformar dados de experiências, ativos e anúncios em possivelmente seis conjuntos de dados de resumo.

![Geração de mídia paga de conjuntos de dados de resumo](/help/content-analytics/assets/paid-media-generation-of-datasets.png)

A rede de anúncios específica determina quais conjuntos de dados de resumo são criados. Nem toda rede de anúncios, para a qual você configurou um conector de origem, gera todos os seis conjuntos de dados de resumo possíveis. Consulte a tabela abaixo para obter uma visão geral dos conjuntos de dados de resumo com as seguintes informações:

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


* O que cada linha em um conjunto de dados de resumo representa.

| Conjunto de dados de resumo<br/>Tipo de evento<br/>Sufixo do componente | Detalhamento de Entidade<br/> | ![MetaMulti](/help/assets/icons2/MetaSolid.svg) | ![GoogleAdsMulti](/help/assets/icons2/GoogleAdsMulti.svg) | ![PinterestMulti](/help/assets/icons2/PinterestMulti.svg) | ![Snapchat](/help/assets/icons2/Snapchat.svg) | ![TikTok](/help/assets/icons2/TikTok.svg) | Cada linha representa |
|---|---|:---:|:---:|:---:|:---:|:---:|---|
| `paidmedia_ad_summary` <br/> `ad.summary`<br/>`\| Ad Summary` | Anúncio<br/>nenhum | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio sem detalhamentos demográficos ou geográficos. |
| `paidmedia_ad_demographics` <br/> `ad.demographics`<br/>`\| Ad Demo` | Anúncio<br/>idade, gênero | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio<br/>dividido por idade e sexo. |
| `paidmedia_ad_geography` <br/> `ad.geography`<br/>`\| Ad Geo` | Ad<br/>país, região | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | O desempenho diário de um anúncio<br/>dividido por país e região. |
| `paidmedia_experience_placement` <br/> `ad.experience.placement`<br>`\| Experience Placement` | Experience<br>platform, position | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário associado<br/>à experiência criativa de um anúncio,<br/>detalhado por plataforma e posição. |
| `paidmedia_asset_summary` <br/>`ad.asset.summary`<br/>`\| Asset Summary` | Ativo<br/>nenhum | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | Desempenho diário no nível do ativo<br/>em seu contexto de anúncio/campanha<br/>sem detalhamento demográfico ou geográfico. |
| `paidmedia_assets_demographics` <br/> `ad.asset.demographics`<br/>`\| Asset Demo` | Ativo<br/>idade, gênero | ![Marca de seleção](/help/assets/icons2/Checkmark.svg) | | | | | Desempenho diário no nível do ativo<br/>em seu contexto de anúncio/campanha<br/>detalhado por idade e sexo. |

Essa tabela descreve a cobertura do conjunto de dados, não uma garantia de que uma rede específica preencha cada métrica ou campo de metadados. Verifique os campos necessários para a análise. Um campo indisponível ou um detalhamento não compatível não é o mesmo que um valor zero medido para um campo.

O agrupamento de dados de resumo reúne dimensões equivalentes; o agrupamento não totaliza os seis totais de métricas de desempenho.

## Conjuntos de dados de pesquisa

Conjuntos de dados de pesquisa separados descrevem Conta, Campanha, Grupo de publicidade, Anúncio, Experiência e Ativo. Eles fornecem nomes e metadados usando GUIDs de entidade. Não existe emparelhamento um para um entre os conjuntos de dados de resumo e os seis conjuntos de dados de pesquisa.

Os conjuntos de dados de pesquisa compartilham dois blocos de construção comuns:

* **Objeto de IDs de entidade**: armazena objetos de conta, anúncio, grupo de anúncios, ativo, campanha e experiência. Cada objeto contém uma chave global gerada pela Adobe e uma ID nativa da plataforma.
* **Metadados principais de mídia paga**: armazena campos descritivos comuns, como nome, status, objetivo, meta de otimização, estratégia de licitação, tipo de orçamento, valores de orçamento, moeda, fuso horário, status de veiculação, datas, rede de anúncios, canal, caminho de hierarquia, rede e identificadores de portfólio.

| Conjunto de dados de pesquisa | Conteúdo principal |
|---|---|
| Pesquisa de conta | Metadados a nível de conta, como nome, moeda, fuso horário, status, limite de gastos e datas de criação |
| Pesquisa de campanha | Configurações de campanha para orçamento, agendamento, direcionamento, rastreamento de conversão, atribuição, posicionamentos, objetos promovidos, objetivo e IDs de catálogo ou armazenamento |
| Pesquisa de grupo de anúncios | Metadados do grupo de anúncios, como vinculação de campanha, status, orçamento, metas de otimização e direcionamento |
| Pesquisa de anúncio | Adicionar detalhes criativos, como ativos, variantes, dimensões, URLs de rastreamento, call to action, corpo de texto, títulos, URL de destino, status do delivery e status de revisão |
| Pesquisa de ativo | Propriedades de ativos, como dimensões, detalhes do arquivo, propriedades de imagem, URLs de mídia, metadados de uso, metadados de vídeo, descrição, subtipo, título e tipo |
| Pesquisa de experiência | Agrupamentos criativos de nível de experiência, como ID de experiência, ativos, título, descrição e call to action |


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

Cada componente de métrica de cliques serve a um contexto de relatório diferente. Não é possível totalizar esses componentes de métrica em um total geral. A mesma atividade publicitária subjacente pode ser representada em mais de um conjunto de dados de resumo.

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
| Gastos | Resumo do anúncio |
| Índice de click-through | Geografia do anúncio |
| Custo por clique | Resumo do anúncio |


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

1. Identifique a campanha. Use um campo derivado para ler `utm_id` da URL e mapear seu valor para o identificador de campanha correspondente nos dados de mídia paga.
1. Agrupe as dimensões correspondentes. Na visualização de dados, adicione a dimensão de campanha do site à dimensão de campanha paga `Summary Data Group`, preservando todos os membros existentes.
1. Comparar gastos e pedidos. No Analysis Workspace, use a dimensão de campanha agrupada como as linhas de uma tabela de forma livre. Adicione o gasto de `Ad Summary` e o site `Orders` como colunas. Defina o modelo de atribuição e a janela de retrospectiva para `Orders`.


A tabela de forma livre mostra os gastos da rede de anúncios junto com os pedidos do site atribuídos a cada campanha. Duas campanhas com gastos de anúncio semelhantes têm números diferentes de ações downstream atribuídas do site. Use essa comparação para identificar campanhas e experiências de página de aterrissagem para investigação ou testes adicionais, em vez de avaliar o desempenho somente com base nas métricas de publicidade.

O exemplo usa uma ID de campanha, mas a mesma abordagem pode usar grupos de anúncios, anúncios ou identificadores de ativos quando valores correspondentes podem ser capturados. Os atributos do Content Analytics, como **[!UICONTROL Cores de primeiro plano do ativo]**, permitem comparar as características criativas com o desempenho da mídia paga. Com o rastreamento específico do ativo e as dimensões de atributo de correspondência configuradas em ambas as fontes, é possível estender essa comparação para pedidos de sites atribuídos e usar os resultados para orientar testes criativos.

#### Combinar o desempenho dos ativos com os dados da Web

Se quiser relatar e analisar o desempenho do ativo relacionado aos investimentos em mídia paga, considere adicionar um parâmetro UTM de ativo específico na configuração de mídia paga da rede de anúncios. Por exemplo, além dos parâmetros dinâmicos padrão como s`ite_source_name`, `campaign.id`, `adset.id` ou `placement`, adicione parâmetros estáticos personalizados, como `aca_asset_id=999999`.

Esse parâmetro personalizado é adicionado ao URL da página inicial. Por exemplo: https://www.example.com/home.html?utm_content=120241705099850539%2Caca_asset_id%3D9999999%2Caca_placement%3DFacebook_Desktop_Feed&aca_id_2=8888888&utm_medium=paid&utm_source=fb&utm_id=120241705099830539&utm_term=120241705099840539&utm_campaign=120241705099830539

Agora você tem uma relação entre um ativo em uma página e seus dados de mídia paga. Use essa relação no Analysis Workspace para ver como os metadados de ativos do Content Analytics (por exemplo, **[!UICONTROL Cores de primeiro plano do ativo]**) contribuem para o sucesso da campanha de mídia paga.


<!--

Do we need to include the tables from the Wiki?

## Reference

The following table lists paid media fields, their XDM paths, provisioned components, and reporting visibility.

+++ Paid media fields

| Field name | XDM path | ACA Paid Media component | Provisioning status | Reporting visibility |
| --- | --- | --- | --- | --- |
| Ad Network | `paidMedia.adNetwork` | Ad Network (dimension) | existing | visible through shared grouping: Ad Network |
| Channel | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | existing | visible through shared grouping: Content Channel |
| Account GUID | `paidMedia.accountGUID` | Account GUID (dimension) | existing | visible through shared grouping: Account GUID |
| Campaign GUID | `paidMedia.campaignGUID` | Campaign GUID (dimension) | existing | visible through shared grouping: Campaign GUID |
| Ad Group GUID | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | existing | visible through shared grouping: AdGroup GUID |
| Ad GUID | `paidMedia.adGUID` | Ad GUID (dimension) | existing | visible through shared grouping: Ad GUID |
| Experience GUID | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | existing | visible through shared grouping: Experience Id |
| Asset GUID | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | existing | visible through shared grouping: Asset Id |
| Name | `paidMedia.metadata.name` | Ad Name (derived field)<br/>Ad Name (shared dimension)<br/>AdGroup Name (derived field)<br/>AdGroup Name (shared dimension)<br/>Asset Name (Paid Media) (derived field)<br/>Asset Name (Paid Media) (shared dimension)<br/>Campaign Name (derived field)<br/>Campaign Name (shared dimension)<br/>Experience Name (derived field)<br/>Experience Name (shared dimension) | existing | visible through shared grouping: Ad Name, AdGroup Name, Asset Name (Paid Media), Campaign Name, Experience Name |
| Status | `paidMedia.metadata.status` | Ad Status (derived field)<br/>Ad Status (shared dimension)<br/>Ad Group Status (derived field)<br/>Ad Group Status (shared dimension)<br/>Campaign Status (derived field)<br/>Campaign Status (shared dimension) | curated net-new | visible through shared grouping: Ad Status, Ad Group Status, Campaign Status |
| Serving Status | `paidMedia.metadata.servingStatus` | | excluded | missing provisioned component |
| Updated Time | `paidMedia.metadata.updatedTime` | | excluded | missing provisioned component |
| Account Name | `paidMedia.accountDetails.accountName` | Account Name (derived field)<br/>Account Name (shared dimension) | existing | visible through shared grouping: Account Name |
| Currency | `paidMedia.accountDetails.currency` | Account Currency (derived field)<br/>Account Currency (shared dimension) | curated net-new | visible through shared grouping: Account Currency |
| Timezone | `paidMedia.accountDetails.timezone` | Account Timezone (derived field)<br/>Account Timezone (shared dimension) | curated net-new | visible through shared grouping: Account Timezone |
| Account Type | `paidMedia.accountDetails.accountType` | Account Type (derived field)<br/>Account Type (shared dimension) | curated net-new | visible through shared grouping: Account Type |
| Business Name | `paidMedia.accountDetails.businessName` | Account Business Name (derived field)<br/>Account Business Name (shared dimension) | curated net-new | visible through shared grouping: Account Business Name |
| Campaign Type | `paidMedia.campaignDetails.campaignType` | Campaign Type (derived field)<br/>Campaign Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Type |
| Objective | `paidMedia.campaignDetails.objective` | Campaign Objective (derived field)<br/>Campaign Objective (shared dimension) | curated net-new | visible through shared grouping: Campaign Objective |
| Is Automated Campaign | `paidMedia.campaignDetails.isAutomatedCampaign` | Campaign Is Automated \| Ad Summary (derived field) | curated net-new | hidden |
| Bid Strategy | `paidMedia.campaignDetails.budgetSettings.bidStrategy` | Campaign Bid Strategy (derived field)<br/>Campaign Bid Strategy (shared dimension) | curated net-new | visible through shared grouping: Campaign Bid Strategy |
| Budget Type | `paidMedia.campaignDetails.budgetSettings.budgetType` | Campaign Budget Type (derived field)<br/>Campaign Budget Type (shared dimension) | curated net-new | visible through shared grouping: Campaign Budget Type |
| Daily Budget | `paidMedia.campaignDetails.budgetSettings.dailyBudget` | Campaign Daily Budget (derived field)<br/>Campaign Daily Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Daily Budget |
| Lifetime Budget | `paidMedia.campaignDetails.budgetSettings.lifetimeBudget` | Campaign Lifetime Budget (derived field)<br/>Campaign Lifetime Budget (shared dimension) | curated net-new | visible through shared grouping: Campaign Lifetime Budget |
| Campaign Budget Optimization | `paidMedia.campaignDetails.budgetSettings.isCampaignBudgetOptimization` | Campaign Budget Optimization \| Ad Summary (derived field) | curated net-new | hidden |
| Catalog ID | `paidMedia.campaignDetails.catalogId` | Campaign Catalog ID \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.campaignDetails.startTime` | Campaign Start Time (derived field)<br/>Campaign Start Time (shared dimension) | curated net-new | visible through shared grouping: Campaign Start Time |
| End Time | `paidMedia.campaignDetails.endTime` | Campaign End Time (derived field)<br/>Campaign End Time (shared dimension) | curated net-new | visible through shared grouping: Campaign End Time |
| Ad Group Type | `paidMedia.adGroupDetails.adGroupType` | Ad Group Type (derived field)<br/>Ad Group Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Type |
| Bid Strategy Type | `paidMedia.adGroupDetails.budgetSettings.bidStrategyType` | Ad Group Bid Strategy Type (derived field)<br/>Ad Group Bid Strategy Type (shared dimension) | curated net-new | visible through shared grouping: Ad Group Bid Strategy Type |
| Optimization Goal | `paidMedia.adGroupDetails.optimizationSettings.optimizationGoal` | Ad Group Optimization Goal (derived field)<br/>Ad Group Optimization Goal (shared dimension) | curated net-new | visible through shared grouping: Ad Group Optimization Goal |
| Delivery Status | `paidMedia.adGroupDetails.deliverySettings.deliveryStatus` | Ad Group Delivery Status \| Ad Summary (derived field) | curated net-new | hidden |
| Start Time | `paidMedia.adGroupDetails.startTime` | Ad Group Start Time (derived field)<br/>Ad Group Start Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group Start Time |
| End Time | `paidMedia.adGroupDetails.endTime` | Ad Group End Time (derived field)<br/>Ad Group End Time (shared dimension) | curated net-new | visible through shared grouping: Ad Group End Time |
| Ad Type | `paidMedia.adDetails.adType` | Ad Type (derived field)<br/>Ad Type (shared dimension) | curated net-new | visible through shared grouping: Ad Type |
| Delivery Status | `paidMedia.adDetails.deliveryStatus` | Ad Delivery Status (derived field)<br/>Ad Delivery Status (shared dimension) | curated net-new | visible through shared grouping: Ad Delivery Status |
| Review Status | `paidMedia.adDetails.reviewStatus` | Ad Review Status (derived field)<br/>Ad Review Status (shared dimension) | curated net-new | visible through shared grouping: Ad Review Status |
| Creative Type | `paidMedia.adDetails.creative.paidMediaCreative.creativeType` | Ad Creative Type (derived field)<br/>Ad Creative Type (shared dimension) | curated net-new | visible through shared grouping: Ad Creative Type |
| Title | `paidMedia.adDetails.creative.paidMediaCreative.title` | Ad Title (derived field)<br/>Ad Title (shared dimension) | curated net-new | visible through shared grouping: Ad Title |
| Call to Action | `paidMedia.adDetails.creative.paidMediaCreative.callToAction` | Ad Call to Action (derived field)<br/>Ad Call to Action (shared dimension) | curated net-new | visible through shared grouping: Ad Call to Action |
| Destination URL | `paidMedia.adDetails.creative.paidMediaCreative.destinationURL` | Ad Destination URL (derived field)<br/>Ad Destination URL (shared dimension) | curated net-new | visible through shared grouping: Ad Destination URL |
| Display URL | `paidMedia.adDetails.creative.paidMediaCreative.displayURL` | Ad Display URL (derived field)<br/>Ad Display URL (shared dimension) | curated net-new | visible through shared grouping: Ad Display URL |
| Experience Type | `paidMedia.experienceDetails.experienceType` | Experience Type (derived field)<br/>Experience Type (shared dimension) | curated net-new | visible through shared grouping: Experience Type |
| Landing Page URL | `paidMedia.experienceDetails.landingPageURL` | Experience Landing Page URL (derived field)<br/>Experience Landing Page URL (shared dimension) | curated net-new | visible through shared grouping: Experience Landing Page URL |
| Call To Action | `paidMedia.experienceDetails.callToAction` | Experience Call to Action (derived field)<br/>Experience Call to Action (shared dimension) | curated net-new | visible through shared grouping: Experience Call to Action |
| Card Count | `paidMedia.experienceDetails.carouselProperties.cardCount` | Experience Card Count \| Ad Summary (derived field) | curated net-new | hidden |
| Asset Type | `paidMedia.assetDetails.assetType` | Asset Type (derived field)<br/>Asset Type (shared dimension) | curated net-new | visible through shared grouping: Asset Type |
| Permalink URL | `paidMedia.assetDetails.mediaProperties.permalinkURL` | Asset Permalink URL \| Ad Summary (derived field) | curated net-new | hidden |
| Width | `paidMedia.assetDetails.dimensions.width` | Asset Width (derived field)<br/>Asset Width (shared dimension) | curated net-new | visible through shared grouping: Asset Width |
| Height | `paidMedia.assetDetails.dimensions.height` | Asset Height (derived field)<br/>Asset Height (shared dimension) | curated net-new | visible through shared grouping: Asset Height |
| Aspect Ratio | `paidMedia.assetDetails.dimensions.aspectRatio` | Asset Aspect Ratio (derived field)<br/>Asset Aspect Ratio (shared dimension) | curated net-new | visible through shared grouping: Asset Aspect Ratio |
| Orientation | `paidMedia.assetDetails.dimensions.orientation` | Asset Orientation \| Ad Summary (derived field)<br/>Asset Orientation (shared dimension) | curated net-new | visible through shared grouping: Asset Orientation |
| MIME Type | `paidMedia.assetDetails.fileProperties.mimeType` | Asset MIME Type \| Ad Summary (derived field) | curated net-new | hidden |
| Impressions | `paidMedia.metrics.impressions` | Impressions \| Ad Summary (metric) | existing | visible |
| Clicks | `paidMedia.metrics.clicks` | Clicks \| Ad Summary (metric) | existing | visible |
| Spend | `paidMedia.metrics.spend` | Spend \| Ad Summary (metric) | existing | visible |
| Reach | `paidMedia.metrics.reach` | Reach \| Ad Summary (metric) | curated net-new | visible |
| Conversions | `paidMedia.metrics.conversions` | Conversions \| Ad Summary (metric) | curated net-new | visible |
| Conversion Value | `paidMedia.metrics.conversionValue` | Conversion Value \| Ad Summary (metric) | curated net-new | visible |
| Video Views | `paidMedia.metrics.videoViews` | Video Views \| Ad Summary (metric) | curated net-new | visible |
| Engagements | `paidMedia.metrics.engagements` | Engagements \| Ad Summary (metric) | curated net-new | visible |
| Post-Click Conversions | `paidMedia.conversionMetrics.postClickConversions` | Post-Click Conversions \| Ad Summary (metric) | curated net-new | visible |
| Post-View Conversions | `paidMedia.conversionMetrics.postViewConversions` | Post-View Conversions \| Ad Summary (metric) | curated net-new | visible |
| Purchases | `paidMedia.conversionMetrics.conversionsByType.purchases` | Purchases \| Ad Summary (metric) | curated net-new | visible |
| Add to Cart | `paidMedia.conversionMetrics.conversionsByType.addToCart` | Add to Cart \| Ad Summary (metric) | curated net-new | visible |
| Leads | `paidMedia.conversionMetrics.conversionsByType.leads` | Leads \| Ad Summary (metric) | curated net-new | visible |
| Registrations | `paidMedia.conversionMetrics.conversionsByType.registrations` | Registrations \| Ad Summary (metric) | curated net-new | visible |
| Downloads | `paidMedia.conversionMetrics.conversionsByType.downloads` | Downloads \| Ad Summary (metric) | curated net-new | visible |
| Subscriptions | `paidMedia.conversionMetrics.conversionsByType.subscriptions` | Subscriptions \| Ad Summary (metric) | curated net-new | visible |
| Landing Page View | `paidMedia.conversionMetrics.conversionsByType.landingPageView` | Landing Page Views \| Ad Summary (metric) | curated net-new | visible |
| Total Order Value | `paidMedia.conversionMetrics.totalOrderValue` | Total Order Value \| Ad Summary (metric) | curated net-new | visible |
| Video Plays | `paidMedia.videoMetrics.videoPlays` | Video Plays \| Ad Summary (metric) | curated net-new | visible |
| Video Completions | `paidMedia.videoMetrics.videoCompletions` | Video Completions \| Ad Summary (metric) | curated net-new | visible |
| Link Clicks | `paidMedia.extendedMetrics.linkClicks` | Link Clicks \| Ad Summary (metric) | curated net-new | visible |
| Outbound Clicks | `paidMedia.extendedMetrics.outboundClicks` | Outbound Clicks \| Ad Summary (metric) | curated net-new | visible |
| App Installs | `paidMedia.extendedMetrics.appInstalls` | App Installs \| Ad Summary (metric) | curated net-new | visible |
| Lead Submissions | `paidMedia.extendedMetrics.leadSubmissions` | Lead Submissions \| Ad Summary (metric) | curated net-new | visible |
| Device Type | `paidMedia.dimensionalBreakdowns.deviceType` | | excluded | removed in source range |
| Placement | `paidMedia.dimensionalBreakdowns.placement` | Placement (dimension) | curated net-new | visible through shared grouping: Placement |
| Platform | `paidMedia.dimensionalBreakdowns.platform` | Platform (dimension) | curated net-new | visible through shared grouping: Platform |
| Country | `paidMedia.dimensionalBreakdowns.country` | Country (dimension) | curated net-new | visible through shared grouping: Country |
| Region | `paidMedia.dimensionalBreakdowns.region` | Region (dimension) | curated net-new | visible through shared grouping: Region |
| Other connector-populated fields | See field tables | No named component | excluded | not surfaced |

+++

### Identifiers

| Field name | Description | XDM path | ACA Paid Media component | ACA context label | Meta | Google Ads | Pinterest | Snapchat | TikTok |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Record ID | *Unique record URI, inherited from data/record.* | `@id` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads:{entity}:{ids}`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (pinterest:&lt;entity&gt;: source-derived composite record ID; GUIDs use pinterest_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (snapchat:&lt;entity&gt;: source-derived composite record ID; GUIDs use snapchat_; writer later emits this as _id.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (tiktok:&lt;entity&gt;: source-derived composite record ID; GUIDs use tiktok_; summary IDs omit dimension values; writer emits _id.) |
| Entity Type | The type of paid media entity | `entityType` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) | ⚪ (Fixed entity discriminator per transformer; not a source attribute.) |
| Ad Network | The advertising platform/network | `paidMedia.adNetwork` | Ad Network (dimension) | Ad Network | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads`) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Network | Alias of adNetwork for migration from GenStudio templates | `paidMedia.network` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ⚪ (Fixed routing discriminator (pinterest); not a source attribute.) | ⚪ (Fixed routing discriminator (snapchat); not a source attribute.) | ⚪ (Fixed routing discriminator (tiktok); not a source attribute.) |
| Channel | Content channel indicating the source of the data (e.g., Web, Mobile, PaidMedia). Used as a reporting dimension for cross-channel breakdowns. | `paidMedia.channel` | Content Channel (dimension)<br/>Content Channel (shared dimension) | Content Channel (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`PaidMedia`) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) | ⚪ (Fixed routing discriminator (PaidMedia); not a source attribute.) |
| Hierarchy Path | Full hierarchical path showing parent-child relationships (e.g., account_id/campaign_id/adgroup_id/ad_id) | `paidMedia.hierarchyPath` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account ID | Unique identifier for the ad account within the network | `paidMedia.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Unique identifier for the ad account across all networks | `paidMedia.accountGUID` | Account GUID (dimension) | Account Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`meta_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`google_ads_` prefix) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign ID | Unique identifier for the campaign within the network | `paidMedia.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Campaign GUID | Unique identifier for the campaign across all networks | `paidMedia.campaignGUID` | Campaign GUID (dimension) | Campaign Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group ID | Unique identifier for the ad group/ad set/ad squad within the network | `paidMedia.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad Group GUID | Unique identifier for the ad group/ad set/ad squad across all networks | `paidMedia.adGroupGUID` | AdGroup GUID (dimension) | AdGroup Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad ID | Unique identifier for the individual ad within the network | `paidMedia.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Ad GUID | Unique identifier for the individual ad across all networks | `paidMedia.adGUID` | Ad GUID (dimension) | Ad Id | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Experience ID | Unique identifier for creative experience (multi-asset compositions) within the network | `paidMedia.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Ad ID on Experience lookup and summaries; null on Ad lookup; asset reverse join recovers ad ID when metadata matches.) |
| Experience GUID | Unique identifier for creative experience (multi-asset compositions) across all networks | `paidMedia.experienceGUID` | Experience GUID \| Ad Summary (dimension)<br/>Experience Id (shared dimension) | Experience Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset ID | Unique identifier for creative assets (images, videos, etc.) within the network | `paidMedia.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Asset GUID | Unique identifier for creative assets (images, videos, etc.) across all networks | `paidMedia.assetGUID` | Asset GUID \| Ad Summary (dimension)<br/>Asset Id (shared dimension) | Asset Id (shared component only) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived ID/GUID; union across lookup entities and surviving summaries; nonapplicable entities null.) |
| Account GUID | Account GUID (class entityIDs hierarchy) | `entityIDs.account.accountGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Account ID | Account ID (class entityIDs hierarchy) | `entityIDs.account.accountID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign GUID | Campaign GUID (class entityIDs hierarchy) | `entityIDs.campaign.campaignGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Campaign ID | Campaign ID (class entityIDs hierarchy) | `entityIDs.campaign.campaignID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group GUID | Ad Group GUID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group ID | Ad Group ID (class entityIDs hierarchy) | `entityIDs.adGroup.adGroupID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad GUID | Ad GUID (class entityIDs hierarchy) | `entityIDs.ad.adGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad ID | Ad ID (class entityIDs hierarchy) | `entityIDs.ad.adID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience GUID | Experience GUID (class entityIDs hierarchy) | `entityIDs.experience.experienceGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Experience ID | Experience ID (class entityIDs hierarchy) | `entityIDs.experience.experienceID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset GUID | Asset GUID (class entityIDs hierarchy) | `entityIDs.asset.assetGUID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Asset ID | Asset ID (class entityIDs hierarchy) | `entityIDs.asset.assetID` | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) | ![Checkmark](/help/assets/icons2/CheckMark.svg) (Source-derived on applicable lookup entities; shared ID/GUID pair; other entity rows null.) |
| Ad Group Name | Display name of the ad group/ad set/ad squad. Mirrors metadata.name from the ad group lookup. | `paidMedia.denormalizedNames.adGroupName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad group name"))`) | | |
| Ad Name | Display name of the individual ad. Mirrors metadata.name from the ad lookup. | `paidMedia.denormalizedNames.adName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Ad name"))`) | | |
| Campaign Name | Display name of the campaign. Mirrors metadata.name from the campaign lookup. | `paidMedia.denormalizedNames.campaignName` | | | | | ![Checkmark](/help/assets/icons2/CheckMark.svg) (`nullIfZero(str(df, "Campaign name"))`) | | |

-->
