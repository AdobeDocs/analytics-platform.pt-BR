---
title: Enviar dados para o Adobe Experience Platform ao migrar para o Customer Journey Analytics
description: Enviar dados para o Adobe Experience Platform ao migrar para o Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 1%

---

# Etapa 3: Enviar dados para o Adobe Experience Platform ao migrar para o Customer Journey Analytics

+++As informações nesta página fazem parte de um processo de migração mais amplo. Expanda esta seção para ver onde essas informações se encaixam no processo de migração. </br></br>Você deve concluir todas as etapas de migração anteriores antes de continuar com as informações desta página.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 3, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| <span class="preview">**Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1.</span> |
| **Etapa 4: [Mapeamento de dados do plano para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |

{style="table-layout:auto"}

+++


Depois que você [escolha o método de migração](#step-2-choose-your-customer-journey-analytics-migration-method) que é o melhor para sua organização, você pode começar a enviar dados para a Adobe Experience Platform para disponibilizá-los no Customer Journey Analytics.

O processo para enviar dados para o Experience Platform para cada método de migração é mostrado abaixo. Siga os links na tabela abaixo para obter informações mais detalhadas.

| Método de migração | Processo para enviar dados à plataforma |
|---------|----------|
| Nova implementação do SDK da Web | [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](/help/data-ingestion/aepwebsdk.md) |
| Migrar sua implementação do Adobe Analytics para usar o SDK da Web | Se estiver usando a extensão de tag do Analytics: [Migração da extensão de tag do Adobe Analytics para a extensão de tag do SDK da Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)<p>Ou</p><p>Se você estiver usando o AppMeasurement: [Migração do AppMeasurement para o SDK da Web](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados ao Customer Journey Analytics | [Configurar um fluxo de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream) in [Assimilar dados por meio do SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) |
| Conector de origem do Analytics | [Assimilação e utilização de dados do Adobe Analytics tradicional](/help/data-ingestion/analytics.md) |

## Em seguida, mapeie os dados para o esquema XDM

Depois de enviar dados para o Experience Platform seguindo os links na tabela acima, talvez seja necessário [mapear dados para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md), dependendo do método de implementação escolhido.

Os métodos de implementação a seguir exigem que você mapeie dados para o esquema XDM:

* Migração da extensão de tag do Adobe Analytics para a extensão de tag do SDK da Web

* Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados ao Customer Journey Analytics

Como alternativa, se você optar por fazer uma nova implementação do SDK da Web, um mapeamento não será necessário, pois você já [configurar um novo esquema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) como parte da nova implementação.

Se você optar por usar o Conector de origem do Analytics na migração, não será necessário um mapeamento, pois o Conector de origem do Analytics usa o mesmo esquema do Adobe Analytics em vez do esquema XDM.
