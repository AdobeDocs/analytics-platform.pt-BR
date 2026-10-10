---
title: Componentes disponíveis nos feeds de dados do Customer Journey Analytics
description: Saiba quais dimensões e métricas são necessárias, não compatíveis, restritas ou devem ser substituídas ao criar feeds de dados do Customer Journey Analytics.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: adc7e85339e89c181375c0d3ea5c228d473239a7
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 43%
---
# Disponibilidade de componentes em feeds de dados

{{release-limited-testing}}

Nem todos os componentes do Customer Journey Analytics podem ser usados em feeds de dados. Algumas dimensões são incluídas em cada feed de dados, alguns componentes não podem ser incluídos e algumas métricas devem ser substituídas por uma substituição.

Use as informações a seguir para entender quais componentes você pode incluir ao [criar um feed de dados](/help/components/exports/cja-data-feeds/create-feed.md).

## Dimensões obrigatórias {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="Dimensões obrigatórias"
>abstract="Todo feed de dados deve incluir determinadas dimensões, identificadas por um rótulo **Obrigatório** ao lado do nome da dimensão. Essas dimensões fornecem a estrutura mínima necessária para a análise no nível do evento."

<!-- markdownlint-enable MD034 -->

As seguintes dimensões são incluídas por padrão em todos os feeds de dados e não podem ser removidas:

| Nome da dimensão | Notas | Feeds de dados | Outros relatórios |
|---|---|---|---|
| Carimbo de data e hora UTC | A data e a hora em que o evento ocorreu, representadas no fuso horário UTC. Suporta granularidade de subsegundos (microssegundos). | Obrigatório | Não disponível |
| ID da linha | O identificador exclusivo de cada linha incluída no feed de dados. | Obrigatório | Não disponível |
| ID da sessão | O identificador exclusivo para cada sessão incluído no feed de dados. | Obrigatório | Não disponível |
| ID da pessoa | O identificador de pessoa para a visualização de dados e a conexão | Obrigatório | Padrão opcional |
| ID da conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID da conta ao usar o contêiner Conta | Obrigatório | Padrão opcional |

## Dimensões não suportadas {#unsupported-dimensions}

As dimensões padrão do Customer Journey Analytics não podem ser incluídas nos feeds de dados. A tabela a seguir lista essas dimensões:

| Nome da dimensão | Notas | Feeds de dados |
|---|---|---|
| 5 minutos | Intervalos de cinco minutos quando os eventos ocorreram (arredondados para baixo) | Não disponível |
| 15 minutos | Intervalos de 15 minutos quando os eventos ocorreram (arredondados para baixo) | Não disponível |
| 30 minutos | Intervalos de trinta minutos quando os eventos ocorreram (arredondados para baixo) | Não disponível |
| Dia | Dia em que um evento ocorreu | Não disponível |
| Dia da semana | Dia da semana em que um evento ocorreu | Não disponível |
| Dia do mês | Dia do mês em que um evento ocorreu | Não disponível |
| Hora | Hora em que um evento ocorreu (arredondada para baixo) | Não disponível |
| Hora do dia | Hora do dia em que um evento ocorreu (arredondada para baixo) | Não disponível |
| Minuto | Minuto em que um evento ocorreu (arredondado para baixo) | Não disponível |
| Minuto da hora | Minuto da hora em que um evento ocorreu (arredondado para baixo) | Não disponível |
| Mês | Mês em que um evento ocorreu | Não disponível |
| Mês do ano | Mês do ano em que um evento ocorreu | Não disponível |
| Trimestre | Trimestre em que ocorreu um evento | Não disponível |
| Trimestre do ano | Trimestre do ano em que um evento ocorreu | Não disponível |
| Second | Segundo em que ocorreu um evento (arredondado para baixo) | Não disponível |
| Semana | Semana em que um evento ocorreu | Não disponível |
| Semana do ano | Semana do ano em que um evento ocorreu | Não disponível |
| Ano | Ano em que um evento ocorreu | Não disponível |

## Métricas não suportadas {#unsupported-metrics}

As seguintes métricas padrão do Customer Journey Analytics não podem ser incluídas nos feeds de dados:

| Nome da métrica | Notas | Feeds de dados |
|---|---|---|
| Perfil de visitantes do Adobe | | Não disponível |
| União de oportunidades da Adobe | | Não disponível |
| Perfil de oportunidades da Adobe | | Não disponível |
| União de contas do Adobe | | Não disponível |
| Perfil de contas do Adobe | | Não disponível |
| União de grupos de compra da Adobe | | Não disponível |
| Perfil de grupos de compra da Adobe | | Não disponível |
| União de contas globais da Adobe | | Não disponível |
| Perfil de contas globais da Adobe | | Não disponível |
| União de pessoas da Adobe | | Não disponível |
| Perfil de pessoas da Adobe | | Não disponível |

## Dimensões que não podem ser usadas juntas {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

