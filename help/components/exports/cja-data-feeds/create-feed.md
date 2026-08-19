---
title: Criar um feed de dados
description: Saiba como criar um feed de dados e sobre as informações de arquivos a serem fornecidas à Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 8a5568b3b6136bc3f8b507f551fbb6d169e4b88a
workflow-type: tm+mt
source-wordcount: 4088
ht-degree: 20%

---

# Criar um feed de dados

{{release-limited-testing}}

Ao criar um feed de dados, você fornece à Adobe:

* As informações sobre o destino para onde os arquivos de dados brutos serão enviados

* Os dados para inclusão em cada arquivo

* A frequência com que os dados são enviados (incluindo o atraso de processamento para capturar eventos de chegada tardia)

Antes de criar um feed de dados, é importante ter uma compreensão básica dos feeds de dados e garantir o atendimento de todos os pré-requisitos. Para obter mais informações, consulte: [Visão geral dos feeds de dados](data-feed-overview.md).

## Criar e configurar um feed de dados {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="Manifesto"
>abstract="Escolha se deseja incluir um arquivo de manifesto em cada entrega do feed de dados. Os arquivos de manifesto contêm informações para cada arquivo incluído no feed de dados. Ao enviar dados do feed de dados em um único pacote, também é possível optar por incluir um arquivo de finalização, mas arquivos de manifesto são recomendados. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="Notificar sobre problemas, quando estiverem concluídos e quando estiverem expirando"
>abstract="Especifique um ou mais endereços de email nos quais uma notificação deve ser entregue quando o feed de dados for concluído, expirar ou encontrar problemas. Separe vários endereços de email com vírgula."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Atraso no processamento"
>abstract="O tempo de espera por eventos de chegada tardia antes de processar um arquivo de feed de dados. Quaisquer ocorrências de chegada tardia que chegarem durante o período de tempo de atraso de processamento serão incluídas no feed de dados. <p>Atrasos de processamento são úteis por vários motivos, como para dar às implementações móveis uma oportunidade para que os dispositivos offline fiquem online e enviem dados ou para acomodar os processos do lado do servidor de sua organização no gerenciamento de arquivos processados anteriormente.</p><p>As sessões devem ser iniciadas após o limite do atraso de processamento para serem incluídas; as sessões que iniciam antes do limite e terminam dentro do atraso de processamento não são incluídas.</p><p>O Customer Journey Analytics determina dinamicamente o atraso ideal com base no tempo que os eventos de chegada tardia normalmente levam para o feed, mas você pode defini-lo manualmente para atrasar por 2, 3, 4 ou 8 horas.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user-agent"
>title=""
>abstract="Os dados do agente usuário e os dados de pesquisa do dispositivo não podem existir na mesma configuração de feed de dados."

<!-- markdownlint-enable MD034 -->

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.

1. Selecione [!UICONTROL **Customer Journey Analytics**] no alternador de aplicativos ![App](/help/assets/icons/Apps.svg) na parte superior direita da interface.

1. Na barra de navegação superior, vá para [!UICONTROL **Componentes**] > [!UICONTROL **Exportações**].

1. Selecione a guia [!UICONTROL **Feeds de dados**].

1. Selecione [!UICONTROL **Criar**] no canto superior direito da tela.

   Ou, se nenhum feed de dados tiver sido criado anteriormente, selecione [!UICONTROL **Criar feed de dados**] dentro da tabela vazia.

   Uma página é exibida com as seguintes guias: [!UICONTROL **Detalhes**], [!UICONTROL **Estrutura de dados**] e [!UICONTROL **Entrega**].

   ![Nova página de feed de dados](assets/data-feed-new.png)

1. Na guia [!UICONTROL **Detalhes**], preencha os seguintes campos:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome**] | O nome do feed de dados. Os nomes devem ser exclusivos na visualização de dados selecionada e podem ter até 255 caracteres. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Aplique tags ao feed de dados para facilitar a categorização. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descrição**] | Especifique uma descrição para o feed de dados (até 500 caracteres). A descrição adicionada fica visível ao editar o feed de dados. |
   | [!UICONTROL **Visualização de dados**] | Selecione a visualização de dados que contém os dados que você deseja exportar.<p>Considere o seguinte ao selecionar uma visualização de dados:</p> <ul><li>Se vários feeds de dados forem criados para a mesma visualização, cada feed de dados deverá ter definições de coluna diferentes.</li><li>A lista de colunas disponíveis depende da empresa de logon à qual a visualização de dados selecionada pertence. Se você alterar a visualização de dados, a lista de colunas disponíveis poderá ser alterada. </li></ul> |

