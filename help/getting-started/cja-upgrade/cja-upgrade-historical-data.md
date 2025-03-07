---
title: Reter dados históricos ao atualizar para o Customer Journey Analytics
description: Saiba como reter dados históricos ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 97d48d88af969705f2664781e7a972f20c1b4239
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 45%

---

# Etapa 4: Reter dados históricos ao atualizar

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de atualização maior. Verifique se todas as etapas de atualização anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de atualização anteriores.

As informações nesta página abordam a Etapa 4 do processo de atualização, conforme destacado na tabela abaixo:

| Atualizar tarefa | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à atualização](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Saiba mais sobre os benefícios de atualizar para o Customer Journey Analytics e o processo básico de atualização. |
| **Etapa 2: [Escolher o caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Vários métodos estão disponíveis para atualizar para o Customer Journey Analytics. Escolha o método mais adequado de acordo com o ambiente atual do Adobe Analytics e as metas de longo prazo da sua organização. |
| **Etapa 3: [enviar dados à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere dependendo do caminho de atualização escolhido na Etapa 2. |
| <span class="preview">**Etapa 4: reter dados históricos**</span> | <span class="preview">A maioria das organizações precisa reter dados históricos do Adobe Analytics por um determinado período. Há várias opções disponíveis para fazer isso.</span> |
| **Etapa 5: [executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de atualização, é necessário executar várias tarefas antes que o ambiente do Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Migrar outros dados para a Experience Platform</li><li>Criar conexões entre conjuntos de dados da Platform e o Customer Journey Analytics</li><li>Criar visualizações de dados</li><li>Transferir o uso da API de relatórios</li><li>Contabilizar feeds de dados e data warehouse</li><li>Migrar projetos e componentes</li><li>Planejar a integração de usuários</li></ul> <p>Para mais informações, consulte [Introdução ao Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

<!--

>[!AVAILABILITY]
>
>The information on this page is being replaced with the following more comprehensive upgrade information: <ul><li>**Recommended upgrade steps**<p>For detailed information, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>A new upgrade guide is available that dynamically generates upgrade steps that are tailored for your organization and your unique circumstances.</p><p>To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.</p></li></ul>

-->

Escolha uma das seguintes opções para reter dados históricos ao migrar do Adobe Analytics para o Customer Journey Analytics:

>[!IMPORTANT]
>
>Ao escolher como reter dados históricos, entre em contato com o(a) representante da sua conta da Adobe para determinar os preços.

## Usar o conector de origem do Analytics

Você pode usar o [Conector de origem do Analytics](/help/data-ingestion/analytics.md) para reter dados históricos. Independentemente do caminho de atualização escolhido (mesmo se você atualizar usando o Web SDK), é possível usar o conector de origem do Analytics para reter dados históricos do ambiente do Adobe Analytics.

Você pode usar o conector de origem do Analytics para reter dados históricos, trazendo dados históricos para o seu próprio local dedicado, separado dos dados atuais.

O conector de origem do Analytics deve estar funcionando enquanto você precisar acessar os dados históricos.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Manter a implementação existente do Adobe Analytics

É possível manter a implementação existente do Adobe Analytics junto com a nova implementação do Customer Journey Analytics por um período específico (por exemplo, 1 ano). Ao escolher essa opção, considere o seguinte:

* Os dados não estariam disponíveis na Experience Platform.

* Planeje a desativação da implementação do Adobe Analytics quando tiver dados suficientes no Customer Journey Analytics.

## Em seguida, execute tarefas de implementação adicionais

Nesse ponto do processo de atualização, é necessário executar várias tarefas de implementação antes que o ambiente do Customer Journey Analytics esteja pronto para uso.

Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.

Essas tarefas incluem:

* Migrar outros dados para a Experience Platform

* Criar conexões entre conjuntos de dados da Platform e o Customer Journey Analytics

* Criar visualizações de dados

* Transferir o uso da API de relatórios

* Casos de uso de contabilização de feeds de dados e data warehouse

* Migrar projetos e componentes

* Planejar a integração de usuários

Para mais informações, comece pela etapa 2 da [Introdução ao Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
