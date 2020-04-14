---
title: Perguntas frequentes sobre Customer Journey Analytics
description: Customer Journey Analytics - Perguntas frequentes.
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| **Pré-requisitos** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. Na verdade, eles ainda não são compatíveis. |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| E se for necessário extrair, transformar, carregar (ETL) seus dados antes do Customer Journey Analytics? | Atualmente, você precisa trabalhar com um parceiro de ETL (Unifi ou Informatica) se for necessário transformar os dados antes de colocá-los na AEP. Se ETL for necessário depois que os dados já tiverem sido assimilados, os Serviços de consulta da AEP fornecem algumas opções limitadas. |
| **Costura** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | Não. [!UICONTROL Customer Journey Analytics] é um sistema de análise &quot;traga sua própria ID&quot;. Os planos para uma boa abordagem de costura estão em andamento. |
| A costura de comportamento anônimo para comportamento autenticado é compatível? | Não, ainda não. |
| **Obter dados em[!UICONTROL Customer Journey Analytics]** |  |
| Qual é a latência esperada para [!UICONTROL Customer Journey Analytics] continuar [!UICONTROL Experience Platform]? | <ul><li>Em carga normal: &lt; 60 minutos <br>**Observação:** no caso de um volume de dados excepcionalmente elevado por meio do pipeline, poderá demorar até 24 horas.</li><li>Dados de preenchimento retroativo (até 10 bilhões de eventos): &lt; 4 semanas</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] é um sistema de análise &quot;trazer sua própria ID&quot;. As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. em todos os conjuntos de dados. |
| Como posso trazer meus dados offline para o Customer Journey Analytics? | Os clientes devem primeiro trazer quaisquer dados para a plataforma da experiência antes de poder usá-los com a Análise de jornada do cliente. A equipe de integração de dados da Experience Platform pode ajudar a fornecer recomendações ou consultoria aos clientes, se necessário. |
| Como posso obter dados do Analytics no Customer Journey Analytics? | Os dados do Analytics podem ser conectados à Experience Platform por meio do Analytics Data Connector. A maioria dos campos do Analytics é trazida para o formato XDM, mas outros campos ainda não estão disponíveis (como dimensões de Canais de marketing). |
| Qual é o tempo de montagem dos elementos do conjunto de dados em uma exibição de dados? | Algumas horas para começar e alguns dias para preencher retroativamente os últimos 13 meses de dados. |
| É necessário trazer os dados de PII para estabelecer as conexões entre os dados? | Não, você pode usar qualquer ID, incluindo um hash de uma ID do cliente, que não seja PII. |
| **Componentes tradicionais do Analytics** |  |
| O que isso significa para nosso produto tradicional do Adobe Analytics? | O Customer Journey Analytics é nosso produto de análise da próxima geração. A evolução dos nossos produtos atuais para o Customer Journey Analytics levará anos e precisará de muita coordenação conjunta. Esta versão é um grande passo de muitos nessa direção. |
| É possível compartilhar segmentos do Customer Journey Analytics com a AEP ou outras soluções? | Ainda não. Estamos buscando formas novas e inovadoras de compartilhar segmentos do Customer Journey Analytics para a AEP no futuro, que não tenham um atraso tão grande. Dito isso, você pode compartilhar a saída dos Serviços de consulta com o Perfil unificado, como uma possível solução alternativa. |
| O que aconteceu com minha antiga configuração do eVar? | eVars, props e eventos no sentido tradicional do Adobe Analytics não existem mais no Customer Journey Analytics. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta. |
| Onde estão todas as minhas configurações de sessão e persistência de variável agora? | O Customer Journey Analytics aplica todas essas configurações no momento do relatório e essas configurações agora residem na Exibição de dados. As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados! |
| O que acontece com nossos segmentos/métricas calculadas atuais? | O Customer Journey Analytics não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema da AEP. Isso significa que nenhum dos segmentos ou métricas calculadas existentes é compatível com o Customer Journey Analytics. |
| Como o Customer Journey Analytics lida com `Uniques Exceeded` limitações? | O Customer Journey Analytics não tem limitações de valor exclusivas, portanto, não é necessário se preocupar com elas! |
| Se eu for um [!DNL Data Workbench] cliente atual, posso migrar para o Customer Journey Analytics agora? | Depende. Se você depender muito do Unified Customer Process (UCP), aguarde até que a correção seja implementada. Se você já tiver altas taxas de autenticação do cliente, se quiser que todos os seus dados estejam em um lugar ou se quiser se livrar das eVars, o Customer Journey Analytics pode ser uma boa opção. |