1. Selecione [!UICONTROL **Próximo**].

1. Na guia [!UICONTROL **Estrutura de dados**], verifique se a exibição de dados correta está selecionada no campo **[!UICONTROL Exibição de dados]**.

   <!--add screenshot-->

1. No menu suspenso [!UICONTROL **Segmentos**], procure e selecione segmentos para filtrar os dados incluídos no feed.

   Quando você aplica vários segmentos, eles são agrupados com um operador AND. Para unir segmentos com um operador OU, primeiro você deve criar um novo segmento no construtor de segmentos e, em seguida, aplicar o novo segmento ao feed de dados.

   Os segmentos aplicados aqui complementam quaisquer segmentos que já possam ter sido aplicados na visualização de dados.

1. Adicione componentes à configuração do feed de dados. O painel esquerdo mostra apenas componentes válidos para feeds de dados.

   * **Arrastar e soltar**: arraste os componentes do painel esquerdo para a tela. Mantenha o **[!UICONTROL Shift]** pressionado, ou mantenha pressionado o **[!UICONTROL Command]** (macOS) ou o **[!UICONTROL Ctrl]** (Windows) para selecionar e arrastar vários componentes de uma só vez.
   * **Botão de adição**: selecione o ícone de adição ![Adicionar](/help/assets/icons/Add.svg) ao lado de qualquer componente no painel esquerdo para adicioná-lo à tela.
   * **[!UICONTROL Mostrar tudo]**: selecione **[!UICONTROL Mostrar tudo]** na parte inferior da lista de componentes para abrir uma caixa de diálogo mostrando todos os componentes disponíveis. Marque a caixa de seleção ao lado de cada componente que você deseja adicionar e selecione **[!UICONTROL Adicionar selecionado]**. Quando um termo de pesquisa ou uma marca de filtro está ativa no painel à esquerda, o botão **[!UICONTROL Adicionar tudo]** também é exibido, permitindo adicionar todos os resultados filtrados de uma só vez.

   Quando você adiciona um componente que pertence a um campo de matriz XDM (por exemplo, um campo de proposta do Adobe Journey Optimizer), ele aparece na tela como um grupo aninhado recolhível em vez de um item simples. O grupo reflete a estrutura de dados subjacente e as saídas como uma matriz aninhada no arquivo exportado.

   <!--add screenshot-->

   +++ Dimensões que são sempre incluídas nos feeds de dados

   As seguintes dimensões são incluídas por padrão em todos os feeds de dados e não podem ser removidas:

   | Nome da dimensão | Notas | Feeds de dados | Outros relatórios |
   |---|---|---|---|
   | Carimbo de data e hora UTC | A data e a hora em que o evento ocorreu, representadas no fuso horário UTC. Suporta granularidade de subsegundos (microssegundos). | Obrigatório | Não disponível |
   | ID da linha | O identificador exclusivo de cada linha incluída no feed de dados. | Obrigatório | Não disponível |
   | ID da sessão | O identificador exclusivo para cada sessão incluído no feed de dados. | Obrigatório | Não disponível |
   | ID da pessoa | O identificador de pessoa para a visualização de dados e a conexão | Obrigatório | Padrão opcional |
   | ID da conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | ID da conta ao usar o contêiner Conta | Obrigatório | Padrão opcional |

   +++

   +++ Dimensões que não podem ser incluídas nos feeds de dados

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

   +++

   +++ Métricas que não podem ser incluídas nos feeds de dados

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

   +++

   +++ Dimensões que não podem ser usadas juntas nos feeds de dados

   >[!IMPORTANT]
   >
   >Determinadas dimensões não podem ser usadas juntas em conjuntos de dados do Experience Platform e, portanto, não podem ser incluídas no mesmo feed de dados.
   >
   >Se você optar por incluir as dimensões **Agente do Usuário** ou **ID do Mobile** no feed de dados, as dimensões listadas abaixo não poderão ser adicionadas ao feed de dados.
   >
   >Se você usar o Web SDK, essa restrição será imposta nos fluxos de dados antes que os dados cheguem a um conjunto de dados do Experience Platform. Para obter mais informações, consulte [Configurar pesquisa de dispositivo](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure#geolocation-device-lookup) em [Criar e configurar sequências de dados](https://experienceleague.adobe.com/pt-br/docs/experience-platform/datastreams/configure) no guia Coleção de dados.

   As seguintes dimensões não podem ser usadas junto com as dimensões **Agente de Usuário** ou **ID de Dispositivo Móvel**:

   * Tipo de navegador
   * Navegador
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

   +++

   +++ Métricas que devem ser substituídas nos feeds de dados

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

   +++

   +++ Componentes padrão opcionais

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

   +++

1. (Opcional) Reordene os componentes na tela arrastando-os. A ordem definida é preservada como a ordem das colunas no arquivo de feed de dados exportado.

1. (Opcional) Altere a ID do componente exibida na saída do feed de dados.

   1. Passe o mouse sobre um componente na tela de desenho, em seguida, selecione o ícone de informações.

   1. No campo ID do componente, especifique uma nova ID do componente.

      <!--add screenshot-->

1. (Opcional) Use os painéis **[!UICONTROL Resumo do feed]** e **[!UICONTROL Visualização do esquema]** no lado direito da página para examinar sua estrutura de dados antes de continuar:

   * O **[!UICONTROL Resumo do feed]** mostra uma contagem ativa do total de componentes, colunas, dimensões e métricas que você adicionou.
   * A **[!UICONTROL visualização de esquema]** mostra uma representação JSON do esquema de feed de dados que é atualizado à medida que você adiciona ou reordena componentes.
   * O botão **[!UICONTROL Linhas de exemplo]** abre uma caixa de diálogo que mostra linhas de saída de exemplo para que você possa verificar se a estrutura parece correta. Essa caixa de diálogo mostra apenas dados de exemplo e não reflete seus dados reais.

   <!--add screenshot-->

1. Na guia [!UICONTROL **Entrega**], na seção [!UICONTROL **Agendamento**], escolha o tipo de feed que deseja criar (ativo ou preenchimento retroativo) e especifique a janela de relatórios, a frequência e outras opções de configuração:

   <!--add screenshot-->

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Tipo de feed**] | Selecione o tipo de feed que deseja criar:<ul><li>[!UICONTROL **Feed ativo**]: exporta dados atuais e futuros.</li><li>[!UICONTROL **Feed de preenchimento retroativo**]: exporta dados históricos. </li></ul> |
   | [!UICONTROL **Data de início**] | A data em que o feed de dados começa. Para feeds ao vivo, isso deve ser hoje ou uma data futura. Para feeds de preenchimento retroativo, essa deve ser uma data passada na janela de retenção de dados da visualização de dados. A data de início é baseada no fuso horário da visualização de dados. |
   | [!UICONTROL **Data de expiração**] <br/>Disponível somente para feeds em tempo real | A data em que o feed de dados expira e não é mais executado. A data é baseada no fuso horário da visualização de dados. |
   | [!UICONTROL **Data final**]<br/> Disponível somente para feeds de preenchimento retroativo | A data em que o feed de dados termina. A data final não pode ser no futuro. A data é baseada no fuso horário da visualização de dados. |
   | [!UICONTROL **Frequência**] | Selecione a frequência com que o feed de dados deve ser enviado. Eventos com carimbos de data e hora que caem na janela de frequência são incluídos na entrega do feed de dados. Os campos [!UICONTROL **Intervalo de datas de retrospectiva**] e [!UICONTROL **Atraso de processamento**] também podem afetar quais eventos são incluídos nos dados para a frequência de entrega escolhida.<p>Para feeds ao vivo, selecione para incluir uma hora de dados ou um dia de dados. Para feeds de preenchimento retroativo, este campo está bloqueado para **Diariamente**, o que significa que os dados são agrupados em partes diárias.</p><ul><li>**Diariamente**: os feeds contêm dados de um dia inteiro, da meia-noite a meia-noite no fuso horário da visualização de dados. <p>Essa opção é necessária para feeds de preenchimento retroativo e é opcional para feeds em tempo real.</p></li><li>**Por hora**: os feeds contêm dados de uma hora. <p>Essa opção está disponível somente para feeds em tempo real.</p></li></ul> |
   | [!UICONTROL **Intervalo de datas de retrospectiva**] | Controla até que data o Customer Journey Analytics analisa ao processar a entrega do feed de dados. O padrão é 30 dias.<p>A janela de frequência (hora ou dia) determina quais eventos são incluídos no feed de dados, enquanto o **intervalo de datas da retrospectiva** fornece o contexto histórico necessário para classificar esses eventos corretamente.</p><p>A qualificação de segmento, a persistência de dimensão, o cálculo de sessão e as transformações de campo derivadas podem afetar os eventos incluídos.</p> <p>Antes de configurar esta opção, veja os detalhes e os exemplos descritos na seção abaixo, [Entenda o intervalo de datas da retrospectiva](#understand-the-lookback-date-range).</p> |
   | [!UICONTROL **Atraso no processamento**] | Escolha o tempo de espera antes do processamento de um arquivo de feed de dados. O padrão é 2 horas. Todos os eventos de chegada tardia que chegam durante o atraso de processamento são incluídos no feed de dados. <p>Atrasos de processamento são úteis por vários motivos, como para dar às implementações móveis uma oportunidade para que os dispositivos offline fiquem online e enviem dados ou para acomodar os processos do lado do servidor de sua organização no gerenciamento de arquivos processados anteriormente. </p><p>As sessões devem ser iniciadas após o limite do atraso de processamento para serem incluídas; as sessões que iniciam antes do limite e terminam dentro do atraso de processamento não são incluídas.</p><p>O Customer Journey Analytics determina dinamicamente o atraso ideal com base no tempo que os eventos de chegada tardia normalmente levam para o feed, mas você pode defini-lo manualmente para atrasar por 2, 3, 4 ou 8 horas.</p> |
   | [!UICONTROL **Formato de compactação**] | Selecione o formato de compactação dos arquivos de saída do Parquet entregues ao destino da nuvem. Escolha entre os seguintes formatos:<ul><li>[!UICONTROL **Snappy**]: compactação e descompactação rápidas com tamanhos de arquivo moderados. Amplamente compatível com plataformas de dados modernas, como BigQuery, Snowflake e Apache Spark.</li><li>[!UICONTROL **GZip**]: amplamente compatível, inclusive com ferramentas que não oferecem suporte nativo ao Snappy. Recomendado se o pipeline downstream exigir um padrão de compactação amplamente reconhecido.</li><li>[!UICONTROL **Z Padrão (Zstd)**]: alta eficiência de compactação com descompactação rápida. Adequado se minimizar o tamanho do arquivo é uma prioridade e suas ferramentas suportam Zstd.</li></ul> |

1. Na guia [!UICONTROL **Entrega**], na seção [!UICONTROL **Destino**], configure o destino para onde deseja que os dados sejam enviados.

   >[!NOTE]
   >
   >Considere o seguinte ao configurar um destino de relatórios:
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* Todas as contas em nuvem configuradas anteriormente estão disponíveis para uso nos feeds de dados. Você pode configurar contas em nuvem no Gerenciador de locais, em [Componentes > Exportações > Contas de local](/help/components/exports/cloud-export-accounts.md).
   >
   >* As contas em nuvem estão associadas à sua conta de usuário do Customer Journey Analytics. Outros usuários não podem usar ou exibir contas na nuvem configuradas por você, a menos que você as disponibilize para todos os usuários da organização.
   >
   >* Você pode editar qualquer local que criar no Gerenciador de locais em [Componentes > Exportações > Locais](/help/components/exports/cloud-export-locations.md).

   Preencha os campos a seguir:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Exibir destinos para todos os usuários**] | Se você for um administrador do sistema, poderá habilitar essa opção para exibir destinos criados por todos os usuários em sua organização. Quando esta opção está desativada, somente os destinos que você criou são exibidos. |
   | [!UICONTROL **Conta**] | Realize uma das seguintes ações:<ul><li>**Usar uma conta existente:** Selecione o menu suspenso ao lado do campo **[!UICONTROL Conta]**. Ou comece digitando o nome da conta e selecione-o no menu suspenso. <p>As contas estão disponíveis somente se você as configurar ou se forem compartilhadas com uma organização da qual você faz parte.</p></li><li>**Criar uma nova conta:** Selecione **[!UICONTROL Adicionar conta]** no menu suspenso **[!UICONTROL Conta]**. Para obter informações sobre como configurar a conta, consulte [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md).</li></ul> |
   | [!UICONTROL **Localização**] | Realize uma das seguintes ações:<ul><li>**Usar um local existente:** Selecione o menu suspenso ao lado do campo **[!UICONTROL Local]**. Ou comece digitando o nome do local e selecione-o no menu suspenso.</li><li>**Criar um novo local:** Selecione **[!UICONTROL Adicionar local]** no menu suspenso **[!UICONTROL Local]**. Para obter informações sobre como configurar o local, consulte [Configurar locais de exportação na nuvem](/help/components/exports/cloud-export-locations.md).</li></ul> |
   | [!UICONTROL **Notificar por email quando concluído**] | Especifique um ou mais endereços de email nos quais uma notificação deve ser entregue após o feed de dados ser enviado com êxito ou após uma falha no envio. Para inserir vários endereços de email, separe-os por vírgula. |
   | [!UICONTROL **Habilitar manifesto**] | Escolha se deseja incluir um arquivo de manifesto em cada entrega do feed de dados. O arquivo de manifesto contém informações para cada arquivo incluído no feed de dados. |

