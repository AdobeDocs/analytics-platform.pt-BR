---
title: Relatórios do GA4 no Customer Journey Analytics
description: Encontre o equivalente do Customer Journey Analytics para cada seção de relatório do GA4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Relatórios do GA4 no Customer Journey Analytics

Use esta página como uma referência de pesquisa quando você souber em qual relatório do GA4 está olhando e quiser recriar seu equivalente aproximado no Analysis Workspace. Os relatórios são organizados pelas seções de navegação do GA4. Para ver cenários avançados de relatórios entre canais que ficam disponíveis após a migração dos dados do GA para o Customer Journey Analytics, consulte [Relatórios sobre dados do Google Analytics](/help/use-cases/third-party/ga/report.md).

## Tempo real

+++Tempo real

O relatório em tempo real do GA4 mostra a atividade dos últimos 30 minutos: usuários ativos, eventos que disparam, onde usuários estão, o que está direcionando o tráfego e em quais páginas eles estão.

O Customer Journey Analytics não tem uma área de relatório em tempo real separada. Em vez disso, crie um painel no Analysis Workspace e habilite a opção **[!UICONTROL Atualização em tempo real]** (parte do pacote **Ultimate**) para que suas visualizações sejam atualizadas a cada minuto:

1. Crie um painel de [Forma livre](/help/analysis-workspace/c-panels/freeform-panel.md) (o botão de alternância também funciona nos painéis [Em branco](/help/analysis-workspace/c-panels/blank-panel.md), [Atribuição](/help/analysis-workspace/c-panels/attribution.md) e [Item seguinte ou anterior](/help/analysis-workspace/c-panels/next-previous.md)) com as dimensões e métricas que você deseja monitorar. Para espelhar os cartões em tempo real do GA4, use **[!UICONTROL Página]**, **[!UICONTROL Tipo de evento]**, **[!UICONTROL Domínio de Referência]** ou **[!UICONTROL Países]** como a dimensão, com **[!UICONTROL Sessões]** como a métrica.
2. Habilite a opção de alternância **[!UICONTROL Atualização em tempo real]** e escolha um período entre **[!UICONTROL Últimos 15 minutos]** e **[!UICONTROL Últimas 24 horas]**. Os dados são limitados a uma janela contínua de 24 horas, e o painel é atualizado a cada minuto por até 30 minutos.

Os relatórios em tempo real favorecem dados de nível de evento e sessão e não podem usar a compilação, portanto, prefira **[!UICONTROL Sessões]** a **[!UICONTROL Pessoas]**. Consulte [Usar relatórios em tempo real](/help/components/real-time/use-real-time.md) para obter o procedimento completo e [Visão geral dos relatórios em tempo real](/help/components/real-time/real-time.md) para obter detalhes sobre direitos e latência.

+++

## Aquisição

+++Aquisição de usuário (primeiro contato)

O relatório de aquisição de usuários do GA4 atribui cada usuário ao canal, fonte e mídia que os trouxe para o site pela primeira vez, usando a atribuição de primeiro toque.

No Analysis Workspace, aplique um modelo de atribuição **[!UICONTROL Primeiro contato]** à dimensão **[!UICONTROL Canal de marketing]**. Os Canais de marketing devem ser configurados antes do uso. Consulte [Criar um campo derivado de canal de marketing](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md).

1. Arraste a dimensão **[!UICONTROL Canal de marketing]** para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Clique com o botão direito do mouse em um cabeçalho de coluna de métrica e selecione **[!UICONTROL Usar modelo de atribuição não padrão]**.
3. Selecione **[!UICONTROL Primeiro contato]** com uma janela de retrospectiva apropriada para sua análise.

Como alternativa, use o [[!UICONTROL painel Atribuição]](/help/analysis-workspace/c-panels/attribution.md) para obter uma comparação lado a lado entre o desempenho do canal de primeiro e último toque.

+++

+++Aquisição de tráfego (com base em sessão)

O relatório de aquisição de tráfego do GA4 atribui cada sessão ao canal, origem e mídia que a iniciou, usando atribuição baseada em sessão. Você pode detalhá-lo por grupo de canais padrão, origem/meio, referenciador ou campanha.

