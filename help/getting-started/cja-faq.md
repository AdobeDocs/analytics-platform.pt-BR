---
title: Perguntas frequentes sobre Customer Journey Analytics
description: Customer Journey Analytics - Perguntas frequentes.
translation-type: tm+mt
source-git-commit: 3b3d0b0858d559e94f1bed6a31a63b018ed32a23
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 40%

---


# Perguntas frequentes

## Pré-requisitos

| Pergunta | Resposta |
| --- | --- |
| Eu preciso [!UICONTROL Gráfico de dispositivos privados] ou [!UICONTROL Device Coop] for [!UICONTROL Customer Journey Analytics]? | Não, [!UICONTROL Gráfico de dispositivos privados] ou [!UICONTROL Device Coop] não é obrigatório para [!UICONTROL Customer Journey Analytics]. Na verdade, eles ainda não são compatíveis. |
| Eu preciso [!UICONTROL Experience Cloud ID] (ECID) para [!UICONTROL Customer Journey Analytics]? | Não, o [!UICONTROL Customer Journey Analytics] é compatível com qualquer ID em um conjunto de dados, seja ECID ou outra ID escolhida. |
| E se eu precisar ETL (Extrair, Transformar, Carregar) meus dados antes de [!UICONTROL Customer Journey Analytics]? | Atualmente, você precisa trabalhar com um parceiro de ETL (Unifi ou Informatica) se for necessário transformar os dados antes de colocá-los na AEP. Se precisar de ETL depois que os dados já tiverem sido ingeridos, [!UICONTROL Serviços de Query Adobe Experience Platform] fornece algumas opções limitadas. |

## Como corrigir dados

| Pergunta | Resposta |
| --- | --- |
| O [!UICONTROL Customer Journey Analytics] pode &quot;costurar&quot; todos os dispositivos ou conjuntos de dados? | Sim. O [!UICONTROL Customer Journey Analytics] é um sistema de análise &quot;traga sua própria ID&quot;. Lançamos uma solução de costura em novembro de 2020. Saiba mais. |
| A costura de comportamento anônimo para comportamento autenticado é compatível? | Não, ainda não. |

## Obtenção de dados para o [!UICONTROL Customer Journey Analytics]

