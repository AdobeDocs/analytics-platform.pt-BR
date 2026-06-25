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
source-git-commit: 2c37660458afef6d0202370f3b595b4d907173ef
workflow-type: tm+mt
source-wordcount: 2675
ht-degree: 29%

---

# Criar um feed de dados

Ao criar um feed de dados, você fornece à Adobe:

* As informações sobre o destino para onde os arquivos de dados brutos serão enviados

* Os dados para inclusão em cada arquivo

* A frequência com que os dados são enviados (incluindo o atraso de processamento para capturar ocorrências de chegada tardia)

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
>title="Notificar quando concluído"
>abstract="Especifique um ou mais endereços de email para os quais deseja entregar uma notificação após o envio do feed de dados. Para inserir vários endereços de email, separe-os por vírgula."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervalo de datas da retrospectiva"
>abstract="Controla até que data o Customer Journey Analytics analisa ao processar a entrega do feed de dados.<br/>Essa configuração não altera a janela de frequência (hora ou dia). No entanto, o intervalo de datas da retrospectiva pode influenciar os dados entregues. A qualificação de segmento, o cálculo de sessão, algumas transformações de campo derivadas e a persistência de dimensão são afetados pelo intervalo de datas da retrospectiva."

<!-- markdownlint-enable MD034 -->

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.

1. Selecione [!UICONTROL **Customer Journey Analytics**] no alternador de aplicativos ![App](/help/assets/icons/Apps.svg) na parte superior direita da interface.

1. Na barra de navegação superior, vá para [!UICONTROL **Componentes**] > [!UICONTROL **Feeds de dados**].

1. Selecione [!UICONTROL **Criar**] no canto superior direito da tela.

   Ou, se nenhum feed de dados tiver sido criado anteriormente, selecione [!UICONTROL **Criar feed de dados**] dentro da tabela vazia.

   Uma página é exibida com as seguintes guias: [!UICONTROL **Detalhes**], [!UICONTROL **Estrutura de dados**] e [!UICONTROL **Entrega**].

   ![Nova página de feed de dados](assets/data-feed-new.png)

1. Na guia [!UICONTROL **Detalhes**], preencha os seguintes campos:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Nome**] | O nome do feed de dados. Os nomes devem ser exclusivos na visualização de dados selecionada e podem ter até 255 caracteres. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **Tags**] | Aplique tags ao feed de dados para facilitar a categorização. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **Descrição**] | Especifique uma descrição para o feed de dados. A descrição adicionada fica visível ao editar o feed de dados. |
   | [!UICONTROL **Visualização de dados**] | Selecione a visualização de dados que contém os dados que você deseja exportar.<p>Considere o seguinte ao selecionar uma visualização de dados:</p> <ul><li>Se vários feeds de dados forem criados para a mesma visualização, cada feed de dados deverá ter definições de coluna diferentes.</li><li>A lista de colunas disponíveis depende da empresa de logon à qual a visualização de dados selecionada pertence. Se você alterar a visualização de dados, a lista de colunas disponíveis poderá ser alterada. </li></ul> |

1. Selecione [!UICONTROL **Próximo**].

1. Na guia [!UICONTROL **Estrutura de dados**], verifique se a exibição de dados correta está selecionada no campo **[!UICONTROL Exibição de dados]**.

1. No menu suspenso [!UICONTROL **Segmentos**], procure e selecione segmentos para filtrar os dados incluídos no feed.

   Quando você aplica vários segmentos, eles são agrupados com um operador AND. (Para unir segmentos com um operador OU, primeiro você deve criar um novo segmento no construtor de segmentos e, em seguida, aplicar o novo segmento ao feed de dados.)

1. Adicione componentes à configuração do feed de dados. No painel à esquerda, localize todos os componentes que deseja incluir e arraste-os para a tela para criar sua estrutura de dados. Para selecionar vários componentes, mantenha a tecla **[!UICONTROL Shift]**, **[!UICONTROL Command]** (no macOS) ou **[!UICONTROL Ctrl]** (no Windows) pressionada.

   Use as informações a seguir para entender as dimensões que sempre estão incluídas, as dimensões que não podem ser incluídas e as métricas que devem ser substituídas:

   +++ Dimensões que são sempre incluídas nos feeds de dados

   As seguintes dimensões são incluídas por padrão em todos os feeds de dados e não podem ser removidas:

   | Nome da dimensão | Notas | Feeds de dados | Outros relatórios |
   |---|---|---|---|
   | Carimbo de data e hora | Carimbo de data e hora do período do evento. Granularidade de microssegundos. Representado em UTC. | Obrigatório | Não disponível |
   | ID da linha | Identificador de linha exclusivo | Obrigatório | Não disponível |
   | ID da sessão | Identificador exclusivo de cada sessão | Obrigatório | Não disponível |
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


1. Na guia [!UICONTROL **Entrega**], especifique as seguintes informações:

   | Campo | Função |
   |---------|----------|
   | [!UICONTROL **Tipo de feed**] | Selecione o tipo de feed que deseja criar:<ul><li>[!UICONTROL **Feed ativo**]: exporta dados atuais e futuros.</li><li>[!UICONTROL **Feed de preenchimento retroativo**]: exporta dados históricos entre duas datas anteriores.</li></ul> |
   | [!UICONTROL **Data de início**] | Especifique a data em que deseja que o feed de dados comece. Para iniciar imediatamente o processamento dos feeds de dados de dados históricos, verifique se [!UICONTROL **Feed de preenchimento retroativo**] está selecionado e defina essa data como qualquer data no passado quando os dados estiverem sendo coletados. A data de início é baseada no fuso horário da visualização de dados. |
   | [!UICONTROL **Data final**] | Especifique a data em que deseja que o feed de dados termine. A data de término é baseada no fuso horário da visualização de dados. |
   | [!UICONTROL **Frequência**] | Selecione a frequência com que o feed de dados deve ser enviado. Eventos com carimbos de data e hora que caem na janela de frequência são incluídos na entrega do feed de dados. Os campos [!UICONTROL **Intervalo de datas de retrospectiva**] e [!UICONTROL **Atraso de processamento**] também podem afetar quais eventos são incluídos nos dados para a frequência de entrega escolhida.<p>Para feeds ao vivo, selecione para incluir uma hora de dados ou um dia de dados. Os feeds de preenchimento retroativo devem ser diários.</p><ul><li>**Diariamente**: os feeds contêm dados de um dia inteiro, da meia-noite a meia-noite no fuso horário da visualização de dados. Use essa opção para feeds de preenchimento retroativo ou para feeds em tempo real.</li><li>**Por hora**: os feeds contêm dados de uma hora. Use essa opção para feeds em tempo real.</li></ul> |
   | [!UICONTROL **Intervalo de datas de retrospectiva**] | Controla até que data o Customer Journey Analytics analisa ao processar a entrega do feed de dados. <p>Essa configuração não altera a janela de frequência (hora ou dia), que define o intervalo de tempo dos eventos a serem incluídos na saída do feed de dados. No entanto, o intervalo de datas da retrospectiva pode influenciar os dados entregues, das seguintes maneiras: </p><ul><li>**Qualificação do segmento**: quando um segmento é aplicado à sua definição de feed de dados, todos os eventos dentro do intervalo de datas da pesquisa determinam se uma pessoa se qualifica. A configuração de contêiner do segmento determina o escopo. (Os contêineres possíveis são: Pessoa, Sessão ou Evento. B2B tem os seguintes contêineres adicionais: Conta global, Conta, Oportunidade, Grupo de compras.)  <p>Por exemplo, se um contêiner Pessoa for usado e a pessoa for qualificada durante o intervalo de datas da retrospectiva, todos os eventos dessa pessoa durante a janela de frequência também serão qualificados.</p></li><li>**Cálculo de sessão**: os limites de sessão são calculados usando dados dentro do intervalo de datas da pesquisa.</li><li>**Transformações de campo derivadas**: quaisquer funções de campo derivadas que referenciam contêineres usam o intervalo de datas da pesquisa em exportações de feed de dados.</li><li>**Persistência do Dimension**: se você optar por definir a persistência em uma dimensão individual, também escolha uma expiração para determinar por quanto tempo um item de dimensão persiste além do evento em que está definido. <p>O intervalo de datas de pesquisa afeta a persistência da dimensão quando a expiração é definida como uma das seguintes opções na visualização de dados:</p><ul><li>Para cada dimensão na definição de feed de dados que usa [!UICONTROL **Janela de relatório**] como expiração, o intervalo de datas de retrospectiva se torna a nova janela de relatório.</li><li>Para cada dimensão na definição de feed de dados que usa [!UICONTROL **Tempo personalizado**] como sua expiração, e se o tempo personalizado selecionado se estender além do intervalo de datas da pesquisa, o tempo personalizado será ignorado e o intervalo de datas da pesquisa será usado para a expiração da dimensão.<p>Para obter mais informações sobre como configurar a persistência em dimensões na visualização de dados, consulte [Configurações do componente de Persistência](/help/data-views/component-settings/persistence.md).</p></li></ul> |
   | [!UICONTROL **Atraso no processamento**] | Escolha o tempo de espera antes do processamento de um arquivo de feed de dados. Quaisquer ocorrências de chegada tardia que chegarem durante o atraso de processamento serão incluídas no feed de dados. <p>Atrasos de processamento são úteis por vários motivos, como para dar às implementações móveis uma oportunidade para que os dispositivos offline fiquem online e enviem dados ou para acomodar os processos do lado do servidor de sua organização no gerenciamento de arquivos processados anteriormente. </p><p>Você pode atrasar um feed por 2, 3, 4 ou 8 horas.<p>As sessões devem ser iniciadas após o limite do atraso de processamento para serem incluídas; as sessões que iniciam antes do limite e terminam dentro do atraso de processamento não são incluídas.</p> |
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
   | [!UICONTROL **Notificar quando concluído**] | Especifique um ou mais endereços de email nos quais uma notificação deve ser entregue após o feed de dados ser enviado com êxito ou após uma falha no envio. Para inserir vários endereços de email, separe-os por vírgula. |
   | [!UICONTROL **Habilitar manifesto**] | Escolha se deseja incluir um arquivo de manifesto em cada entrega do feed de dados. O arquivo de manifesto contém informações para cada arquivo incluído no feed de dados. |

1. Selecione **[!UICONTROL Salvar]**.