No Analysis Workspace, a dimensão **[!UICONTROL Canal de marketing]** com o modelo de atribuição padrão **[!UICONTROL Último contato]** fornece relatórios de canal baseados em sessão:

1. Arraste a dimensão **[!UICONTROL Canal de marketing]** para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Arraste as métricas desejadas junto com a métrica padrão **[!UICONTROL Eventos]**.

Os detalhamentos do GA4 são mapeados para essas dimensões do Customer Journey Analytics:

* **Canal**: **[!UICONTROL Canal de marketing]**. O Customer Journey Analytics não tem agrupamentos de canais incorporados — defina-os como um [campo derivado](/help/data-views/derived-fields/derived-fields.md) usando o modelo de função **[!UICONTROL canais de marketing]** ou regras de transporte do Adobe Analytics ao usar o conector de origem do Analytics (consulte [Usar dimensões do canal de marketing](/help/use-cases/aa-data/marketing-channels.md)).
* **Source / médio e referências**: **[!UICONTROL Domínio de Referência]** e **[!UICONTROL Tipo de Referenciador]**.
* **Campanha**: os parâmetros `utm_*` do GA4 não são coletados automaticamente — cada um deve ser mapeado para um campo XDM durante a implementação antes de aparecer como uma dimensão. Se os valores da campanha chegarem como um código de rastreamento, use a dimensão **[!UICONTROL Código de rastreamento]**.

+++

+++Caminhos de atribuição e conversão

Os relatórios de atribuição do GA4 (no Advertising) mostram como canais diferentes contribuem para conversões e permitem comparação de modelo e análise de caminho de conversão.

No Analysis Workspace, use o [[!UICONTROL painel Atribuição]](/help/analysis-workspace/c-panels/attribution.md):

1. Selecione o ícone Painéis e arraste um painel **[!UICONTROL Atribuição]** para a tela.
2. Arraste a dimensão **[!UICONTROL Canal de marketing]** para a caixa **[!UICONTROL Adicionar Dimension]**.
3. Arraste a sua métrica de conversão (por exemplo, um evento de compra) para a caixa **[!UICONTROL Adicionar métrica]**.
4. Selecione **[!UICONTROL Criar]**.

O [!UICONTROL Painel de atribuição] produz uma tabela de comparação de modelo e uma visualização de [!UICONTROL Fluxo de canal] mostrando os principais caminhos que os visitantes tomaram antes da conversão. Selecione **[!UICONTROL Adicionar modelo]** para comparar vários modelos de atribuição simultaneamente.

+++

## Engajamento

+++Páginas e telas

O relatório Páginas e telas do GA4 mostra as métricas de desempenho para páginas individuais e telas de aplicativos.

No Analysis Workspace, arraste a dimensão **[!UICONTROL Página]** para uma [[!UICONTROL tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) e adicione suas métricas desejadas. Métricas comuns incluem **[!UICONTROL Sessões]**, **[!UICONTROL Pessoas]**, **[!UICONTROL Taxa de Rejeição]** e **[!UICONTROL Tempo gasto por sessão]**.

Para agrupar páginas por estrutura de caminho de URL (por exemplo, `/blog/` ou `/products/`), use a dimensão **[!UICONTROL Seção do site]** se sua implementação a definir ou crie um [campo derivado](/help/data-views/derived-fields/derived-fields.md) que analise o URL da página com a função **[!UICONTROL Análise de URL]**. Se você manter um mapeamento explícito de página para seção, um [conjunto de dados de pesquisa](/help/connections/standard-lookups.md) poderá fornecer o agrupamento.

+++

+++Páginas de destino

O relatório de Landing page do GA4 mostra em quais páginas os usuários chegam quando iniciam uma sessão.

No Analysis Workspace, arraste a dimensão **[!UICONTROL Página de entrada]** para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). **[!UICONTROL Sessões]** é a métrica mais relevante para essa dimensão.

+++

+++Eventos

O relatório Eventos do GA4 mostra quantas vezes cada evento foi acionado com métricas no nível do evento.

No GA4, os eventos têm um nome e parâmetros opcionais (por exemplo, evento `video_play` com parâmetro `video_title`). No Customer Journey Analytics, a dimensão padrão do nome do evento é **[!UICONTROL Tipo de evento]** (originado de `xdm.eventType`). Os parâmetros de evento são mapeados para outros campos XDM, cujos nomes dependem da implementação.

