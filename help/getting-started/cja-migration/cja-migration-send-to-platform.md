---
title: Enviar dados para o Adobe Experience Platform ao migrar para o Customer Journey Analytics
description: Enviar dados para o Adobe Experience Platform ao migrar para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 1c789264a9867279f58a3ad139207fec8db29c1b
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# Etapa 3: Enviar dados para o Adobe Experience Platform ao migrar

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de migração geral. Verifique se todas as etapas de migração anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abordam a Etapa 3 da migração, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o caminho de migração](/help/getting-started/cja-migration/cja-migration-path.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| <span class="preview">**Etapa 3: Enviar dados para o Adobe Experience Platform**</span> | <span class="preview">O processo de envio de dados para o Adobe Experience Platform difere, dependendo do caminho de migração escolhido na Etapa 2.</span> |
| **Etapa 4: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 5: [Executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de migração, é necessário executar várias tarefas antes que o ambiente de Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às migrações do Adobe Analytics, bem como às novas implementações de Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Trazendo outros dados para o Experience Platform</li><li>Criação de conexões entre conjuntos de dados da plataforma e Customer Journey Analytics</li><li>Criação de visualizações de dados</li><li>Transferência do uso da API de relatórios</li><li>Contabilização de feeds de dados e Data Warehouse</li><li>Migração de projetos e componentes</li><li>Integração do usuário do Planning</li></ul> <p>Para obter mais informações, consulte [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++


Depois que você [escolha o caminho de migração](#step-2-choose-your-customer-journey-analytics-migration-method) que é o melhor para sua organização, você pode começar a enviar dados para a Adobe Experience Platform para disponibilizá-los no Customer Journey Analytics.

O processo para enviar dados para o Experience Platform de cada caminho de migração é mostrado abaixo. Siga os links na tabela para obter informações detalhadas sobre a configuração.

| Caminho de migração | Processo para enviar dados à plataforma | Informações adicionais |
|---------|----------|----------|
| Nova implementação do SDK da Web do Experience Platform | <ol><li>Crie um esquema XDM para sua organização.<p>Trabalhe com sua equipe de dados para identificar o design de esquema ideal para o Customer Journey Analytics de sua organização.</p></li><li>Implemente o SDK da Web do Experience Platform.</li><li>Enviar dados para a Platform.</li></ol><p>Para obter informações detalhadas sobre cada uma dessas etapas, consulte [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md). | Como esta é uma nova implementação do SDK da Web do Experience Platform, o mapeamento de esquema não é necessário porque você deve criar o esquema como uma das primeiras etapas durante a implementação. |
| Migrar sua implementação do Adobe Analytics para usar o SDK da Web | <ol><li>Mova sua implementação existente do Adobe Analytics para o SDK da Web do Experience Platform e valide se tudo está funcionando no Adobe Analytics.<p>Para obter informações sobre como fazer isso, use os seguintes recursos, dependendo se a implementação atual é a extensão de tag ou o AppMeasurement do Analytics:</p><ul><li>Se estiver usando a extensão de tag do Analytics, consulte [Migração da extensão de tag do Adobe Analytics para a extensão de tag do SDK da Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Se você estiver usando o AppMeasurement, consulte [Migração do AppMeasurement para o SDK da Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Criar um esquema XDM para sua organização](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabalhe com sua equipe de dados para identificar o design de esquema ideal para o Customer Journey Analytics de sua organização.</p></li><li>[Use o Preparo de dados para mapear todos os campos no objeto de dados para o esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Começar a enviar dados para a Platform por [configurar um fluxo de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados ao Customer Journey Analytics | <ol><li>Começar a enviar dados para a Platform por [configurar um fluxo de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).<p>Como sua implementação do Adobe Analytics já está usando o SDK da Web do Experience Platform, você pode ignorar as outras seções em [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</li><li>(Opcional) [Criar um esquema XDM para sua organização](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Trabalhe com sua equipe de dados para identificar o design de esquema ideal para o Customer Journey Analytics de sua organização.</p><p>Observação: para obter informações sobre as vantagens de criar um esquema XDM, consulte [Escolha seu esquema](/help/getting-started/cja-migration/cja-migration-path.md#choose-your-schema).</li><li>(Condicional) Se você criou um esquema XDM, [usar o Preparo de dados para mapear todos os campos no objeto de dados para o esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |
| Usar o Conector de origem do Analytics | [Assimilação e utilização de dados do Adobe Analytics tradicional](/help/data-ingestion/analytics.md) | Os dados do Adobe Analytics são mapeados automaticamente para o esquema XDM ao usar o Conector de origem do Analytics. Não é necessário mapeamento adicional. |

## Em seguida, retenha os dados históricos

Em seguida, decida como você [reter dados históricos do Adobe Analytics](/help/getting-started/cja-migration/cja-migration-historical-data.md).
