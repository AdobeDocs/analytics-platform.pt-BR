---
title: Migrar projetos e componentes para o Customer Journey Analytics
description: Saiba mais sobre a migração de componentes para projetos de migração e componentes para o Customer Journey Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 6e5c3ecf-6eba-4dfa-8bf2-e43d56cfc65f
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 11%

---

# Etapa 9: migrar projetos e componentes para o Customer Journey Analytics

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de migração geral. Verifique se todas as etapas de migração anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 9, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| **Etapa 4: [Mapear dados para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| <span class="preview">**Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics.</span> |
| **Etapa 10: [Executar tarefas de pós-migração](/help/getting-started/cja-getting-started.md)** | Após concluir a migração, é necessário executar várias tarefas, incluindo trazer outros dados para o Experience Platform, criar conexões entre conjuntos de dados da plataforma e o Customer Journey Analytics, criar visualizações de dados e aprender a criar relatórios sobre dados entre canais no Analysis Workspace. |

{style="table-layout:auto"}

+++

A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics.

O processo de migração inclui:

* Recriação de projetos do Adobe Analytics no Customer Journey Analytics.

* Mapeamento de dimensões e métricas de conjuntos de relatórios do Adobe Analytics de acordo com as dimensões e métricas das visualizações de dados do Customer Journey Analytics.

Antes de iniciar a migração, [prepare-se para migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=pt-BR).

Depois de fazer todos os preparativos necessários, você poderá [migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=pt-BR).

## Em seguida, execute as tarefas de pós-migração

Depois que você [Migrar componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=pt-BR), é necessário executar várias tarefas para concluir a configuração do ambiente de Customer Journey Analytics. Essas tarefas incluem trazer outros dados para o Experience Platform, criar conexões entre conjuntos de dados da plataforma e o Customer Journey Analytics, criar visualizações de dados e aprender a criar relatórios sobre dados entre canais no Analysis Workspace.

Saiba mais sobre essas tarefas de migração no [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md).