---
title: Enviar dados à Adobe Experience Platform ao migrar para o Customer Journey Analytics
description: Enviar dados à Adobe Experience Platform ao migrar para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 64%

---

# Etapa 3: Enviar dados para o Adobe Experience Platform ao atualizar

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de atualização maior. Verifique se todas as etapas de atualização anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de atualização anteriores.

As informações nesta página abordam a Etapa 3 do processo de atualização, conforme destacado na tabela abaixo:

| Atualizar tarefa | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à atualização](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Saiba mais sobre os benefícios de atualizar para o Customer Journey Analytics e o processo básico de atualização. |
| **Etapa 2: [Escolher o caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Vários métodos estão disponíveis para atualizar para o Customer Journey Analytics. Escolha o método mais adequado de acordo com o ambiente atual do Adobe Analytics e as metas de longo prazo da sua organização. |
| <span class="preview">**Etapa 3: enviar dados à Adobe Experience Platform**</span> | <span class="preview">O processo de envio de dados para o Adobe Experience Platform difere dependendo do caminho de atualização escolhido na Etapa 2.</span> |
| **Etapa 4: [reter dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | A maioria das organizações precisa reter dados históricos do Adobe Analytics por um determinado período. Há várias opções disponíveis para fazer isso. |
| **Etapa 5: [executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de atualização, é necessário executar várias tarefas antes que o ambiente do Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Migrar outros dados para a Experience Platform</li><li>Criar conexões entre conjuntos de dados da Platform e o Customer Journey Analytics</li><li>Criar visualizações de dados</li><li>Transferir o uso da API de relatórios</li><li>Contabilizar feeds de dados e data warehouse</li><li>Migrar projetos e componentes</li><li>Planejar a integração de usuários</li></ul> <p>Para mais informações, consulte [Introdução ao Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

Depois de [escolher o melhor caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md) para sua organização, você poderá começar a enviar dados para a Adobe Experience Platform para torná-los disponíveis no Customer Journey Analytics.

O processo para enviar dados ao Experience Platform para cada caminho de atualização é mostrado abaixo. Siga os links na tabela para obter informações detalhadas sobre a configuração.

| Caminho de atualização | Processo de envio de dados à Platform | Informações adicionais |
|---------|----------|----------|
| Nova implementação do SDK da web da Experience Platform | <ol><li>Criar um esquema XDM para a organização.<p>Colabore com a sua equipe de dados para identificar o design de esquema do Customer Journey Analytics ideal para a sua organização.</p></li><li>Implemente o SDK da web da Experience Platform.</li><li>Enviar dados para a Platform.</li></ol><p>Para obter informações detalhadas sobre cada uma dessas etapas, consulte [Assimilar dados por meio do SDK da web da Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Como esta é uma nova implementação do SDK da web da Experience Platform, o mapeamento de esquemas não é necessário, visto que criar o esquema é uma das primeiras etapas da implementação. |
| Migrar a sua implementação do Adobe Analytics para usar o SDK da web | <ol><li>Mova a implementação existente do Adobe Analytics para o SDK da web da Experience Platform e confira se tudo está funcionando no Adobe Analytics.<p>Para mais informações sobre como fazer isso, use os seguintes recursos, considerando se a sua implementação atual é a extensão de tag do Analytics ou o AppMeasurement:</p><ul><li>Se estiver usando a extensão de tag do Analytics, consulte [Migrar da extensão de tag do Adobe Analytics para a extensão de tag do SDK da web](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Se estiver usando o AppMeasurement, consulte [Migrar do AppMeasurement para o SDK da web](https://experienceleague.adobe.com/pt-br/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Crie um esquema XDM para a sua organização](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Colabore com a sua equipe de dados para identificar o design de esquema do Customer Journey Analytics ideal para a sua organização.</p></li><li>[Use o preparo de dados para mapear todos os campos no objeto de dados de acordo com o seu esquema XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home).</li><li>Para começar a enviar dados à Platform, [configure uma sequência de dados](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados à Platform | <ol><li>Para começar a enviar dados à Platform, [configure uma sequência de dados](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Como a sua implementação do Adobe Analytics já utiliza o SDK da web da Experience Platform, você pode ignorar as outras seções do artigo [Assimilar dados por meio do SDK da web da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Se você já estiver enviando dados para a Platform com a implementação do Adobe Analytics, esta etapa não será necessária. Basta criar uma conexão entre os conjuntos de dados da Plataforma e o Customer Journey Analytics, conforme descrito posteriormente neste processo.</p></li><li>(Opcional) [Crie um esquema XDM para a sua organização](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Colabore com a sua equipe de dados para identificar o design de esquema do Customer Journey Analytics ideal para a sua organização.</p><p>Observação: para mais informações sobre as vantagens de criar um esquema XDM, consulte [Escolha o seu esquema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Condicional) Se você tiver criado um esquema XDM, [use o preparo de dados para mapear todos os campos no objeto de dados de acordo com o seu esquema XDM](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-prep/home).</li></ol> |  |
| Usar o conector de origem do Analytics | [Assimilação e utilização de dados do Adobe Analytics tradicional](/help/data-ingestion/analytics.md) | Os dados do Adobe Analytics são mapeados automaticamente para o esquema XDM ao usar o conector de origem do Analytics. Nenhum mapeamento adicional é necessário. |

## Em seguida, retenha os dados históricos

Em seguida, decida como [reterá os dados históricos do Adobe Analytics](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