Arraste a dimensão **[!UICONTROL Tipo de evento]** para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) para listar todos os tipos de evento, junto com a métrica **[!UICONTROL Eventos]**.

+++

+++Eventos principais (conversões)

O relatório de Eventos principais do GA4 (anteriormente Conversões) lista cada evento principal por nome com sua contagem — eventos sinalizados como críticos para os negócios na configuração de propriedade do GA4.

O Customer Journey Analytics não tem um sinalizador &quot;evento principal&quot;. Cada interação é um evento, portanto, não há uma lista predefinida de conversões a serem abertas.

Para recriar a lista de conversões do GA4 por nome, use **segmentos como linhas**. Uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) não pode colocar uma métrica na posição da linha, mas pode colocar um segmento lá:

1. Para cada conversão, crie um segmento que isole seus eventos, por exemplo, um segmento com escopo de evento em que `xdm.eventType` é igual a `commerce.purchases`. Nomeie cada segmento após a conversão que ele representa (por exemplo, **Compras**).
2. Arraste cada segmento de conversão para a área de linha de uma [!UICONTROL tabela de forma livre], uma por linha.
3. Adicione a métrica **[!UICONTROL Eventos]** como coluna. Cada linha mostra a contagem dessa conversão, espelhando a lista de eventos-chave do GA4. Em vez disso, use **[!UICONTROL Pessoas]** para contar conversores exclusivos.

Para adicionar uma taxa de conversão, crie uma métrica calculada (selecione o ícone **+** próximo à lista de métricas) definida como uma métrica de conversão dividida por **[!UICONTROL Sessões]** ou **[!UICONTROL Pessoas]**.

Cada conversão isolada aqui também pode ser definida como uma métrica reutilizável na visualização de dados. Consulte a entrada **Eventos-chave → Métricas de evento personalizadas** em [Métricas comuns](#common-metrics) para saber como configurar isso.

+++

## Monetização

+++Compras de comércio eletrônico

O relatório de compras de comércio eletrônico do GA4 mostra dados de compra no nível do produto, incluindo itens, receita e quantidade.

No Customer Journey Analytics, o relatório de comércio eletrônico usa a dimensão **[!UICONTROL Produto]** junto com as métricas de compra. Este relatório exige que sua implementação envie dados de comércio XDM (como `xdm.commerce.purchases`, `xdm.commerce.order` e `xdm.productListItems`).

1. Arraste a dimensão **[!UICONTROL Produto]** para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
2. Arraste métricas de comércio eletrônico como **[!UICONTROL Pedidos]**, **[!UICONTROL Receita]** e **[!UICONTROL Unidades]** juntamente com a métrica padrão **[!UICONTROL Eventos]**.

+++

+++Jornada de compra (funnel)

O relatório de jornada de compra do GA4 mostra como os usuários se movem pelo seu funnel de compras — por exemplo, de adicionar ao carrinho para iniciar o check-out para comprar — e onde eles caem.

No Analysis Workspace, use a visualização [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Selecione o ícone Visualizações e arraste uma visualização **[!UICONTROL Fallout]** para a tela.
2. Localize a dimensão **[!UICONTROL Página]** e expanda-a para revelar valores de página individuais.
3. Arraste a primeira etapa do funnel (por exemplo, uma página de produto) para o primeiro slot **[!UICONTROL Adicionar ponto de contato]**.
4. Continue adicionando pontos de contato para cada etapa.

A visualização Fallout aceita qualquer dimensão, métrica ou segmento como um ponto de contato, não apenas páginas, portanto, corresponde aos funis baseados em eventos do GA4 e se estende a sequências que misturam eventos, páginas e segmentos.

+++

+++Promoções

O relatório de Promoções do GA4 mostra como as promoções internas (banners, disposições em destaque) impulsionam as interações do produto.

No Customer Journey Analytics, os dados de promoção exigem a captura de impressões promocionais e cliques em campos de esquema XDM. Depois de coletada, crie uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) que inclua a dimensão do nome da promoção com métricas de impressão e clique. Trabalhe com o administrador do Customer Journey Analytics para confirmar quais dados de promoção estão disponíveis em sua visualização de dados.

+++

+++Anúncios do editor

O relatório Anúncios do editor do GA4 mostra a receita de anúncios do Google Ad Manager ou do AdMob para propriedades monetizadas pelo editor.

O Customer Journey Analytics não tem integração nativa de receita de anúncios de editores. Para relatar esses dados, assimile os números de receita da sua plataforma de monetização de anúncios (como o Google Ad Manager ou AdMob) na Adobe Experience Platform como um conjunto de dados, usando um conector de origem ou assimilação direta de dados. Depois de assimilados, os dados ficam disponíveis para relatórios no Customer Journey Analytics.

+++

## Retenção

+++Visão geral da retenção

O relatório Visão geral de retenção do GA4 combina várias exibições de retenção — usuários novos versus recorrentes e um gráfico de coorte que mostra quantos usuários retornam ao longo do tempo.

**Usuários novos vs. recorrentes**: usar os segmentos **[!UICONTROL Primeira Sessão]** e **[!UICONTROL Retornar Sessões]** como linhas em uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md):

