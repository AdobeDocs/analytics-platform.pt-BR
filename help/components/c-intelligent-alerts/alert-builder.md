---
description: Saiba como criar alertas no Analysis Workspace.
title: Criar alertas
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
TQID: https://experienceleague.adobe.com/DALPpXgGDOoMJT8kv5xsDmZWapk4rDXhQmtTTvV0-TA
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817afid: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 997
ht-degree: 67%

---

# Criar alertas {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Granularidade de tempo"
>abstract="A granularidade de tempo refere-se à frequência com a qual o alerta é verificado."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>O uso de alertas com detecção de anomalias (também conhecidos como _Alertas inteligentes_) está disponível somente para organizações com um pacote Prime ou Ultimate do Customer Journey Analytics.

Os alertas no Customer Journey Analytics permitem a notificação com base em porcentagens alteradas ou pontos de dados específicos. Dependendo do pacote do Customer Journey Analytics, você também pode usar alertas para serem acionados com base em limites de anomalias.

Para informações mais detalhadas sobre os alertas, consulte [Visão geral dos alertas](/help/components/c-intelligent-alerts/intelligent-alerts.md).

Para criar um alerta:

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]**. No [Gerenciador de alertas](alert-manager.md), selecione ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Adicionar]** para criar um novo alerta ou escolha qualquer um dos alertas listados para modificar um alerta existente.

1. No Analysis Workspace, selecione um ou mais itens de linha em uma tabela de forma livre, selecione **[!UICONTROL Criar alerta a partir da seleção]** no menu de contexto. Essa ação preenche o criador de alertas automaticamente para criar um alerta com as métricas e os segmentos corretos.

A interface do [Construtor de alertas](#alert-builder) é exibida.


## Construtor de alertas

A interface do Criador de alertas é semelhante à interface usada ao criar segmentos ou métricas calculadas no Customer Journey Analytics:

![Interface do construtor de alertas](assets/alert-builder.png)

Especifique os seguintes detalhes no Construtor de alertas para um alerta:

| Elemento | Descrição |
|---------|----------|
| **[!UICONTROL Título]** | Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite das métricas. |
| **[!UICONTROL Descrição (opcional)]** | Especifique uma descrição para o alerta. |
| **[!UICONTROL Granularidade de tempo]** | Selecione a frequência com que deseja verificar a métrica: por dia, hora ou mês.<p><b>Observação</b>: para exibições de dados com um [calendário personalizado](/help/data-views/create-dataview.md#calendar), não há suporte para a granularidade mensal no Criador de alertas.<!--true?--></p> |
| **[!UICONTROL Destinatários]** | Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.<p><b>Importante:</b> o número de telefone deve ser precedido por um `+` e o [código do país](https://countrycode.org/).</p><p>O email que um usuário recebe após um alerta:</p><p>![Email de alerta](assets/alerts-email.PNG)</p> |
| **[!UICONTROL Data de expiração]** | Defina a data e a hora em que deseja que o alerta expire. |
| **[!UICONTROL Atraso]** | O tempo necessário antes que os dados sejam concluídos e estejam disponíveis para serem relatados no Customer Journey Analytics muda de acordo com a organização, normalmente com uma variação de 3 a 9 horas após o horário do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de evento devem ser concluídos, o que significa que a Adobe não está mais recebendo dados de evento para o intervalo de evento especificado.<p>Para levar em conta esse atraso no tempo de ingestão, os alertas têm um atraso padrão de 9 horas antes de serem enviados.</p><p>É possível ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.</p><p>Leve em consideração o seguinte ao diminuir o tempo de atraso:</p><ul><li>**Entender a disponibilidade dos dados versus a integridade dos dados**: os dados em lote são assimilados em um conjunto de dados do Experience Platform somente após um período de 3 a 9 horas. Para que os alertas sejam precisos, a ingestão de dados deve ser concluída, com todos os dados em lote disponíveis no conjunto de dados.</li><li>**Determine quanto tempo leva para que seus dados sejam concluídos e estejam disponíveis no conjunto de dados**: os tempos de ingestão de dados diferem de acordo com a organização. Certifique-se de que o tempo de atraso escolhido para a entrega de alertas é o mesmo ou menos frequente do que o tempo que leva para que os dados em lote fiquem disponíveis no conjunto de dados da Platform<!--add link? -->.</li><p>**Dica:** a maneira mais precisa de saber o tempo necessário para que todos os dados em lote sejam concluídos e assimilados no conjunto de dados do Experience Platform é consultar os engenheiros de dados em sua organização.</p><p>Como alternativa, você pode ter uma ideia geral de quanto tempo leva para que a entrega em lote em sua organização fique disponível no conjunto de dados da plataforma. Crie a seguinte tabela de forma livre no Analysis Workspace:</p><ol><li>Em uma tabela de forma livre no Analysis Workspace, adicione uma métrica [!UICONTROL **Eventos**] e uma dimensão [!UICONTROL **Dia**].</li><li>Detalhe a dimensão [!UICONTROL **Dia**] usando uma dimensão [!UICONTROL **Horas**].<p>Horas que não possuem nenhum dado são mostradas como 0.</p></li></ol><li>**Leve em conta os erros de cálculo**: se você diminuir o tempo de atraso padrão, configure o atraso para pelo menos uma hora além do tempo que a organização demora para concluir a ingestão de dados. Por exemplo, se houver um atraso de 3 horas antes da conclusão da ingestão de dados, você deve definir um atraso de 4 horas.</li></ul><p>Para obter mais informações, consulte [Os tempos da ingestão de dados variam no Customer Journey Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics), no artigo [Comparação de recursos de alertas: Customer Journey Analytics e Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md). |
| **[!UICONTROL Enviar um alerta quando]**: | [!UICONTROL **Qualquer uma destas métricas aciona**]: <ol><li>Arraste e solte métricas (incluindo métricas calculadas) para criar acionadores para o alerta.<p>Uma mensagem *componentes incompatíveis* será exibida se nem todas as métricas, dimensões ou segmentos no alerta forem compatíveis com o conjunto de relatórios selecionado atualmente.</p><p>Determine o limite (para uma anomalia) que a métrica deve exceder ou o valor (em caso de acima, abaixo, igual ou alteração de porcentagem) a ser usado antes que um alerta seja definido.</li><li>Selecione uma das seguintes condições:<ul><li>a anomalia existe</li><li>a anomalia está acima do esperado</li><li>a anomalia está abaixo do esperado</li><li>é maior que ou igual a</li><li>é menor que ou igual a</li><li>alterações por</li></ul></li><li>Selecione um valor de limite ou insira um valor.</li></ol>[!UICONTROL **Com todos estes filtros**]: arraste e solte segmentos ou dimensões para adicionar filtros ao alerta. Por exemplo, adicionar um segmento *Somente dispositivos móveis* significa que a regra será acionada apenas para dispositivos móveis. É possível adicionar filtros extras usando uma instrução AND. Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.</p><p>Consulte [Alertas - casos de uso](alerts-use-cases.md) para exemplos de casos de uso.</p> |
| **[!UICONTROL Pré-visualizar]** | A visualização interativa de alertas mostra a frequência de acionamento aproximada de um alerta com base em experiências passadas.<p>Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alerta foi acionado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.</p><p>Se você constatar o acionamento de uma quantidade excessiva de alertas, ajuste o limite em [Gerenciar alertas](/help/components/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert-preview.png){width="50%"}</p> |
