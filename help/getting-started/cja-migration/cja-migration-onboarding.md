---
title: Planejar a integração do usuário ao migrar para o Customer Journey Analytics
description: Planejar a integração do usuário ao migrar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 923dfac33fcde368392fe29c6530069cc0d8fb9d
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%

---

# Etapa 6: planejar a integração de usuários ao migrar para o Customer Journey Analytics

+++Expanda esta seção para ver onde as informações desta página se encaixam no processo de migração geral. Verifique se todas as etapas de migração anteriores foram concluídas.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 6, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| **Etapa 4: [Mapear dados para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| <span class="preview">**Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.</span> |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Há algumas diferenças importantes entre o Customer Journey Analytics e o Adobe Analytics que os usuários precisam saber.

Como no Adobe Analytics, o Analysis Workspace é a principal ferramenta voltada para o usuário no Customer Journey Analytics. No entanto, existem algumas diferenças importantes ao usar o Analysis Workspace no Customer Journey Analytics que os usuários precisam estar cientes.

Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.

Para obter informações sobre algumas das principais diferenças entre o Adobe Analytics e o Customer Journey Analytics, consulte [Guia do usuário para usuários do Adobe Analytics](/help/getting-started/aa-to-cja-user.md).

## Em seguida, direcione o uso da API de relatórios

A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md) da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics.