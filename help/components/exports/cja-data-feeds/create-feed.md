---
title: Criar um feed de dados
description: Saiba como criar um feed de dados e sobre as informações de arquivos a serem fornecidas à Adobe.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 93107a7cf46e5d71bcb5c588eb7395fd1b88d150
workflow-type: tm+mt
source-wordcount: '3924'
ht-degree: 12%
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
>title="Notifique-me de problemas, quando concluído e quando expirar"
>abstract="Especifique um ou mais endereços de email para os quais uma notificação deve ser enviada quando o feed de dados terminar, estiver expirando ou encontrar problemas. Separe vários endereços de email com vírgulas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_frequency_granularity"
>title="Frequência e granularidade"
>abstract="**Frequência de entrega** (feeds em tempo real): a frequência com que o feed de dados é entregue. As entregas por hora contêm dados de uma hora; as entregas diárias contêm dados de um dia. O intervalo de datas da retrospectiva e o atraso de processamento também podem afetar os eventos incluídos.<p>**Granularidade** (feeds de preenchimento retroativo): o intervalo de tempo usado para dividir os dados históricos. Cada bloco contém os dados de um dia e é entregue o mais rápido possível, não uma vez por dia. Este campo é sempre definido como Diário e não pode ser modificado.</p>"

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

1. (Opcional) No painel à esquerda, use o campo **pesquisa** para localizar componentes específicos. Ou selecione o ícone **Classificar** ![Ícone Classificar componentes](/help/assets/icons/SortOrderDown.svg) para aplicar qualquer uma das seguintes opções de classificação:

   | Opção | Função |
   | --------- | ---------- |
   | [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
   | [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
   | [!UICONTROL **Categórico**] | Classifica componentes semelhantes a [!UICONTROL **Recomendado**], exceto que as métricas calculadas e as métricas padrão são agrupadas separadamente, em vez de serem misturadas. |

1. Adicione componentes à configuração do feed de dados. O painel esquerdo mostra apenas componentes válidos para feeds de dados.

   * **Arrastar e soltar**: arraste os componentes do painel esquerdo para a tela. Mantenha o **[!UICONTROL Shift]** pressionado, ou mantenha pressionado o **[!UICONTROL Command]** (macOS) ou o **[!UICONTROL Ctrl]** (Windows) para selecionar e arrastar vários componentes de uma só vez.
   * **Botão de adição**: selecione o ícone de adição ![Adicionar](/help/assets/icons/Add.svg) ao lado de qualquer componente no painel esquerdo para adicioná-lo à tela.
   * **[!UICONTROL Mostrar tudo]**: selecione **[!UICONTROL Mostrar tudo]** na parte inferior da lista de componentes para abrir uma caixa de diálogo mostrando todos os componentes disponíveis. Marque a caixa de seleção ao lado de cada componente que você deseja adicionar e selecione **[!UICONTROL Adicionar selecionado]**. Quando um termo de pesquisa ou uma marca de filtro está ativa no painel à esquerda, o botão **[!UICONTROL Adicionar tudo]** também é exibido, permitindo adicionar todos os resultados filtrados de uma só vez.

   Considere o seguinte ao adicionar campos:

   * Alguns componentes são obrigatórios, não são compatíveis ou têm restrições nos feeds de dados. Para obter detalhes, consulte [Disponibilidade de componentes em feeds de dados](/help/components/exports/cja-data-feeds/df-components.md).

   * Ao adicionar um componente que pertence a um campo de matriz XDM (por exemplo, um campo de proposta do Adobe Journey Optimizer) ou um campo de mapa, uma caixa de diálogo solicita que você adicione outros componentes do mesmo subcontêiner. Na saída do feed de dados, todos esses componentes aparecem em uma única coluna. Para obter mais informações, consulte [Componentes de subcontêiner em feeds de dados](/help/components/exports/cja-data-feeds/df-sub-event.md)

1. (Opcional) Reordene os componentes na tela arrastando-os. A ordem definida é preservada como a ordem das colunas no arquivo de feed de dados exportado.

1. (Opcional) Redimensione as colunas na tela de desenho arrastando a borda da coluna.

   As larguras de coluna são salvas em um cookie e persistem na próxima vez que você retornar a esse feed de dados no mesmo navegador.

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
   | [!UICONTROL **Frequência**]<br/> Disponível somente para feeds em tempo real | Selecione a frequência com que o feed de dados deve ser enviado. Eventos com carimbos de data e hora que caem na janela de frequência são incluídos na entrega do feed de dados. Os campos [!UICONTROL **Intervalo de datas de retrospectiva**] e [!UICONTROL **Atraso de processamento**] também podem afetar quais eventos são incluídos nos dados para a frequência de entrega escolhida.<p>Selecione para incluir dados de uma hora ou de um dia.</p><ul><li>**Diariamente**: os feeds contêm dados de um dia inteiro, da meia-noite a meia-noite no fuso horário da visualização de dados.</li><li>**Por hora**: os feeds contêm dados de uma hora.</li></ul> |
   | [!UICONTROL **Granularidade**]<br/> Disponível somente para feeds de preenchimento retroativo | O intervalo de tempo usado para dividir os dados históricos em partes. Cada bloco contém dados de um dia inteiro, da meia-noite à meia-noite no fuso horário da visualização de dados. <p>A granularidade determina como os dados são agrupados, não com que frequência são entregues. Os dados de preenchimento retroativo são entregues o mais rápido possível, não uma vez por dia.</p><p>Este campo é sempre definido como [!UICONTROL **Diariamente**] e não pode ser modificado.</p> |
   | [!UICONTROL **Intervalo de datas de retrospectiva**] | Controla até que data o Customer Journey Analytics analisa ao processar a entrega do feed de dados. O padrão é 30 dias.<p>A janela de frequência (hora ou dia) determina quais eventos são incluídos no feed de dados, enquanto o **intervalo de datas da retrospectiva** fornece o contexto histórico necessário para classificar esses eventos corretamente.</p><p>Qualificação de segmento, persistência de dimensão, cálculo de sessão e transformações de campo derivado podem afetar os eventos incluídos.</p> <p>Antes de configurar esta opção, veja os detalhes e os exemplos descritos na seção abaixo, [Entenda o intervalo de datas da retrospectiva](#data-feed-lookback-date-range).</p> |
   | [!UICONTROL **Atraso no processamento**] | Escolha o tempo que o Customer Journey Analytics aguarda antes de processar um arquivo de feed de dados. Todos os eventos de chegada tardia que chegam durante o atraso de processamento são incluídos no feed de dados. <p>O atraso mínimo de processamento é de 2 horas, mas alguns tipos de dados exigem um atraso mais longo. O atraso escolhido depende dos tipos de dados em sua conexão, como transmissão, lote, compilado, pesquisa ou dados de perfil.</p><p>Escolha um atraso suficientemente longo para que os dados mais lentos da conexão terminem o processamento. Se o atraso for muito curto, os dados que ainda estão sendo processados não serão incluídos no arquivo de feed de dados.</p><p>Antes de configurar esta opção, veja os detalhes e os exemplos descritos na seção abaixo, [Entenda o atraso de processamento](#data-feed-processing-delay).</p> |
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

## Noções básicas sobre o intervalo de datas da retrospectiva {#data-feed-lookback-date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="Intervalo de datas da retrospectiva"
>abstract="Controla até que data o Customer Journey Analytics analisa ao processar cada entrega.<p>A janela de frequência (hora ou dia) determina quais eventos são incluídos no feed de dados, enquanto o **intervalo de datas da retrospectiva** fornece o contexto histórico necessário para classificar esses eventos corretamente.</p><p>Qualificação de segmento, persistência de dimensão, cálculo de sessão e transformações de campo derivado podem afetar os eventos incluídos.</p><p>A retrospectiva mais longa melhora a precisão; a mais curta melhora o desempenho.</p>"

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

Os limites da sessão são calculados usando todos os eventos no intervalo de datas de retrospectiva, não apenas os eventos na janela de entrega. Uma sessão iniciada antes da janela de entrega ainda é reconhecida como a mesma sessão.

A ID da sessão é baseada na pessoa, na hora de início da sessão e nas configurações da sessão na visualização de dados. Uma sessão mantém a mesma ID de sessão em todos os deliveries, para que você possa ingressar em eventos de uma sessão que abrange vários deliveries por hora ou por dia.

Leve em consideração o seguinte ao trabalhar com sessões em feeds de dados:

* Se uma sessão começou antes do intervalo de datas da retrospectiva, seus eventos anteriores não estarão disponíveis, portanto, os valores da sessão podem ser diferentes do Analysis Workspace. Para obter mais informações, consulte [Entender as discrepâncias de dados entre os feeds de dados e o Analysis Workspace](/help/components/exports/cja-data-feeds/df-comparison-workspace.md).
* A alteração das configurações de sessão na visualização de dados altera as IDs de sessão. As IDs de sessão em deliveries posteriores não corresponderão às IDs de sessão em deliveries anteriores.

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

## Entender o atraso de processamento {#data-feed-processing-delay}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_processing_delay"
>title="Atraso no processamento"
>abstract="O tempo que o Customer Journey Analytics aguarda antes de processar um arquivo de feed de dados. Todos os eventos de chegada tardia que chegam durante o atraso de processamento são incluídos no feed de dados.<p>O atraso mínimo de processamento é de 2 horas, mas alguns tipos de dados exigem um atraso mais longo. Escolha um atraso suficientemente longo para que os dados mais lentos da sua conexão cheguem ao data lake da Experience Platform e sejam assimilados no Customer Journey Analytics. Se o atraso for muito curto, os dados que ainda estão sendo processados não serão incluídos no arquivo de feed de dados.</p><p>A costura pode levar até 4 horas. Para levar em conta isso, adicione 4 horas ao atraso para todos os dados compilados.</p>"

<!-- markdownlint-enable MD034 -->

### Como funciona o atraso de processamento

O atraso de processamento é o tempo que o Customer Journey Analytics aguarda antes de processar um arquivo de feed de dados. Todos os eventos de chegada tardia que chegam durante o atraso de processamento são incluídos no feed de dados.

Atrasos de processamento são necessários por vários motivos, como para levar em conta a latência do pipeline, para dar às implementações móveis uma oportunidade para que os dispositivos offline fiquem online e enviem dados ou para acomodar os processos do lado do servidor de sua organização no gerenciamento de arquivos processados anteriormente.

O atraso mínimo de processamento é de 2 horas, mas alguns tipos de dados exigem um atraso mais longo.

>[!BEGINSHADEBOX]

**Exemplo:**

Suponha que um feed de dados por hora inclua dados de 13h às 14h e o atraso de processamento seja de 2 horas. O processamento desse arquivo de feed de dados começa às 16h e inclui todos os dados que chegaram antes do início do processamento.

>[!ENDSHADEBOX]

### Escolha um atraso de processamento com base em seus dados

Tipos diferentes de dados levam períodos variáveis para serem disponibilizados no Customer Journey Analytics. Os dados passam por duas fases de processamento, e o tempo de cada fase soma-se ao total.

Escolha um atraso de processamento que seja longo o suficiente para que os dados mais lentos em sua conexão concluam ambas as fases. Se o atraso for muito curto, os dados que ainda estão sendo processados não serão incluídos no arquivo de feed de dados.

#### Fase 1: os dados chegam ao data lake da Experience Platform

Os tempos de chegada variam de acordo com o tipo de dados que você está coletando. Escolha um atraso que acomode o tipo de dados que você está coletando.

* **Conjuntos de dados de evento da Edge Network ou assimilação de streaming**: os dados normalmente chegam ao data lake em 60 minutos (consulte [Latências](/help/technotes/guardrails.md#latencies)).

* **Conjuntos de dados do conector de origem do Analytics**: os dados normalmente chegam ao data lake em 2,25 horas (consulte [Latências](/help/technotes/guardrails.md#latencies)).

  <!--When using the Analytics Source Connector, the minimum processing delay increases from 2 hours to 6 hours (?) to account for the source connector data. (checking to see if this is feasible) -->

* **Conjuntos de dados de outros conectores de origem**: a latência varia de acordo com o conector de origem e quando os lotes são enviados. O processamento de upstream no Experience Platform, como o Preparo de dados, pode adicionar mais tempo.

* **Conjuntos de dados de pesquisa**: o tempo para que os dados cheguem ao data lake depende da frequência com que os dados são carregados. Os dados de pesquisa normalmente são carregados como uma cópia completa de um banco de dados, no qual apenas uma pequena porcentagem de registros foi alterada. Faça upload de dados de pesquisa em lotes menores para reduzir o tempo de processamento.

  Em geral, pequenos uploads são processados dentro do atraso mínimo.

  Uploads grandes (por exemplo, um upload semanal de milhões de registros) são processados com prioridade mais baixa e podem levar de 3 a 4 horas a mais. No caso de uploads grandes, os dados do evento não são atrasados, mas os valores de pesquisa podem não refletir as atualizações mais recentes.

* **Conjuntos de dados de perfil**: o tempo para que os dados cheguem ao data lake depende da frequência com que os dados são carregados. Normalmente, os dados do perfil são assimilados em lotes grandes, como um instantâneo diário da tabela de perfil completa. Faça upload dos dados do perfil em lotes menores para reduzir o tempo de processamento.

  Em geral, pequenos uploads são processados dentro do atraso mínimo.

  Uploads grandes (por exemplo, um upload semanal de milhões de registros) são processados com prioridade mais baixa e podem levar de 3 a 4 horas a mais. No caso de uploads grandes, os dados do evento não são atrasados, mas os valores de perfil podem não refletir as atualizações mais recentes.

#### Fase 2: os dados são assimilados do data lake na Customer Journey Analytics

Os tempos de assimilação de dados variam dependendo se a compilação do conjunto de dados está ativada.

* **Conjuntos de dados não compilados**: isso pode levar até 90 minutos (consulte [Latências](/help/technotes/guardrails.md#latencies)).

* **Conjuntos de dados compilados**: a compilação pode adicionar até 4 horas além dos 90 minutos que leva para conjuntos de dados não compilados (consulte [Latências](/help/technotes/guardrails.md#latencies)). Se a compilação estiver ativada para a conexão, defina o atraso como pelo menos 6 horas e possivelmente 8 horas. Os dados atualizados por uma repetição de compilação geralmente não são incluídos em arquivos de feed de dados que já foram processados.

  Quando a compilação é ativada, o atraso mínimo de processamento aumenta de 2 horas para 6 horas para levar em conta os dados compilados.

>[!BEGINSHADEBOX]

**Exemplo:**

Se sua conexão incluir vários tipos de dados, escolha um atraso que acomode os dados mais lentos. No exemplo abaixo, são aproximadamente 8 horas.

A costura pode adicionar até 4 horas para assimilação no Customer Journey Analytics. Para levar em conta isso, adicione 4 horas ao atraso para todos os dados compilados.

| Fonte de dados | Fase 1: Chegada no data lake | Fase 2: Assimilação na Customer Journey Analytics | Total |
| --- | --- | --- | --- |
| Edge Network ou assimilação por transmissão | 60 minutos | 90 minutos <p>Sem compilação</p> | 2,5 horas |
| Conector de origem do Analytics | 2,25 horas | 90 minutos + 4 horas para compilação <p>Com a compilação</p> | 7,75 horas |

>[!ENDSHADEBOX]