| Pergunta | Resposta |
| --- | --- |
| É possível combinar dados de diferentes [!UICONTROL Adobe Experience Platform] caixas de proteção em uma [!UICONTROL Customer Journey Analytics] conexão? | Não, não é possível acessar dados em sandboxes. É possível combinar somente conjuntos de dados localizados na mesma sandbox. [Saiba mais...](https://docs.adobe.com/content/help/pt-BR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Qual é a latência esperada para [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>Em carga normal: &lt; 60 minutos <br>**Observação:** no caso de um volume de dados excepcionalmente elevado por meio do pipeline, poderá demorar até 24 horas.</li><li>Dados de preenchimento retroativo (até 13 meses de dados, independentemente do tamanho): &lt; 4 semanas</li></ul> |
| Como conectar os dados online aos dados offline no [!UICONTROL Customer Journey Analytics]? | O [!UICONTROL Customer Journey Analytics] é um sistema de análise &quot;traga sua própria ID&quot;. Contanto que a ID da pessoa corresponda entre os conjuntos de dados, o [!UICONTROL Customer Journey Analytics] pode conectar segmentos, atribuição, fluxo, fallout, etc. em todos os conjuntos de dados. |
| Como faço para trazer meus dados offline para [!UICONTROL Customer Journey Analytics]? | Primeiro, você deve trazer quaisquer dados para o Experience Platform antes de usá-los com [!UICONTROL Customer Journey Analytics]. A equipe de integração de dados da Experience Platform pode ajudar a fornecer recomendações ou consultoria a você, se necessário. |
| Como faço para obter [!UICONTROL Adobe Analytics] dados em [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] os dados podem ser conectados à Experience Platform através da variável [Conector de origem Adobe Analytics](https://docs.adobe.com/content/help/pt-BR/experience-platform/sources/connectors/adobe-applications/analytics.html). Mais [!UICONTROL Adobe Analytics] são trazidos para o formato XDM, mas outros campos ainda não estão disponíveis (como [!UICONTROL Canais de marketing] dimensões). |
| Qual é o tempo de montagem dos elementos do conjunto de dados em uma exibição de dados? | Algumas horas para começar e alguns dias para preencher retroativamente os últimos 13 meses de dados. |
| É necessário trazer os dados de PII para estabelecer as conexões entre os dados? | Não, você pode usar qualquer ID, incluindo um hash de uma ID do cliente, que não seja PII. |

## Tradicional [!UICONTROL Adobe Analytics] componentes

| Pergunta | Resposta |
| --- | --- |
| O que isso significa para o nosso tradicional [!UICONTROL Adobe Analytics] produto? | [!UICONTROL O Customer Journey Analytics é nosso produto de análise da próxima geração. ] Evoluindo de nossos produtos atuais para [!UICONTROL Customer Journey Analytics] levará anos e muita coordenação. Para obter mais informações, consulte [Suporte aos recursos do Customer Journey Analytics](/help/getting-started/cja-aa.md). |
| Posso compartilhar segmentos de [!UICONTROL Customer Journey Analytics] para AEP ou outras soluções? | Ainda não. Estamos procurando formas novas e inovadoras de compartilhar segmentos do [!UICONTROL Customer Journey Analytics] para a AEP no futuro que não tem um atraso tão grande. Dito isso, você pode compartilhar a saída dos Serviços de consulta com o Perfil unificado, como uma possível solução alternativa. |
| O que aconteceu com minha antiga configuração do eVar? | eVars, props e eventos no sentido Adobe Analytics tradicional não existem mais em [!UICONTROL Customer Journey Analytics]. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta. |
| Onde estão todas as minhas configurações de sessão e persistência de variável agora? | [!UICONTROL O Customer Journey Analytics aplica todas essas configurações no momento do relatório e essas configurações agora residem na Exibição de dados. ] As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados! |
| O que acontece com nossos segmentos/métricas calculadas atuais? | [!UICONTROL O Customer Journey Analytics não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. ] Isso significa que nenhum dos segmentos ou métricas de cálculo existentes são compatíveis com [!UICONTROL Customer Journey Analytics]. |
| Como [!UICONTROL Customer Journey Analytics] cabo `Uniques Exceeded` limitações? | [!UICONTROL O Customer Journey Analytics não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas!] |
| Se eu for um [!DNL Data Workbench] cliente atual, posso migrar para o Customer Journey Analytics agora? | Depende. Se você depender muito do Unified Customer Process (UCP), aguarde até que a correção seja implementada. Se você já tiver altas taxas de autenticação do cliente, se quiser que todos os seus dados estejam em um lugar ou se quiser se livrar das eVars, o Customer Journey Analytics pode ser uma boa opção. |

## Implicações da exclusão de componentes de dados

Quando se trata de eliminação, estamos preocupados com seis componentes: sandbox, schema, conjunto de dados, conexão, visualização de dados e projetos do Workspace. Veja alguns cenários possíveis para excluir qualquer um desses componentes:

| E se eu... | Isso acontece... |
| --- | --- |
| Excluir uma caixa de proteção em [!UICONTROL Adobe Experience Platform]? | A exclusão de uma caixa de proteção quebrará qualquer [!UICONTROL Customer Journey Analytics] conexões com conjuntos de dados nessa caixa de proteção. No entanto, os conjuntos de dados no CJA não serão excluídos no momento. |
| Excluir um schema em [!UICONTROL Adobe Experience Platform], mas não os conjuntos de dados associados a este schema? | [!UICONTROL Adobe Experience Platform] não permite a exclusão de schemas que têm um ou mais conjuntos de dados associados a eles. No entanto, um Administrador com o conjunto apropriado de direitos pode excluir os conjuntos de dados primeiro e, em seguida, excluir o schema. |
| Excluir um conjunto de dados em [!UICONTROL Adobe Experience Platform]? | Não haveria notificação em [!UICONTROL Customer Journey Analytics]; no entanto, se os dados de transmissão estiverem ativados, não aparecerão mais novos dados após o momento em que os conjuntos de dados foram excluídos.<br>Em outras palavras, se a configuração **[!UICONTROL Importe automaticamente todos os novos conjuntos de dados nesta conexão, a partir de hoje]** na conexão ativada, não apareceriam mais novos dados após o momento em que os conjuntos de dados eram excluídos. |
| Excluir um conjunto de dados em [!UICONTROL Customer Journey Analytics]? | Atualmente, não é possível excluir um conjunto de dados em uma conexão que foi salva. Você teria que excluir toda a conexão e o start. (No entanto, você pode excluir um conjunto de dados em [!UICONTROL Adobe Experience Platform].) |
| Excluir um lote de um conjunto de dados (em [!UICONTROL Adobe Experience Platform])? | Se o lote já tiver sido ingerido em [!UICONTROL Customer Journey Analytics], [!UICONTROL Customer Journey Analytics] no momento, o não está ciente de que o lote foi excluído. Se o lote não tiver sido ingerido, é óbvio que não pode ser ingerido depois de ter sido eliminado em [!UICONTROL Adobe Experience Platform]. |
| Excluir um lote **enquanto estiver sendo ingerido** into [!UICONTROL Customer Journey Analytics]? | Se houver apenas um lote no conjunto de dados, nenhum dado ou dado parcial desse lote será exibido em [!UICONTROL Customer Journey Analytics]. A ingestão será revertida. Por exemplo, se houver 5 lotes no conjunto de dados e 3 deles já tiverem sido ingeridos quando o conjunto de dados tiver sido excluído, os dados desses 3 lotes aparecerão em [!UICONTROL Customer Journey Analytics]. |
| Excluir uma conexão em [!UICONTROL Customer Journey Analytics]? | Uma mensagem de erro indicará que:<ul><li>Quaisquer visualizações de dados criadas para a conexão excluída não funcionarão mais.</li><li> Da mesma forma, quaisquer projetos do Workspace que dependam de visualizações de dados na conexão excluída deixarão de funcionar.</li></ul> |
| Excluir uma visualização de dados em [!UICONTROL Customer Journey Analytics]? | Uma mensagem de erro indicará que todos os projetos do Workspace que dependem dessa visualização de dados excluída deixarão de funcionar. |
| Excluir um projeto do Workspace em [!UICONTROL Customer Journey Analytics]? | Você pode recriar o projeto ou usar uma solução alternativa para recuperar o projeto. Vá para [!UICONTROL Admin > Logs > Log de uso e acesso], localize o projeto excluído e copie sua ID. Em seguida, abra qualquer projeto do Workspace e atualize a ID no URL com a ID copiada. Em seguida, salve o projeto. |
