---
title: Substituir Feeds de dados e Data Warehouse ao migrar para o Customer Journey Analytics
description: Planeje a migração do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Etapa 8: Substituir os feeds de dados e o Data Warehouse ao migrar para o Customer Journey Analytics

+++As informações nesta página fazem parte de um processo de migração mais amplo. Expanda esta seção para ver onde essas informações se encaixam no processo de migração. </br></br>Você deve concluir todas as etapas de migração anteriores antes de continuar com as informações desta página.

Antes de continuar com esta seção, primeiro verifique se você concluiu todas as tarefas de migração anteriores.

As informações nesta página abrangem a Etapa 8, conforme destacado na tabela abaixo:

| Tarefa de migração | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| **Etapa 4: [Mapeamento de dados do plano para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| <span class="preview">**Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics.</span> |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |

{style="table-layout:auto"}

+++

Se você usa atualmente Feeds de dados ou o Data Warehouse no Adobe Analytics, use a tabela a seguir para saber mais sobre as várias opções de exportação disponíveis no Customer Journey Analytics:

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| Feeds de dados | Avalie os casos de uso dos feeds de dados e use qualquer combinação de métodos de exportação alternativos disponíveis no Customer Journey Analytics: <ul><li>Para exportar conjuntos de dados brutos, [exportar conjuntos de dados para destinos de armazenamento na nuvem](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)&#x200B;</li><li>Para exportações de público-alvo ou nível de evento usando a ID de pessoa ou o carimbo de data e hora, use [Exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md)&#x200B;</li><li>Para integração direta com o Power BI e o Tableau, use o [Extensão Customer Journey Analytics BI](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension)&#x200B;</li><li>Para obter acesso direto ao SQL para dados no Adobe Experience Platform, use o [Serviço de consulta Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | Alterar exportações do Adobe Analytics Data Warehouse para usar [Exportação de tabela completa](/help/analysis-workspace/export/export-cloud.md) em Customer Journey Analytics.<p>Exportação de tabela completa do Customer Journey Analytics é a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos e frequentemente solicitados que não estão disponíveis no Data Warehouse hoje.</p> |

{style="table-layout:auto"}

## Em seguida, migre projetos e componentes

Use a área Migração de componentes no Adobe Analytics para [migrar projetos e seus componentes associados](/help/getting-started/cja-migration/cja-migration-projects.md) do Adobe Analytics para o Customer Journey Analytics.
