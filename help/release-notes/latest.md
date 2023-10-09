---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 49d91b513abd545ea73c7867817cd8724b460be4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 94%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (outubro de 2023)

**Última atualização**: 4 de outubro de 2023

Essas notas de versão abrangem o período de lançamento de 4 de outubro de 2023 a 24 de outubro de 2023. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exportação de tabelas completas para a nuvem** | A Exportação de tabela completa do Customer Journey Analytics permite exportar milhões de linhas do Workspace para destinos na nuvem. <p>A exportação de tabelas completas oferece entrega única ou agendada de tabelas de dados criadas no Workspace com suporte para até cinco detalhamentos, cinco métricas, filtros e métricas calculadas, tudo em uma tabela concatenada. É a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos e frequentemente solicitados que não estão disponíveis no Data Warehouse atualmente.</p><p> As opções de exportação na nuvem incluem:</p><ul><li>Zona de destino de dados da Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Para obter mais informações, consulte [Exportação de relatórios do Customer Journey Analytics para a nuvem](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html?lang=pt-BR). | 4 de outubro de 2023 | 19 de outubro de 2023 |
| **Novas colunas disponíveis ao gerenciar componentes** | As novas colunas a seguir estão disponíveis no [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html?lang=pt-BR) e no [Gerenciador de filtros](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html?lang=pt-BR) ao gerenciar componentes:<ul><li>Usado em</li><li>Última utilização</li></ul>Essas informações podem ajudar a determinar se um componente é relevante para usuários(as) em sua organização, onde é usado e se precisa ser excluído ou modificado. É possível usar o Dicionário de dados junto com essas informações para ajudar a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. | 23 de setembro de 2023 | 4 de outubro de 2023 |
| **Migração de projetos do Adobe Analytics e quaisquer componentes incluídos para o Customer Journey Analytics** | Agora é possível migrar seus projetos do Adobe Analytics para o Customer Journey Analytics. Esse processo simplifica a transição do Adobe Analytics para o Customer Journey Analytics. <p>Ao migrar projetos para o Customer Journey Analytics, os ativos são mapeados de um conjunto de relatórios do Adobe Analytics para uma visualização de dados do Customer Journey Analytics.</p> <p>Você pode migrar projetos para o Customer Journey Analytics a partir da interface do Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html)</p> | N/D | 9 de outubro de 2023 |
| **Adobe Product Analytics: Mostrar/Ocultar série** | Clique na legenda do gráfico ou nas linhas da tabela para controlar a visibilidade da série nas visualizações.  [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/overview.html?lang=en) | N/D | 4 de outubro de 2023 |
| **Anotações no Adobe Product Analytics** | A análise guiada agora permite visualizar anotações criadas no Customer Journey Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/annotations/overview.html?lang=en) | N/D | 4 de outubro de 2023 |
| **Gerenciador de atividades de relatórios** | O Gerenciador de atividades de relatórios permite ver a capacidade de relatórios para cada conexão na organização. Ele oferece visibilidade detalhada do consumo de relatórios à administração para maior facilidade no diagnóstico e na correção de problemas de capacidade durante os horários de pico de relatórios. Os recursos principais do Gerenciador de atividades de relatórios incluem:<ul><li>O cancelamento de solicitações de relatórios atuais (incluindo solicitações de análises guiadas e exportações de tabela completa)</li><li>A restrição de solicitações subsequentes por um período definido</li></ul>Além de cancelar solicitações atuais, a administração agora pode restringir solicitações por um período definido. É possível restringir solicitações por solicitação, projeto ou usuário(a). Saiba mais (em breve) | 17 de outubro de 2023 | 23 de outubro de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-325940; AN-326468; AN-328301; AN-328640; AN-329370

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL)

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do Adobe I/O OAuth** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics, da API do Customer Journey Analytics e da transmissão ao vivo que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth até o dia **1º de janeiro de 2025**. O Adobe I/O não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