<!-- pretty sure this isn't being used -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="Os dados do agente do usuário e os dados de pesquisa de dispositivos não podem coexistir na mesma configuração de feed de dados."

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>Determinadas dimensões não podem ser usadas juntas em conjuntos de dados do Experience Platform e, portanto, não podem ser incluídas no mesmo feed de dados.
>
>Se você optar por incluir as dimensões **Agente de usuário** ou **ID de dispositivo móvel** no feed de dados, as dimensões listadas abaixo não poderão ser adicionadas ao feed de dados.
>
>Se você usar o Web SDK, essa restrição será imposta nos fluxos de dados antes que os dados cheguem a um conjunto de dados do Experience Platform. Para obter mais informações, consulte [Configurar pesquisa de dispositivo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure#geolocation-device-lookup) em [Criar e configurar sequências de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure) no guia Coleção de dados.

As seguintes dimensões não podem ser usadas junto com as dimensões **Agente de Usuário** ou **ID de Dispositivo Móvel**:

>[!NOTE]
>
>A lista a seguir usa nomes de dimensão padrão. As dimensões renomeadas na visualização de dados aparecem nos feeds de dados com seus nomes personalizados.


* Tipo de navegador
* Navegador
* ID do navegador
* Fabricante do dispositivo móvel
* Tipo de dispositivo móvel
* Suporte a Áudio Remoto
* DRM Remoto
* Java VM Móvel
* Serviços de Informação Remotos
* Suporte a Imagem Remota
* Intensidade de Cor Remota
* Protocolos de Rede Remota
* Número do dispositivo móvel
* Extensão máx. de email móvel
* Decoração de correio para dispositivo móvel
* Push To Talk para dispositivo móvel
* Largura da tela do dispositivo móvel
* Extensão máx. do URL do navegador para dispositivo móvel
* Sistema operacional de dispositivos móveis (descontinuado)
* Altura da tela do dispositivo móvel
* Suporte a Vídeo Remoto
* Suporte a Cookie Remoto
* Extensão max do marcador de dispositivo móvel
* Tamanho da tela do dispositivo móvel
* Nome do dispositivo móvel
* Tipos de sistema operacional
* Sistemas operacionais
* ID do sistema operacional

## Métricas que exigem um substituto {#substitute-metrics}

As seguintes métricas do Customer Journey Analytics devem ser substituídas:

| Nome da métrica | Notas | Feeds de dados |
|---|---|---|
| Contas [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Com base na ID de conta especificada na conexão | Não disponível. Use a contagem distinta da ID da conta. |
| Grupo de compras [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Grupos de compras com base na ID do grupo de compras na conexão | Não disponível. Use a contagem distinta da ID do grupo de compra. |
| Eventos | Número de linhas de todos os conjuntos de dados de eventos em uma conexão | Não disponível. Use a contagem distinta da ID de linha. |
| Contas globais [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Com base na ID de contas globais na conexão | Não disponível. Use a contagem distinta da ID de contas globais. |
| Oportunidades [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Oportunidades baseadas na ID de oportunidade na conexão | Não disponível. Use a contagem distinta da ID de oportunidade. |
| Pessoas | Com base na ID de pessoa especificada em uma conexão | Não disponível. Use a contagem distinta da ID de pessoa. |
| Conversas | Número de conversas | Não disponível. Use a contagem distinta da ID de conversa. |
| Término da sessão | Número de eventos que foram o último evento de uma sessão | Não disponível |
| Início da sessão | Número de eventos que foram o primeiro evento de uma sessão | Não disponível |
| Sessões | Com base nas configurações de sessão da visualização de dados | Não disponível. Use a contagem distinta da ID da sessão. |
| Tempo gasto (segundos) | Soma o tempo entre dois valores de dimensão diferentes | Não disponível |

## Componentes padrão opcionais {#optional-standard-components}

| Nome do componente | Tipo | Notas | Feeds de dados |
|---|---|---|---|
| AM/PM | Dimensão de separação de tempo | AM ou PM | Não disponível |
| ID do lote | Dimensão | Identificador para um lote do Experience Platform | Disponível |
| ID do conjunto de dados | Dimensão | Identificador para um conjunto de dados da Experience Platform | Disponível |
| Dia do mês | Dimensão de separação de tempo | 1-31 | Não disponível |
| Dia da semana | Dimensão de separação de tempo | de segunda a domingo | Não disponível |
| Dia do ano | Dimensão de separação de tempo | 1-366 | Não disponível |
| Profundidade do evento | Dimensão | Valor numérico sequencial (1, 2, 3, etc.) atribuído a cada interação de evento em uma sessão<p>Redefine no início de cada nova sessão</p> | Disponível |
| Hora do dia | Dimensão de separação de tempo | 0-23 | Não disponível |
| Mês do ano | Dimensão de separação de tempo | Janeiro-dezembro | Não disponível |
| Primeiras sessões | Métrica | A primeira sessão definida de uma pessoa na janela de relatórios | Não disponível |
| Sessões de retorno | Métrica | Sessões que não foram a primeira sessão de uma pessoa | Não disponível |
| Namespace da ID de pessoa | Dimensão | Tipo de ID no qual a ID de pessoa consiste (por exemplo, ID de email ou cookie) | Disponível |
| ID da Conta Global [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensão | ID da conta global ao usar o contêiner da conta global | Disponível |
| ID da oportunidade [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensão | ID da oportunidade ao usar o contêiner Oportunidade | Disponível |
| ID do Grupo de Compras [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | Dimensão | ID do Grupo de compra ao usar o contêiner Grupo de compra | Disponível |
| Trimestre do ano | Dimensão de separação de tempo | T1, T2, T3, T4 | Não disponível |
| Repetir sessão | Métrica | Sessões que não foram a primeira sessão de uma pessoa | Não disponível |
| Tipo de sessão | Dimensão | Dois valores: Primeira Vez ou Retorno | Não disponível |
| Tempo gasto por evento | Dimensão | Segmenta a métrica Tempo gasto em segmentos de evento | Não disponível |
| Tempo gasto por sessão | Dimensão | Segmenta a métrica Tempo gasto em segmentos de sessão | Não disponível |
| Tempo gasto por pessoa | Dimensão | Segmenta a métrica Tempo gasto em segmentos de pessoa | Não disponível |
| Final de semana/Dia de semana | Dimensão de separação de tempo | Final de semana ou Dia de semana | Não disponível |