1. Selecione **[!UICONTROL Salvar]**.

## Entender o intervalo de datas da pesquisa {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervalo de datas da retrospectiva"
>abstract="Controla a aparência retroativa do Customer Journey Analytics ao processar cada delivery.<p>A janela de frequência (hora ou dia) determina quais eventos são incluídos no feed de dados, enquanto o **intervalo de datas da retrospectiva** fornece o contexto histórico necessário para classificar esses eventos corretamente.</p><p>A qualificação de segmento, a persistência de dimensão, o cálculo de sessão e as transformações de campo derivadas podem afetar os eventos incluídos.</p><p>Uma pesquisa mais longa melhora a precisão; uma pesquisa mais curta melhora o desempenho.</p>"

<!-- markdownlint-enable MD034 -->

O intervalo de datas de pesquisa controla a aparência retroativa do Customer Journey Analytics ao processar cada entrega de feed de dados.

Os eventos ainda devem ter carimbos de data e hora que se enquadrem na janela de frequência (hora ou dia) a serem incluídos na entrega, mas os dados que se enquadram no **intervalo de datas de retrospectiva** fornecem o contexto histórico necessário para classificar esses eventos corretamente.

Ao configurar essa opção, considere os seguintes conceitos importantes:

* Um intervalo de datas de pesquisa mais longo normalmente resulta em dados mais precisos; um intervalo mais curto resulta em melhor desempenho do delivery.
* O intervalo de datas de pesquisa, junto com a janela de frequência, funciona de forma semelhante ao intervalo de datas do relatório do Analysis Workspace. Entretanto, há [diferenças importantes](/help/components/exports/cja-data-feeds/df-comparison-workspace.md#differences). Essas diferenças podem resultar em discrepâncias de dados entre os relatórios do Workspace e os deliveries do feed de dados.

Qualificação de segmento, cálculo de sessão, persistência de dimensão e transformações de campo derivadas são consideradas ao processar dados dentro do intervalo de datas de lookback:

### Qualificação de segmento

Quando um segmento é aplicado à definição do feed de dados, os dados dentro do intervalo de datas da retrospectiva determinam quais eventos, sessões ou pessoas se qualificam para o segmento. A configuração de contêiner do segmento determina o escopo. (Os contêineres possíveis são: Pessoa, Sessão ou Evento. B2B inclui os seguintes contêineres adicionais: Conta global, Conta, Oportunidade, Grupo de compras.)

>[!BEGINSHADEBOX]

**Exemplo:**

Suponha que você queira criar um feed de dados para entender o comportamento dos usuários que fazem parte de uma campanha de marketing específica, Campanha B.

Para fazer isso, aplique um segmento ao feed de dados chamado _Usuários na Campanha B_, indicando que somente os eventos vinculados aos usuários neste segmento devem ser incluídos no feed de dados.

Nesse caso, os usuários são incluídos no feed de dados somente se atenderem **às duas** condições a seguir:

* O usuário tinha um evento com um carimbo de data e hora que está na janela de frequência do feed de dados (a hora ou o dia especificado do feed de dados).
* O usuário qualificado para o _segmento B_ da campanha **em algum momento dentro do intervalo de datas da retrospectiva**.

  Para um evento de qualificação ocorrido há 9 dias, isso significa que o usuário **seria incluído** no feed de dados se o intervalo de datas da retrospectiva fosse definido como 30 dias, mas o usuário **não seria incluído** no feed de dados se o intervalo de datas da retrospectiva fosse definido como 7 dias.

>[!ENDSHADEBOX]

### Cálculo de sessão

Os limites da sessão são calculados usando dados dentro do intervalo de datas da retrospectiva. <!--Maybe this matters more regarding what the session ID is? Could it impact the Session ID? This could impact several factors, such as session-based persistence.-->

### Persistência do Dimension

Ao definir a persistência em uma dimensão individual, você também define uma expiração para determinar por quanto tempo o item de dimensão persiste além do evento em que está definido.

O intervalo de datas de pesquisa afeta a persistência da dimensão quando a expiração é definida como uma das seguintes opções na visualização de dados:

* [!UICONTROL **Janela de relatório de pessoa**]: o intervalo de datas da retrospectiva torna-se a nova janela de relatório para cada dimensão na definição de feed de dados que usa [!UICONTROL **Janela de relatório de pessoa**] como sua expiração.
* [!UICONTROL **Tempo personalizado**]: se o tempo personalizado selecionado se estender além do intervalo de datas da pesquisa, o tempo personalizado será ignorado e o intervalo de datas da pesquisa será usado para a expiração da dimensão para cada dimensão na definição de feed de dados que usa [!UICONTROL **Tempo personalizado**] como sua expiração. Valores que ocorreram antes do intervalo de datas da retrospectiva não são considerados.

  Para obter mais informações sobre como configurar a persistência em dimensões na visualização de dados, consulte [Configurações do componente de Persistência](/help/data-views/component-settings/persistence.md).

Para obter os dados mais precisos, considere definir o intervalo de datas de pesquisa com um valor igual ou maior que o conjunto de persistência em dimensões em seus dados. No entanto, lembre-se de que um intervalo de datas de lookback mais curto resulta em melhor desempenho para as entregas do feed de dados.

>[!BEGINSHADEBOX]

**Exemplo:**

Suponha que, em seu feed de dados, você queira saber qual usuário de campanha de marketing viu originalmente antes de acessar seu site.

Para fazer isso, defina a persistência na dimensão Campanhas com Original como o modelo de alocação.

Nesse caso, a campanha original é exibida na saída do feed de dados somente se os usuários atenderem **ambos** das seguintes condições:

* O usuário tinha um evento com um carimbo de data e hora que está na janela de frequência do feed de dados (a hora ou o dia especificado do feed de dados).

* O usuário se qualificou para a campanha original **em algum momento dentro do intervalo de datas da retrospectiva**.

  Se o usuário se qualificou para a campanha original há 9 dias, a campanha original **será incluída** no feed de dados se o intervalo de datas da retrospectiva for definido como 30 dias, mas a campanha original **não será incluída** no feed de dados se o intervalo de datas da retrospectiva for definido como 7 dias.

>[!ENDSHADEBOX]

### Transformações de campo derivadas

Quaisquer funções de campo derivadas que fazem referência a contêineres usam o intervalo de datas de retrospectiva nas exportações de feed de dados. Quais recursos de data existem em campos derivados? <!--Not sure how this applies.-->