1. Arraste o segmento **[!UICONTROL Primeira sessão]** do painel Componentes para a área de linha da tabela e arraste o segmento **[!UICONTROL Sessões de Retorno]** abaixo dele.
2. Adicione as métricas desejadas junto com a métrica padrão **[!UICONTROL Eventos]**.
3. Para analisar a tendência ao longo do tempo, arraste uma visualização de [**[!UICONTROL Linha]**](/help/analysis-workspace/visualizations/line.md) acima da tabela, em seguida, pressione ctrl+clique (Windows) ou cmd+clique (Mac) em cada linha para realçar ambos os segmentos.

**Retenção ao longo do tempo**: usar a visualização de [**[!UICONTROL Tabela de coorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Selecione o ícone Visualizações e arraste uma **[!UICONTROL Tabela de coorte]** para a tela.
2. Arraste a métrica **[!UICONTROL Pessoas]** para os campos de Critérios de Inclusão e de Retorno e selecione **[!UICONTROL Build]**.

A [!UICONTROL Tabela de coorte] agrupa as pessoas por seu período inicial e rastreia o comportamento de retorno nos períodos subsequentes; os critérios de inclusão, retorno e granularidade são todos configuráveis.

+++

## Usuário

+++Detalhes demográficos

O relatório de Detalhes demográficos do GA4 aborda as características do usuário — idade, gênero e interesses (possibilitado pelos Sinais do Google, que exigem que os usuários façam logon em uma conta do Google com personalização ativada) — juntamente com o local (país, região, cidade) e o idioma.

O **Local** mapeia diretamente para dimensões do Customer Journey Analytics: use **[!UICONTROL Países]**, **[!UICONTROL Regiões]** ou **[!UICONTROL Cidades]** em uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) ou a visualização [[!UICONTROL Mapa]](/help/analysis-workspace/visualizations/map.md) para obter uma visão geral geográfica (arraste a métrica **[!UICONTROL Pessoas]** para o slot **[!UICONTROL Adicionar Métrica]** e selecione **[!UICONTROL Compilação]**).

**Idade, sexo e interesses** exigem dados primários. Se a sua organização coletar dados demográficos por meio de CRM, formulários de registro ou pesquisas baseadas em consentimento, assimile-os como um [conjunto de dados de perfil](/help/connections/create-connection.md#profile-dataset) e associe-os aos dados do evento. Essa abordagem produz dados mais confiáveis do que o modelo inferido de sinais do Google do GA4, pois usa atributos próprios consentidos.

+++

+++Detalhes técnicos

O relatório técnico do GA4 mostra a categoria de Navegador, Sistema operacional, Resolução de tela e Dispositivo.

No Analysis Workspace, as seguintes dimensões são mapeadas para as dimensões Técnicas do GA4, cada uma proveniente de um campo XDM padrão:

| Dimensão técnica do GA4 | dimensão do Analysis Workspace | Campo XDM |
|---|---|---|
| Navegador | **[!UICONTROL Navegador]** | `xdm.environment.browserDetails.name` |
| Sistema operacional | **[!UICONTROL Sistema operacional]** | `xdm.environment.operatingSystem` |
| Resolução da tela | **[!UICONTROL Resolução do Monitor]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| Categoria do dispositivo (móvel, desktop, tablet) | **[!UICONTROL Tipo de dispositivo móvel]** | `xdm.device.type` |
| Modelo do dispositivo | **[!UICONTROL Dispositivo móvel]** | `xdm.device.model` |

Arraste qualquer uma dessas dimensões do painel Componentes para uma [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).

>[!NOTE]
>
>Como os navegadores modernos reduziram os detalhes na sequência Usuário-Agente, valores completos e precisos dependem da coleta das [Dicas do cliente do usuário-agente](https://experienceleague.adobe.com/en/docs/experience-platform/collection/use-cases/client-hints) na configuração do Web SDK.

+++

## Explorar

+++Exploração de forma livre

A exploração de forma livre do GA4 é uma tabela de tela em branco com linhas, colunas e sobreposições opcionais de gráfico.

A [**[!UICONTROL Tabela de forma livre]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) da Analysis Workspace é o equivalente direto e a base da maioria dos projetos do Workspace. Arraste qualquer dimensão para as linhas, qualquer métrica para as colunas e qualquer segmento para a área de soltar segmentos acima da tabela.

Consulte [Introdução ao Analysis Workspace](home.md#getting-started-in-analysis-workspace) para obter o mapeamento de terminologia entre o GA4 Explore e o Workspace.

+++

+++Exploração do funnel

A exploração do Funnel no GA4 define uma sequência de etapas e mede a conclusão e a devolução em cada etapa.

No Analysis Workspace, use a visualização [**[!UICONTROL Fallout]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md):

1. Selecione o ícone Visualizações e arraste uma visualização **[!UICONTROL Fallout]** para a tela.
2. Arraste a dimensão, métrica ou segmento que representa sua primeira etapa para o primeiro slot **[!UICONTROL Adicionar ponto de contato]**.
3. Continue adicionando um ponto de contato para cada etapa subsequente da sequência.

Como qualquer dimensão, métrica ou segmento pode servir como ponto de contato, o [!UICONTROL Fallout] corresponde aos funis baseados em eventos do GA4 e se estende às sequências entre canais que misturam eventos, páginas e segmentos.

+++

+++Exploração de caminho

A Exploração de caminho do GA4 (Universal Analytics chamado de Fluxo de usuários) visualiza as sequências de páginas ou eventos pelos quais os usuários navegam.

No Analysis Workspace, use a visualização [**[!UICONTROL Fluxo]**](/help/analysis-workspace/visualizations/c-flow/flow.md):

1. Selecione o ícone Visualizações e arraste uma visualização de **[!UICONTROL Fluxo]** para a tela.
2. Arraste um valor da dimensão para a qual você deseja direcionar (por exemplo, um valor de **[!UICONTROL Página]** ou **[!UICONTROL Tipo de evento]**) no centro do fluxo.
3. A visualização mostra o que os usuários fizeram antes e depois desse ponto.

A visualização [!UICONTROL Flow] é interativa — selecione qualquer nó para expandir caminhos em qualquer direção. Qualquer dimensão pode ser usada para que você possa direcionar em páginas, eventos, canais de marketing ou links personalizados.

+++

+++Sobreposição de segmento

A exploração da sobreposição de segmentos do GA4 mostra como vários segmentos de usuários se cruzam, visualizados como um diagrama de Venn.

No Analysis Workspace, use a visualização [**[!UICONTROL Venn]**](/help/analysis-workspace/visualizations/venn.md):

1. Selecione o ícone Visualizações e arraste uma visualização **[!UICONTROL Venn]** para a tela.
2. Arraste até três segmentos do painel Componentes para a visualização.

O diagrama de Venn mostra os tamanhos das interseções e a [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) abaixo dele mostra os dados subjacentes.

+++

+++Exploração de coorte

A exploração de coorte do GA4 agrupa usuários por uma característica compartilhada (normalmente a data de aquisição) e rastreia seu comportamento ao longo do tempo.

No Analysis Workspace, use a visualização [**[!UICONTROL Tabela de coorte]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md):

1. Selecione o ícone Visualizações e arraste uma **[!UICONTROL Tabela de coorte]** para a tela.
2. Arraste a métrica **[!UICONTROL Pessoas]** para os campos de Critérios de Inclusão e de Retorno.
3. Selecione **[!UICONTROL Criar]**.

A [!UICONTROL Tabela de coorte] agrupa as pessoas por seu período inicial e rastreia o comportamento de retorno nos períodos subsequentes. Por padrão, ele coorta na data de aquisição, mas os critérios de inclusão, retorno e granularidade são configuráveis.

+++

+++Explorador de usuários

O explorador de usuários do GA4 mostra usuários individuais, seu histórico de sessões e uma linha do tempo de eventos.

O Customer Journey Analytics oferece suporte à análise no nível da pessoa de duas maneiras:

* **Com a compilação habilitada**: crie um escopo de segmento para um valor de ID de pessoa específico e aplique-o a qualquer projeto do Workspace. O contêiner **[!UICONTROL Pessoa]** isola a atividade compilada desse indivíduo entre sessões e canais.
* **Dados brutos do evento**: use **visualizações do conjunto de dados** na interface do Adobe Experience Platform para inspecionar registros brutos de eventos XDM. Essa exibição é útil para validação de implementação e depuração de eventos individuais.

+++

+++Tempo de vida do usuário

A exploração da vida útil do usuário do GA4 mede o valor acumulado e o envolvimento de cada usuário em todo o relacionamento com a sua empresa, em vez de dentro de um intervalo de datas fixo. Ele combina métricas históricas de duração com as previsões de aprendizado de máquina da Google para probabilidade de compra, probabilidade de churn e receita prevista.

Eles são mapeados para o Customer Journey Analytics em duas partes:

**O valor histórico da vida útil** pode ser obtido nativamente. Como o Customer Journey Analytics emite relatórios em toda a janela de retenção de dados, você pode definir um intervalo de datas longo e agregar a receita acumulada e o envolvimento de cada pessoa nessa retrospectiva. Com a identificação ou uma ID de pessoa persistente, o contêiner **[!UICONTROL Pessoa]** vincula essa atividade a uma atividade individual e as métricas calculadas expressam um valor por pessoa. O resultado não é uma duração ilimitada, mas uma pesquisa longa e configurável que se aproxima de uma.

**O valor de tempo de vida preditivo** não está incorporado. O Customer Journey Analytics não tem probabilidade de compra no produto, churn ou modelo de receita prevista. Para usar pontuações preditivas, calcule-as externamente (por exemplo, em um CRM ou fluxo de trabalho de ciência de dados) e traga-as para o Customer Journey Analytics como um conjunto de dados de perfil e, em seguida, as supere como dimensões ou métricas. A Adobe recomenda trabalhar com um consultor de implementação para projetar essa abordagem.

+++

## Métricas comuns

+++Usuários ativos → Pessoas

Os **usuários ativos** do GA4 contam os usuários que tiveram pelo menos uma sessão engajada no intervalo de datas.

No Customer Journey Analytics, o equivalente mais próximo é **[!UICONTROL Pessoas]**, uma contagem de IDs de pessoa exclusivas no intervalo de datas. [!UICONTROL Pessoas] inclui todas as pessoas identificadas, independentemente do nível de engajamento, portanto, geralmente é maior do que os usuários Ativos do GA4 para sites com tráfego passivo significativo.

Para uma comparação comportamental mais detalhada, aplique um [segmento de sessões engajadas](compare-data.md#engaged-sessions) para definir o escopo da métrica [!UICONTROL Pessoas] para usuários que atendam aos seus critérios de engajamento.

+++

+++Sessões envolvidas → Métrica calculada

As **Sessões engajadas** do GA4 contam sessões que duraram 10 segundos ou mais, tiveram 2 ou mais exibições de página ou incluíram pelo menos um evento principal.

O Customer Journey Analytics não tem uma métrica de sessões engajadas integrada — você a define como um segmento que captura seus critérios de engajamento e a usa junto com a métrica **[!UICONTROL Sessões]**. Consulte [Sessões envolvidas](compare-data.md#engaged-sessions) para obter a abordagem recomendada e como derivar uma taxa de participação dela.

+++

+++Taxa de engajamento → Métrica calculada

A **Taxa de envolvimento** do GA4 é a porcentagem de sessões envolvidas: sessões envolvidas divididas pelo total de sessões.

No Customer Journey Analytics, crie-a como uma métrica calculada a partir da definição de suas sessões engajadas. Consulte [Sessões envolvidas](compare-data.md#engagement-rate) para obter instruções passo a passo.

+++

+++Tempo médio de envolvimento → Tempo gasto por sessão

O **Tempo médio de envolvimento** do GA4 mede o tempo médio que o navegador ou aplicativo esteve em primeiro plano durante as sessões engajadas.

No Customer Journey Analytics, use **[!UICONTROL Duração da sessão (segundos)]**, que mede o tempo decorrido desde o primeiro evento até o último evento em uma sessão. Esse componente inclui períodos em que o usuário pode não ter se envolvido ativamente, portanto, os valores podem ser diferentes da medição do GA4. É o equivalente incorporado mais próximo.

+++

+++Contagem de eventos → Eventos

A **Contagem de eventos** do GA4 é o número total de vezes que qualquer evento foi registrado.

No Customer Journey Analytics, a métrica equivalente é **[!UICONTROL Eventos]** — o número total de registros de eventos no conjunto de dados para o intervalo de datas selecionado e os segmentos aplicados.

+++

+++Sessões → Sessões

As **Sessões** do GA4 e as **[!UICONTROL Sessões]** da Customer Journey Analytics medem o número de sessões em um intervalo de datas. As contagens podem diferir devido a diferentes regras de definição de sessão. Consulte [Por que os dados do GA4 e do Customer Journey Analytics diferem](compare-data.md#sessions) para obter mais detalhes.

+++

+++Novos usuários → Segmento de primeira sessão aplicado a pessoas

Os **Novos usuários** do GA4 contam os usuários que tiveram sua primeira sessão no intervalo de datas selecionado.

No Analysis Workspace:

1. Localize o segmento **[!UICONTROL Primeira sessão]** no painel Componentes.
2. Arraste-o para a área de destino do segmento acima da sua [[!UICONTROL Tabela de forma livre]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
3. Use a métrica **[!UICONTROL Pessoas]** para contar novas pessoas exclusivas.

+++

+++Taxa de rejeição → Taxa de rejeição (com limitações)

A **Taxa de rejeição** do GA4 é a porcentagem de sessões que não foram envolvidas (menos de 10 segundos, nenhum evento principal, menos de 2 exibições de página). É o inverso da Taxa de engajamento.

A métrica **[!UICONTROL Taxa de rejeição]** da Customer Journey Analytics usa uma definição diferente por padrão e pode ser configurada por visualização de dados. Essas diferenças produzem números materialmente diferentes que medem comportamentos diferentes.

Para aproximar a taxa de rejeição do GA4 no Customer Journey Analytics, crie uma métrica de Taxa de envolvimento e inverta-a com uma segunda métrica calculada definida como `1 - Engagement Rate`. Consulte [Sessões envolvidas](compare-data.md#engagement-rate) para obter a compilação passo a passo.

Consulte [Por que os dados do GA4 e do Customer Journey Analytics diferem](compare-data.md#bounce-rate) para obter uma explicação detalhada da diferença de definição.

+++

+++Eventos principais → Métricas de evento personalizadas

Os **Eventos-chave** do GA4 (anteriormente chamados de Conversões) são eventos designados como resultados comerciais importantes na configuração da propriedade do GA4.

No Customer Journey Analytics, uma conversão é uma métrica de evento personalizada configurada na visualização de dados. Qualquer evento XDM pode ser exposto como uma métrica e uma métrica pode ser definida para incrementar condicionalmente em um valor de campo XDM — por exemplo, uma métrica **[!UICONTROL Compras]** que é incrementada quando `xdm.eventType` é igual a `commerce.purchases`. Localize a métrica relevante pelo rótulo no painel Componentes do Analysis Workspace; o nome reflete como o administrador a configurou.

Para reproduzir o *relatório* dos eventos principais do GA4 (uma lista de todas as conversões com sua contagem), consulte a entrada **Eventos-chave (conversões)** em [Envolvimento](#engagement) nesta página.

+++

>[!MORELIKETHIS]
>
>* [Relatório de dados do Google Analytics](/help/use-cases/third-party/ga/report.md)
