---
title: Perguntas frequentes sobre Customer Journey Analytics
description: Customer Journey Analytics - Perguntas frequentes.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: 2412b2b3d6c0abf29c2d265ba60668c3e4a12936
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Perguntas frequentes

[!UICONTROL O Customer Journey Analytics] (CJA) é nosso produto de análise de última geração. Veja a seguir respostas para perguntas frequentes sobre o CJA. Para obter mais informações, consulte [Suporte aos recursos do Customer Journey Analytics](/help/getting-started/cja-aa.md).

## 1. Pré-requisitos

| Pergunta | Resposta |
| --- | --- |
| Preciso do [!UICONTROL Private Device Graph] ou do [!UICONTROL Device Coop] para o [!UICONTROL Customer Journey Analytics]? | Não, o [!UICONTROL Private Device Graph] ou o [!UICONTROL Device Coop] não são necessários para o [!UICONTROL Customer Journey Analytics]. Na verdade, eles ainda não são compatíveis. |
| Preciso da [!UICONTROL Experience Cloud ID] (ECID) para o [!UICONTROL Customer Journey Analytics]? | Não, o [!UICONTROL Customer Journey Analytics] é compatível com qualquer ID em um conjunto de dados, seja [!UICONTROL ECID] ou outra ID escolhida. |
| E se for necessário extrair, transformar, carregar (ETL) meus dados antes do [!UICONTROL Customer Journey Analytics]? | O Customer Journey Analytics inclui recursos de [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=pt-BR) para ajudar a transformar seus dados antes de colocá-los no data lake da Adobe Experience Platform. Se ETL for necessário depois que os dados já tiverem sido assimilados, o [Serviço de consulta da Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=pt-BR#queries) fornecerá algumas opções limitadas, embora possa haver a cobrança de tarifas adicionais. |

{style=&quot;table-layout:auto&quot;}

## 2. Compilação de dados (Cross-Channel Analytics)

| Pergunta | Resposta |
| --- | --- |
| O [!UICONTROL Customer Journey Analytics] pode &quot;costurar&quot; todos os dispositivos ou conjuntos de dados? | Sim. [!UICONTROL O Customer Journey Analytics] tem uma solução de compilação chamada [Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR) (CCA). Ela permite alterar a chave da ID pessoal de um conjunto de dados, o que permite a combinação perfeita de vários conjuntos de dados. |
| A costura de comportamento anônimo para comportamento autenticado é compatível? | Sim. [O Cross-Channel Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) analisa os dados do usuário de sessões autenticadas e não autenticadas para gerar uma ID compilada. |
| Como a &quot;repetição&quot; funciona no CCA? | O CCA “repete” dados com base em identificadores exclusivos que ele aprendeu. A repetição faz com que novos dispositivos da conexão sejam compilados. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=pt-BR#etapa-1%3A-compila%C3%A7%C3%A3o-em-tempo-real) |
| Como a compilação de dados históricos (preenchimento retroativo) funciona no CCA? | Quando ativado pela primeira vez, a Adobe fornece um preenchimento retroativo de dados compilados que retorna até o início do mês anterior (até 60 dias). Para fazer esse preenchimento retroativo, a ID transitória deve existir nos dados não compilados até aquele momento. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=pt-BR#habilitar-a-an%C3%A1lise-de-v%C3%A1rios-canais) |

{style=&quot;table-layout:auto&quot;}

## 3. Obtenção de dados no [!UICONTROL Customer Journey Analytics]

| Pergunta | Resposta |
| --- | --- |
| É possível combinar dados de diferentes sandboxes da [!UICONTROL Adobe Experience Platform] em uma conexão do [!UICONTROL Customer Journey Analytics]? | Não, não é possível acessar dados em sandboxes. É possível combinar somente conjuntos de dados localizados na mesma sandbox. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#select-sandbox-and-datasets) |
| Como conectar os dados online aos dados offline no [!UICONTROL Customer Journey Analytics]? | Contanto que a ID de pessoa corresponda entre os conjuntos de dados, o [!UICONTROL Customer Journey Analytics] pode conectar filtros, atribuição, fluxo, fallout etc. em todos os conjuntos de dados. |
| Como posso trazer meus dados offline para o [!UICONTROL Customer Journey Analytics]? | Seu direito ao Customer Journey Analytics permite assimilar dados na Experience Platform. Em seguida, você pode criar conexões com esses dados e visualizações de dados no [!UICONTROL Customer Journey Analytics] para criar relatórios no Analysis Workspace. A equipe de integração de dados da Experience Platform pode ajudar a fornecer recomendações ou consultoria a você, se necessário. |
| Como posso obter dados do [!UICONTROL Adobe Analytics] no [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Os dados do Adobe Analytics] podem ser conectados à Experience Platform por meio do [Conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR). A maioria dos campos do [!UICONTROL Adobe Analytics] está no formato XDM, mas outros campos ainda não estão disponíveis. |
| Qual é o tempo de montagem dos elementos do conjunto de dados em uma exibição de dados? | Algumas horas para começar e alguns dias para preencher retroativamente os últimos 13 meses de dados. |
| É necessário trazer os dados de PII para estabelecer as conexões entre os dados? | Não, você pode usar qualquer ID, incluindo um hash de uma ID do cliente, que não seja PII. |

{style=&quot;table-layout:auto&quot;}

## 4. Considerações de latência

>[!NOTE]
>Não há tamanho de dados fixo no CJA e, portanto, o Adobe não pode se comprometer com um tempo de ingestão padrão. Estamos trabalhando ativamente para reduzir essas latências por meio de novas atualizações e otimização de assimilação.

| Pergunta | Resposta |
| --- | --- |
| Qual é a latência esperada para o [!UICONTROL Customer Journey Analytics] na [!UICONTROL Adobe Experience Platform]? | <ul><li>Dados ou eventos ao vivo: Processados e assimilados em 90 minutos, quando os dados estiverem disponíveis no AEP.</li><li>Tamanho do lote > 50 milhões de linhas: superior a 90 minutos.</li><li>Pequenos preenchimentos retroativos - Por exemplo, um conjunto de dados de pesquisa de 10 milhões de linhas: no prazo de 24 horas<li>Preenchimentos retroativos grandes - Por exemplo, 500 bilhões de linhas: 30 dias</li></ul> |


## 5. Componentes tradicionais do [!UICONTROL Adobe Analytics]

| Pergunta | Resposta |
| --- | --- |
| É possível compartilhar/publicar filtros (segmentos) do Customer Journey Analytics no Experience Platform Unified Profile ou em outros aplicativos da Experience Cloud? | Ainda não, mas estamos trabalhando ativamente para fornecer esse recurso. |
| O que aconteceu com minha antiga configuração do eVar? | eVars, props e eventos no sentido tradicional do Adobe Analytics não existem mais no [!UICONTROL Customer Journey Analytics]. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta. |
| Onde estão todas as minhas configurações de sessão e persistência de variável agora? | [!UICONTROL O Customer Journey Analytics] aplica todas essas configurações no momento do relatório e essas configurações agora residem na Exibição de dados. As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados! |
| O que acontece com nossos segmentos/métricas calculadas atuais? | [!UICONTROL O Customer Journey Analytics] não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhum dos segmentos ou métricas calculadas existentes é compatível com o [!UICONTROL Customer Journey Analytics]. |
| Como o [!UICONTROL Customer Journey Analytics] lida com `Uniques Exceeded` limitações? | [!UICONTROL O Customer Journey Analytics] não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas! |
| Se eu for um [!DNL Data Workbench] cliente atual, posso migrar para o [!UICONTROL Customer Journey Analytics] agora? | Depende do seu caso de uso. Entre em contato com a equipe de conta da Adobe. Seus casos de uso atuais já podem ser adequados para o Customer Journey Analytics. |

{style=&quot;table-layout:auto&quot;}

## 6. Implicações da exclusão de componentes de dados

Quando se trata de exclusão, nos referimos a seis tipos de componentes: sandbox, esquema, conjunto de dados, conexão, visualização de dados e projetos do Workspace. Veja alguns cenários possíveis para excluir qualquer um desses componentes:

| Se você... | Isso acontece... |
| --- | --- |
| Excluir uma sandbox na [!UICONTROL Adobe Experience Platform] | A exclusão de uma sandbox interromperá o fluxo de dados para qualquer conexão do [!UICONTROL Customer Journey Analytics] com conjuntos de dados nessa sandbox. Atualmente, as Conexões no CJA vinculadas à sandbox excluída não serão automaticamente excluídas. |
| Excluir um esquema na [!UICONTROL Adobe Experience Platform], mas não os conjuntos de dados associados a esse esquema | [!UICONTROL A Adobe Experience Platform] não permite a exclusão de esquemas que tenham um ou mais conjuntos de dados associados a eles. No entanto, um Administrador com o conjunto apropriado de direitos pode excluir os conjuntos de dados primeiro e, em seguida, excluir o esquema. |
| Excluir um conjunto de dados no data lake da [!UICONTROL Adobe Experience Platform] | A exclusão de um conjunto de dados na AEP interromperá o fluxo de dados desse conjunto de dados para qualquer Conexão do CJA que inclua esse conjunto de dados. Quaisquer dados desse conjunto de dados não são excluídos automaticamente das Conexões associadas do CJA. |
| Excluir um conjunto de dados no [!UICONTROL Customer Journey Analytics] | Atualmente, não é possível excluir um conjunto de dados em uma conexão que foi salva. Você teria que excluir toda a conexão e começar novamente. (No entanto, os clientes que compraram o SKU do CJA podem excluir um conjunto de dados na interface do usuário da [!UICONTROL Adobe Experience Platform].) |
| Excluir um lote de um conjunto de dados (na [!UICONTROL Adobe Experience Platform]) | Se um lote for excluído de um conjunto de dados da [!UICONTROL Adobe Experience Platform], o mesmo lote será removido de qualquer Conexão do CJA que contenha esse lote específico.  O CJA é notificado de exclusões em lote na [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto ele estiver sendo assimilado** no [!UICONTROL Customer Journey Analytics] | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido no [!UICONTROL Customer Journey Analytics]. A assimilação será revertida. Por exemplo, se houver cinco lotes no conjunto de dados e três deles já tiverem sido assimilados quando o conjunto de dados tiver sido excluído, os dados desses três lotes aparecerão no [!UICONTROL Customer Journey Analytics]. |
| Excluir uma conexão no [!UICONTROL Customer Journey Analytics] | Uma mensagem de erro indicará que:<ul><li>Qualquer visualização de dados criada para a conexão excluída não funcionará mais.</li><li> Da mesma forma, qualquer projeto do Workspace que dependa de visualizações de dados na conexão excluída deixará de funcionar.</li></ul> |
| Excluir uma visualização de dados no [!UICONTROL Customer Journey Analytics] | Uma mensagem de erro indicará que todos os projetos do Workspace que dependem dessa visualização de dados excluída deixarão de funcionar. |

## 7. Considerações ao mesclar conjuntos de relatórios no CJA

Caso planeje assimilar dados do Adobe Analytics por meio do [conector de origem do Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=pt-BR), considere essas ramificações ao mesclar dois ou mais conjuntos de relatórios do Adobe Analytics.

| Problema | Consideração |
| --- | --- |
| Variáveis | Variáveis como [!UICONTROL eVars] podem não se alinhar em conjuntos de relatórios. Por exemplo, a eVar1 no conjunto de relatórios 1 pode apontar para **[!UICONTROL Página]**. No conjunto de relatórios 2, a eVar1 pode apontar para **[!UICONTROL Campanha interna]**, gerando relatórios mistos e imprecisos. |
| Contagens de [!UICONTROL Sessões] e [!UICONTROL Pessoas] | Elas são desduplicadas em conjuntos de relatórios. Como resultado, as contagens podem não corresponder. |
| Desduplicação de métrica | Desduplica instâncias de uma métrica (por exemplo, [!UICONTROL Pedidos]) se várias linhas tiverem a mesma ID de transação (por exemplo, [!UICONTROL ID de compra]). Isso evita a contagem excessiva de métricas principais. Como resultado, métricas como [!UICONTROL Pedidos] podem não se corresponder em conjuntos de relatórios. |
| Moeda | A conversão de moeda ainda não é compatível com o CJA. Se os conjuntos de relatórios que você está tentando mesclar usarem moedas base diferentes, podem ocorrer problemas. |
| [!UICONTROL Persistência] | A [Persistência](../data-views/component-settings/persistence.md) se estende pelos conjuntos de relatórios, o que afeta os [!UICONTROL filtros], a [!UICONTROL atribuição] e assim por diante. Os números podem não ser correspondidos corretamente. |
| [!UICONTROL Classificações] | As [!UICONTROL Classificações] não são automaticamente desduplicadas ao mesclar conjuntos de relatórios. Ao combinar vários arquivos de classificações em um único conjunto de dados de [!UICONTROL pesquisa], você pode encontrar problemas. |