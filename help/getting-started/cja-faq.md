---
title: Perguntas frequentes sobre Customer Journey Analytics
description: Customer Journey Analytics - Perguntas frequentes.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: 91d9e473d38e12a7ba9cafea92c864641cebd206
workflow-type: ht
source-wordcount: '2371'
ht-degree: 100%

---

# Perguntas frequentes

[!UICONTROL O Customer Journey Analytics] (CJA) é nosso produto de análise de última geração. Veja a seguir respostas para perguntas frequentes sobre o CJA. Para obter mais informações, consulte [Suporte aos recursos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Pré-requisitos {#prerequisites}

| Pergunta | Resposta |
| --- | --- |
| Preciso do [!UICONTROL Private Device Graph] ou do [!UICONTROL Device Coop] para o [!UICONTROL Customer Journey Analytics]? | Não, o [!UICONTROL Private Device Graph] ou o [!UICONTROL Device Coop] não são necessários para o [!UICONTROL Customer Journey Analytics]. Na verdade, eles ainda não são compatíveis. |
| Preciso da [!UICONTROL Experience Cloud ID] (ECID) para o [!UICONTROL Customer Journey Analytics]? | Não, o [!UICONTROL Customer Journey Analytics] é compatível com qualquer ID em um conjunto de dados, seja [!UICONTROL ECID] ou outra ID escolhida. |
| E se for necessário extrair, transformar, carregar (ETL) meus dados antes do [!UICONTROL Customer Journey Analytics]? | O Customer Journey Analytics inclui recursos de [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=pt-BR) para ajudar a transformar seus dados antes de colocá-los no data lake da Adobe Experience Platform. Se ETL for necessário depois que os dados já tiverem sido assimilados, o [Serviço de consulta da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=pt-BR#queries) fornecerá algumas opções limitadas, embora possa haver a cobrança de tarifas adicionais. |

{style=&quot;table-layout:auto&quot;}

## 2. Compilação de dados (Cross-Channel Analytics) {#stitching}

| Pergunta | Resposta |
| --- | --- |
| O [!UICONTROL Customer Journey Analytics] pode &quot;costurar&quot; todos os dispositivos ou conjuntos de dados? | Sim. [!UICONTROL O Customer Journey Analytics] tem uma solução de compilação chamada [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR) (CCA). Ele permite alterar a chave da ID de pessoa de um conjunto de dados, o que possibilita realizar uma combinação perfeita de vários conjuntos de dados. |
| A costura de comportamento anônimo para comportamento autenticado é compatível? | Sim. [O Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR) analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada. |
| Como a &quot;repetição&quot; funciona no CCA? | O CCA “repete” dados com base em identificadores exclusivos que ele aprendeu. A repetição faz com que novos dispositivos da conexão sejam compilados. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=pt-BR#step-1%3A-live-stitching) |
| Como a compilação de dados históricos (preenchimento retroativo) funciona no CCA? | Quando ativado pela primeira vez, a Adobe fornece um preenchimento retroativo de dados compilados que retorna até o início do mês anterior (até 60 dias). Para fazer esse preenchimento retroativo, a ID transitória deve existir nos dados não compilados até aquele momento. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR#enable-cross-channel-analytics) |
| Qual é o comportamento esperado para registros de conjunto de dados de perfil não compilados? | **Exemplo de cenário**: você associa dois conjuntos de dados em uma conexão do CJA usando `CRMid` como a ID de pessoa. Um é um conjunto de dados de Evento da Web com `CRMid` em todos os registros. O outro conjunto de dados é um conjunto de dados de perfil do CRM. 40% do conjunto de dados do CRM tem `CRMid` presente no conjunto de dados do evento web. Os outros 60% não estão presentes no conjunto de dados de eventos da Web. Esses registros aparecem nos relatórios no Analysis Workspace?<p> **Resposta**: as linhas de perfil que não têm eventos vinculados a elas são armazenadas no CJA. No entanto, não é possível visualizá-las no Analysis Workspace até que um evento vinculado a essa ID seja exibido. |

{style=&quot;table-layout:auto&quot;}

## 3. Obtenção de dados no [!UICONTROL Customer Journey Analytics] {#ingest}

| Pergunta | Resposta |
| --- | --- |
| É possível combinar dados de diferentes sandboxes da [!UICONTROL Adobe Experience Platform] em uma conexão do [!UICONTROL Customer Journey Analytics]? | Não, não é possível acessar dados em sandboxes. É possível combinar somente conjuntos de dados localizados na mesma sandbox. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#select-sandbox-and-datasets) |
| Como conectar os dados online aos dados offline no [!UICONTROL Customer Journey Analytics]? | Contanto que a ID de pessoa corresponda entre os conjuntos de dados, o [!UICONTROL Customer Journey Analytics] pode conectar filtros, atribuição, fluxo, fallout etc. em todos os conjuntos de dados. |
| Como posso trazer meus dados offline para o [!UICONTROL Customer Journey Analytics]? | Seu direito ao Customer Journey Analytics permite assimilar dados na Experience Platform. Em seguida, você pode criar conexões com esses dados e visualizações de dados no [!UICONTROL Customer Journey Analytics] para criar relatórios no Analysis Workspace. A equipe de integração de dados da Experience Platform pode ajudar a fornecer recomendações ou consultoria a você, se necessário. |
| Como posso obter dados do [!UICONTROL Adobe Analytics] no [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Os dados do Adobe Analytics] podem ser conectados à Experience Platform por meio do [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). A maioria dos campos do [!UICONTROL Adobe Analytics] está no formato XDM, mas outros campos ainda não estão disponíveis. |
| Qual é o tempo de montagem dos elementos do conjunto de dados em uma exibição de dados? | Algumas horas para começar e alguns dias para preencher retroativamente os últimos 13 meses de dados. |
| É necessário trazer os dados de PII para estabelecer as conexões entre os dados? | Não, você pode usar qualquer ID, incluindo um hash de uma ID do cliente, que não seja PII. |
| Quais são os limites para assimilação de datas/carimbos de data e hora passados ou futuros em conjuntos de dados de eventos do CJA? | <ul><li>Em relação a datas/carimbos de data e hora anteriores: dados de evento com até 10 anos.</li><li>Em relação a datas/carimbos de data e hora futuros: dados de evento (preditivo) até 1 mês no futuro.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## 4. Considerações sobre latência {#latency}

>[!NOTE]
>Não há tamanho de dados fixo no CJA e, portanto, a Adobe não pode se comprometer com um tempo de ingestão padrão. Estamos trabalhando ativamente para reduzir essas latências por meio de novas atualizações e otimização de assimilação.

| Pergunta | Resposta |
| --- | --- |
| Qual é a latência esperada para o [!UICONTROL Customer Journey Analytics] na [!UICONTROL Adobe Experience Platform]? | <ul><li>Dados ou eventos ao vivo: processados e assimilados em 90 minutos, quando os dados estiverem disponíveis no AEP. (Tamanho do lote > 50 milhões de linhas: superior a 90 minutos.)</li><li>Pequenos preenchimentos retroativos - Por exemplo, um conjunto de dados de pesquisa de 10 milhões de linhas: no prazo de 7 dias<li>Preenchimentos retroativos grandes - Por exemplo, 500 bilhões de linhas: 30 dias</li></ul> |

## 5. Definir janela contínua para retenção de dados de [!UICONTROL Conexão] {#data-retention}

A configuração [**[!UICONTROL Ativar janela de dados contínuos ]**](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#create-connection) permite definir a retenção de dados do CJA como uma janela contínua em meses (3 meses, 6 meses etc.). Ela é definida no nível de uma [!UICONTROL conexão], não no nível de um [!UICONTROL conjunto de dados]. A retenção de dados tem por base os carimbos de data e hora do conjunto de dados do evento e se aplica somente aos conjuntos de dados do evento. Não há configuração de retenção de dados para o perfil ou conjuntos de dados de pesquisa, pois não há carimbos de data e hora aplicáveis.

O principal benefício é armazenar ou relatar apenas dados que sejam aplicáveis e úteis, além de excluir dados mais antigos que não sejam mais úteis. Isso ajuda você a ficar dentro dos limites do contrato e reduz o risco de custo excedente.

## 6. Implicações da exclusão de componentes de dados {#deletion}

Quando se trata de exclusão, nos referimos a seis tipos de componentes: sandbox, esquema, conjunto de dados, conexão, visualização de dados e projetos do Espaço de trabalho. Veja alguns cenários possíveis para excluir qualquer um desses componentes:

| Se você... | Isso acontece... |
| --- | --- |
| Excluir uma sandbox na [!UICONTROL Adobe Experience Platform] | A exclusão de uma sandbox interromperá o fluxo de dados para qualquer conexão do [!UICONTROL Customer Journey Analytics] com conjuntos de dados nessa sandbox. Atualmente, as [!UICONTROL Conexões] no CJA vinculadas à sandbox excluída não serão automaticamente excluídas. |
| Excluir um esquema na [!UICONTROL Adobe Experience Platform], mas não os conjuntos de dados associados a esse esquema | [!UICONTROL A Adobe Experience Platform] não permite a exclusão de [!UICONTROL esquemas] que tenham um ou mais [!UICONTROL conjuntos de dados] associados a eles. No entanto, um Administrador com o conjunto apropriado de direitos pode excluir os conjuntos de dados primeiro e, em seguida, excluir o esquema. |
| Excluir um conjunto de dados no data lake da [!UICONTROL Adobe Experience Platform] | A exclusão de um conjunto de dados na AEP interromperá o fluxo de dados desse conjunto de dados para qualquer Conexão do CJA que inclua esse conjunto de dados. Quaisquer dados desse conjunto de dados são excluídos automaticamente das Conexões associadas do CJA. |
| Excluir um conjunto de dados no [!UICONTROL Customer Journey Analytics] | Entre em contato com o Gerente de conta da Adobe para iniciar o processo de exclusão de um conjunto de dados em uma conexão que foi salva. |
| Excluir um lote de um conjunto de dados (na [!UICONTROL Adobe Experience Platform]) | Se um lote for excluído de um conjunto de dados da [!UICONTROL Adobe Experience Platform], o mesmo lote será removido de qualquer Conexão do CJA que contenha esse lote específico.  O CJA é notificado de exclusões em lote na [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto ele estiver sendo assimilado** no [!UICONTROL Customer Journey Analytics] | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido no [!UICONTROL Customer Journey Analytics]. A assimilação será revertida. Por exemplo, se houver cinco lotes no conjunto de dados e três deles já tiverem sido assimilados quando o conjunto de dados tiver sido excluído, os dados desses três lotes aparecerão no [!UICONTROL Customer Journey Analytics]. |
| Excluir uma conexão no [!UICONTROL Customer Journey Analytics] | Uma mensagem de erro indicará que:<ul><li>Qualquer visualização de dados criada para a conexão excluída não funcionará mais.</li><li> Da mesma forma, qualquer projeto do Espaço de trabalho que dependa de visualizações de dados na conexão excluída deixará de funcionar.</li></ul> |
| Excluir uma visualização de dados no [!UICONTROL Customer Journey Analytics] | Uma mensagem de erro indicará que todos os projetos do Espaço de trabalho que dependem dessa visualização de dados excluída deixarão de funcionar. |

## 7. Considerações ao mesclar conjuntos de relatórios no CJA {#merge-reportsuite}

Caso planeje assimilar dados do Adobe Analytics por meio do [conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR), considere essas ramificações ao mesclar dois ou mais conjuntos de relatórios do Adobe Analytics.

| Problema | Consideração |
| --- | --- |
| Variáveis | Variáveis como [!UICONTROL eVars] podem não se alinhar em conjuntos de relatórios. Por exemplo, a eVar1 no conjunto de relatórios 1 pode apontar para **[!UICONTROL Página]**. No conjunto de relatórios 2, a eVar1 pode apontar para **[!UICONTROL Campanha interna]**, gerando relatórios mistos e imprecisos. |
| Contagens de [!UICONTROL Sessões] e [!UICONTROL Pessoas] | Elas são desduplicadas em conjuntos de relatórios. Como resultado, as contagens podem não corresponder. |
| Desduplicação de métrica | Desduplica instâncias de uma métrica (por exemplo, [!UICONTROL Pedidos]) se várias linhas tiverem a mesma ID de transação (por exemplo, [!UICONTROL ID de compra]). Isso evita a contagem excessiva de métricas principais. Como resultado, métricas como [!UICONTROL Pedidos] podem não se corresponder em conjuntos de relatórios. |
| Moeda | A conversão de moeda ainda não é compatível com o CJA. Se os conjuntos de relatórios que você está tentando mesclar usarem moedas base diferentes, podem ocorrer problemas. |
| [!UICONTROL Persistência] | A [Persistência](../data-views/component-settings/persistence.md) se estende pelos conjuntos de relatórios, o que afeta os [!UICONTROL filtros], a [!UICONTROL atribuição] e assim por diante. Os números podem não ser correspondidos corretamente. |
| [!UICONTROL Classificações] | As [!UICONTROL Classificações] não são automaticamente desduplicadas ao mesclar conjuntos de relatórios. Ao combinar vários arquivos de classificações em um único conjunto de dados de [!UICONTROL pesquisa], você pode encontrar problemas. |


## 8. Componentes tradicionais do [!UICONTROL Adobe Analytics]

| Pergunta | Resposta |
| --- | --- |
| É possível compartilhar/publicar [!UICONTROL filtros] ([!UICONTROL segmentos]) do [!DNL Customer Journey Analytics] no Perfil unificado da Experience Platform ou em outros aplicativos da Experience Cloud? | Ainda não, mas estamos trabalhando ativamente para fornecer esse recurso. |
| O que aconteceu com minha antiga configuração de [!UICONTROL eVar]? | [!UICONTROL eVars], [!UICONTROL props] e [!UICONTROL eventos] no sentido tradicional do Adobe Analytics não existem mais no [!UICONTROL Customer Journey Analytics]. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta. |
| Onde estão todas as minhas configurações de sessão e persistência de variável agora? | [!UICONTROL O Customer Journey Analytics] aplica todas essas configurações no momento do relatório e essas configurações agora residem na Exibição de dados. As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados! |
| O que acontece com nossos segmentos/métricas calculadas atuais? | [!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhum dos segmentos ou métricas calculadas existentes é compatível com o [!UICONTROL Customer Journey Analytics]. |
| Como o [!UICONTROL Customer Journey Analytics] lida com `Uniques Exceeded` limitações? | [!UICONTROL O Customer Journey Analytics] não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas! |
| Se eu for um [!DNL Data Workbench] cliente atual, posso migrar para o [!UICONTROL Customer Journey Analytics] agora? | Depende do seu caso de uso. Entre em contato com a equipe de conta da Adobe. Seus casos de uso atuais já podem ser adequados para o Customer Journey Analytics. |

{style=&quot;table-layout:auto&quot;}

## 9. Estimar tamanho da conexão {#estimate-size}

Talvez seja necessário saber quantas linhas de dados você tem atualmente no [!UICONTROL Customer Journey Analytics]. Para obter uma conta precisa do uso dos registros de dados de evento (linhas de dados) de sua organização, faça o seguinte **para cada uma das conexões criadas pela organização**.

1. No [!UICONTROL Customer Journey Analytics], clique na guia **[!UICONTROL Conexões]**.

   Agora você pode ver uma lista de todas as conexões atuais.

1. Clique em cada nome de conexão para acessar o Gerenciador de conexões.

1. Adicione o **[!UICONTROL Registros dos dados do evento disponíveis]** para todas as conexões criadas. (Dependendo do tamanho da conexão, o número pode levar algum tempo para ser exibido.)

   ![dados do evento](assets/event-data.png)

1. Depois de ter uma soma de todas as linhas de dados do evento, procure o direito de “Linhas de dados” no contrato do Customer Journey Analytics que sua empresa assinou com a Adobe.

   Isso fornece o número máximo de linhas de dados autorizadas na Ordem de venda. Se o número de linhas de dados resultante da Etapa 3 for maior que esse número, você está incorrendo em um excedente.

1. Para corrigir essa situação, você tem várias opções:

   * Alterar as [configurações de retenção de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=pt-BR#set-rolling-window-for-connection-data-retention).
   * [Excluir todas as conexões não usadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#implications-of-deleting-data-components).
   * [Excluir um conjunto de dados na AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#implications-of-deleting-data-components).
   * Entre em contato com o Gerente de conta da Adobe para obter licença de capacidade adicional.

## 10. Em relação às sobreposições de uso {#overage}

Os limites de uso são monitorados e aplicados regularmente pela Adobe. “Linhas de dados” são as linhas médias diárias de dados disponíveis para análise no Customer Journey Analytics.

Por exemplo, digamos que o seu contrato dê direito a um milhão de linhas de dados. Suponha que, no primeiro dia de uso do Customer Journey Analytics, você carregue dois milhões de linhas de dados. No dia 2, você exclui 1 milhão de linhas e mantém seu uso no máximo permitido (ou seja, um milhão de linhas de dados) para o restante do Prazo da licença. Dependendo dos termos contratuais, você ainda poderá incorrer em taxas de uso excessivo proporcionais em relação ao dia 1, já que você excedeu o direito de licença de “linhas de dados”.

## 11. Diagnosticar discrepâncias de dados {#discrepancies}

Em alguns casos, você pode notar que o número total de eventos assimilados pela sua conexão é diferente do número de linhas no conjunto de dados na [!UICONTROL Adobe Experience Platform]. Neste exemplo, o conjunto de dados &quot;Impressão B2B&quot; tem 7650 linhas, mas o conjunto de dados contém 3830 linhas na [!UICONTROL Adobe Experience Platform]. Há várias razões pelas quais podem ocorrer discrepâncias, e as seguintes etapas podem ser executadas para diagnosticar:

1. Detalhe essa dimensão por **[!UICONTROL ID do conjunto de dados da Plataform]** e você observará dois conjuntos de dados com o mesmo tamanho, mas diferentes **[!UICONTROL IDs do conjunto de dados do Platform]**. Cada conjunto de dados tem 3825 registros. Isso significa que o [!UICONTROL Customer Journey Analytics] ignorou cinco registros devido a IDs de pessoa ausentes ou a carimbos de data e hora ausentes:

   ![detalhamento](assets/data-size2.png)

1. Além disso, se verificarmos a [!UICONTROL Adobe Experience Platform], não há conjunto de dados com a ID &quot;5f21c12b732044194bffc1d0&quot;, portanto, alguém excluiu esse conjunto de dados específico da [!UICONTROL Adobe Experience Platform] quando a conexão inicial estava sendo criada. Mais tarde, ele foi adicionado ao Customer Journey Analytics novamente, mas uma [!UICONTROL ID do conjunto de dados da plataforma] diferente foi gerada pela [!UICONTROL Adobe Experience Platform].

Leia mais sobre as [implicações do conjunto de dados e a exclusão de conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#implications-of-deleting-data-components) no [!UICONTROL Customer Journey Analytics] e na [!UICONTROL Adobe Experience Platform].
