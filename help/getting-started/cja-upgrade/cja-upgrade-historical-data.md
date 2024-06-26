---
title: Reter dados históricos ao atualizar para o Customer Journey Analytics
description: Saiba como reter dados históricos ao atualizar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# Etapa 4: Reter dados históricos ao atualizar

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de atualização maior. Verifique se todas as etapas de atualização anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de atualização anteriores.

As informações nesta página abordam a Etapa 4 do processo de atualização, conforme destacado na tabela abaixo:

| Atualizar tarefa | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à atualização](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Saiba mais sobre os benefícios de atualizar para o Customer Journey Analytics e o processo básico de atualização. |
| **Etapa 2: [Escolher o caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Vários métodos estão disponíveis para atualizar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere dependendo do caminho de atualização escolhido na Etapa 2. |
| <span class="preview">**Etapa 4: Reter dados históricos**</span> | <span class="preview">A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso.</span> |
| **Etapa 5: [Executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de atualização, é necessário executar várias tarefas antes que o ambiente de Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Trazendo outros dados para o Experience Platform</li><li>Criação de conexões entre conjuntos de dados da plataforma e Customer Journey Analytics</li><li>Criação de visualizações de dados</li><li>Transferência do uso da API de relatórios</li><li>Contabilização de feeds de dados e Data Warehouse</li><li>Migração de projetos e componentes</li><li>Integração do usuário do Planning</li></ul> <p>Para obter mais informações, consulte [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Escolha uma das seguintes opções para reter dados históricos ao mover do Adobe Analytics para o Customer Journey Analytics:

>[!IMPORTANT]
>
>Ao escolher como reter os dados históricos, entre em contato com o representante de conta Adobe para determinar os preços.

## Usar o Conector de origem do Analytics

Você pode usar o [Conector de origem do Analytics](/help/data-ingestion/analytics.md) para reter dados históricos. Independentemente do caminho de atualização escolhido (mesmo se você atualizar usando o SDK da Web), é possível usar o Conector de origem do Analytics para reter dados históricos do ambiente do Adobe Analytics.

Você pode usar o Conector de origem do Analytics para reter dados históricos, trazendo dados históricos para seu próprio local dedicado, separado de seus dados atuais.

O Conector de origem do Analytics deve estar funcionando enquanto você precisar acessar os dados históricos.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Manter a implementação existente do Adobe Analytics

Você pode manter sua implementação atual do Adobe Analytics junto com sua nova implementação do Customer Journey Analytics por um período específico (por exemplo, 1 ano). Ao escolher essa opção, considere o seguinte:

* Os dados não estariam disponíveis no Experience Platform.

* Você deve planejar desativar a implementação do Adobe Analytics depois de ter dados suficientes no Customer Journey Analytics.

## Em seguida, execute tarefas de implementação adicionais

Nesse ponto do processo de atualização, é necessário executar várias tarefas de implementação antes que o ambiente de Customer Journey Analytics esteja pronto para uso.

Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.

Essas tarefas incluem:

* Trazendo outros dados para o Experience Platform

* Criação de conexões entre conjuntos de dados da plataforma e Customer Journey Analytics

* Criação de visualizações de dados

* Transferência do uso da API de relatórios

* Contabilização de feeds de dados e casos de uso de Data Warehouse

* Migração de projetos e componentes

* Integração do usuário do Planning

Para obter mais informações, comece com a Etapa 2 em [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md).
