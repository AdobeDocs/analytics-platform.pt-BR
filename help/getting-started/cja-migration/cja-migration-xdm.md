---
title: Mapear dados para o esquema XDM ao migrar para o Customer Journey Analytics
description: Saiba como mapear dados para o esquema XDM ao migrar para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---

# Etapa 4: Mapear dados para o esquema XDM ao migrar para o Customer Journey Analytics

+++As informações nesta página fazem parte de um processo de migração mais amplo. Expanda esta seção para ver onde essas informações se encaixam no processo de migração. </br></br>Você deve concluir todas as etapas de migração anteriores antes de continuar com as informações desta página.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 4, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| <span class="preview">**Etapa 4: [Mapeamento de dados do plano para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)**</span> | <span class="preview">[Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p></span> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |

{style="table-layout:auto"}

+++

A tabela a seguir mostra que os métodos de implementação exigem o mapeamento de dados para o esquema XDM:


| Método de migração | Mapeamento XDM necessário? | Mais informações |
|---------|----------|---------|
| **Nova implementação do SDK da Web**<p>As etapas básicas são:</p><ol><li>Criar um esquema XDM para sua organização</li><li>Implementar o SDK da Web</li><li>Enviar dados para a Platform</li></ol> | Não | Não é necessário um mapeamento porque você já [configurar um novo esquema XDM](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) como parte da nova implementação. |
| **Migrar sua implementação do Adobe Analytics para usar o SDK da Web**<p>As etapas básicas são:</p><ol><li>Mova sua implementação existente do Adobe Analytics para o SDK da Web e valide se tudo está funcionando lá.</li><li>Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>Use o Mapeamento de fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li><li>Enviar dados para a Platform</li></ol> | Sim | Trabalhando com sua equipe de dados, identifique o design de esquema ideal da organização para o Customer Journey Analytics e determine como você mapeará eVars e Props para o XDM.</br>[Use o Preparo de dados para mapear todos os campos no objeto de dados para o esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Configurar a implementação existente do Adobe Analytics Web SDK para enviar dados ao Customer Journey Analytics**<p>As etapas básicas são:</p><ol><li>Começar a enviar dados para o Customer Journey Analytics.<!-- What's involved here? Just point it at CJA? --></li><li>(Opcional) Crie um esquema XDM para sua organização à medida que tiver tempo.</li><li>Use o Mapeamento de fluxo de dados para mapear todos os campos no objeto de dados para o esquema XDM.</li></ol> | Sim | Trabalhando com sua equipe de dados, identifique o design de esquema ideal da organização para o Customer Journey Analytics e determine como você mapeará eVars e Props para o XDM.</br>[Use o Preparo de dados para mapear todos os campos no objeto de dados para o esquema XDM](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home) |
| **Conector de origem do Analytics**</br> Se a implementação do Adobe Analytics for o AppMeasurement ou a extensão do Analytics, você poderá começar a enviar dados para uma visualização de dados no Customer Journey Analytics.<p>Essa é a maneira mais fácil de obter dados para o Customer Journey Analytics, mas é o método menos viável a longo prazo.</p> | Não | Não é necessário um mapeamento porque o Conector de origem do Analytics usa o mesmo esquema do Adobe Analytics em vez do esquema XDM. |

{style="table-layout:auto"}

<!-- Does it benefit the customer to do this all at the same time if they're using multiple AEP apps? If so, have multiple sections like this. Or can they do CJA first and AJO later?

### Plan data mapping for Customer Journey Analytics


### Plan data mapping for Customer Journey analytics and other Adobe Experience platform applications

-->

## Em seguida, retenha os dados históricos

Em seguida, escolha o método que usará para [reter dados históricos do Adobe Analytics](/help/getting-started/cja-migration/cja-migration-historical-data.md).