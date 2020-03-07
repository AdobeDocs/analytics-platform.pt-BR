---
title: Perguntas frequentes sobre análise de jornada do cliente
description: Análise de jornada do cliente - Perguntas frequentes.
translation-type: tm+mt
source-git-commit: cca701c2a18d094ee4b172b032c125e710b51ff0

---


# Perguntas frequentes

| Pergunta | Resposta |
|---|---|
| **Pré-requisitos** |  |
| Você precisa do Gráfico de dispositivos ou do Device Coop para a Análise de jornada do cliente? | Não, o Gráfico de dispositivos privados ou o Device Coop não são necessários para a Análise de jornada do cliente. Na verdade, eles ainda não são apoiados. |
| Você precisa da Experience Cloud ID (ECID) para a Análise de jornada do cliente? | Não, o Customer Journey Analytics suporta qualquer ID em um conjunto de dados, seja ECID ou outra ID escolhida. |
| E se você precisar ETL dos seus dados antes do Customer Journey Analytics? | Atualmente, você precisa trabalhar com um parceiro ETL (Unifi ou Informatica) se precisar transformar seus dados antes de colocá-los na AEP. Se você precisar de ETL depois que os dados já tiverem sido assimilados, o AEP Query Services fornecerá algumas opções limitadas. |
| **Ortografia** |  |
| O Customer Journey Analytics pode &quot;unir&quot; entre dispositivos ou conjuntos de dados? | Não. A Análise de jornada do cliente é um sistema analítico &quot;traga sua própria ID&quot;. Os planos para uma boa abordagem costuradora estão em andamento. |
| A sutura de comportamento anônimo para comportamento autenticado é compatível? | Não, ainda não. |
| **Obtenção de dados no Customer Journey Analytics** |  |
| Qual é a latência esperada para a Análise de jornada do cliente na plataforma? | <ul><li>Em carga normal: &lt; 60<br>**minutosNota:**No caso de um volume de dados invulgarmente elevado através do pipeline, este poderá demorar até 24 horas.</li><li>Dados de preenchimento retroativo (até 10 bilhões de eventos): &lt; 4 semanas</li></ul> |
| Como você conecta dados online a dados offline no Customer Journey Analytics? | A Análise de jornada do cliente é um sistema de análise &quot;trazer sua própria ID&quot;. Desde que a ID da pessoa corresponda entre conjuntos de dados, o Customer Journey Analytics pode conectar segmentos, atribuição, fluxo, fallout etc. em conjuntos de dados. |
| Como faço para trazer meus dados offline para o Customer Journey Analytics? | Os clientes devem primeiro trazer quaisquer dados para a AEP antes de poder usá-los com o Customer Journey Analytics. A equipe de integração de dados da plataforma Experience pode ajudar a fornecer recomendações ou consultoria aos clientes, se necessário. |
| Como obtenho dados do Analytics no Customer Journey Analytics? | Os dados do Analytics podem ser conectados ao AEP por meio do Conector de dados do Analytics. A maioria dos campos do Analytics é trazida para o formato XDM, mas outros campos ainda não estão disponíveis (como dimensões de Canais de marketing). |
| Quanto tempo leva para montar elementos do conjunto de dados em uma visualização de dados? | Algumas horas para começar, e alguns dias para preencher retroativamente os últimos 13 meses de dados. |
| É necessário trazer dados de PII para estabelecer conexões entre os dados? | Não, você pode usar qualquer ID, incluindo um hash de uma ID do cliente, que não seja PII. |
| **Componentes tradicionais do Analytics** |  |
| O que isso significa para nosso produto tradicional do Adobe Analytics? | O Customer Journey Analytics é nosso produto de análise da próxima geração. A evolução dos nossos produtos atuais para a Análise de jornada do cliente levará anos e muita coordenação em conjunto. Esta versão é um grande passo de muitos nessa direção. |
| É possível compartilhar segmentos do Customer Journey Analytics com o AEP ou outras soluções? | Ainda não. Estamos buscando formas novas e inovadoras de compartilhar segmentos do Customer Journey Analytics para a AEP no futuro, que não têm um atraso tão grande. Dito isso, você pode compartilhar a saída dos Serviços de consulta para o Perfil unificado como uma solução alternativa potencial. |
| O que aconteceu com minha configuração antiga de eVar? | As eVars, props e eventos no sentido tradicional do Adobe Analytics não existem mais no Análise de jornada do cliente. Você tem elementos de esquema ilimitados (dimensões, métricas, campos de lista). Portanto, todas as configurações de atribuição que você costumava aplicar durante o processo de coleta de dados agora são aplicadas no momento da consulta. |
| Onde estão todas as minhas configurações de persistência de sessão e variável agora? | A Análise de jornada do cliente aplica todas essas configurações no momento do relatório, e essas configurações agora vivem em Exibições de dados. As alterações nessas configurações agora são retroativas e você pode ter várias versões usando várias Exibições de dados! |
| O que acontece com nossos segmentos atuais/métricas calculadas? | A Análise de jornada do cliente não usa mais eVars, props ou eventos e, em vez disso, usa qualquer esquema AEP. Isso significa que nenhum dos segmentos ou métricas de cálculo existentes são compatíveis com a Análise de jornada do cliente. |
| Como o Customer Journey Analytics lida com `Uniques Exceeded` limitações? | A Análise de jornada do cliente não tem limitações de valor exclusivas, portanto não é necessário se preocupar com elas! |
| Se eu for um [!DNL Data Workbench] cliente atual, posso mudar para o Customer Journey Analytics agora? | Depende. Se você depender muito do Unified Customer Process (UCP), aguarde até que a correção seja implementada. Se você já tiver altas taxas de autenticação do cliente, ou se quiser que todos os seus dados estejam em um local, ou se quiser se livrar das eVars, o Customer Journey Analytics pode se encaixar bem. |

