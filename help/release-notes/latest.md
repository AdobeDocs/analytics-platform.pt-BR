---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e1254a5ecff0f638cbef1051564c1ce856f715bd
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 51%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (outubro de 2023)

**Última atualização**: 4 de outubro de 2023

Essas notas de versão abrangem o período de 4 de outubro de 2023 a 24 de outubro de 2023. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Exportar tabelas completas para a nuvem** | A Exportação de tabela completa para Customer Journey Analytics permite exportar milhões de linhas do Workspace para destinos em nuvem. A exportação de tabelas completas oferece a entrega única ou agendada de tabelas de dados criadas no Workspace com suporte para até cinco detalhamentos, cinco métricas, filtros e métricas calculadas, tudo em uma tabela concatenada. É a evolução dos relatórios do Data Warehouse no Adobe Analytics, com muitos recursos novos e frequentemente solicitados que não estão disponíveis no Data Warehouse hoje. As opções de exportação da nuvem incluem:<ul><li>Zona de aterrissagem de dados Adobe Experience Platform</li><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li><li>Snowflake</li></ul>Para obter mais informações, consulte [Exportar relatórios de Customer Journey Analytics para a nuvem](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/export/export-cloud.html). | 4 de outubro de 2023 | 19 de outubro de 2023 |
| **Novas colunas disponíveis ao gerenciar componentes** | As novas colunas a seguir estão disponíveis no [Gerenciador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-manager.html) e no [Gerenciador de filtros](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/manage-filters.html) ao gerenciar componentes:<ul><li>Usado em</li><li>Última utilização</li></ul>Essas informações podem ajudar a determinar se um componente é relevante para usuários(as) em sua organização, onde é usado e se precisa ser excluído ou modificado. É possível usar o Dicionário de dados junto com essas informações para ajudar a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. | 23 de setembro de 2023 | 4 de outubro de 2023 |
| **Migrar projetos do Adobe Analytics e quaisquer componentes incluídos para o Customer Journey Analytics** | Agora você pode migrar seus projetos do Adobe Analytics para o Customer Journey Analytics. Esse processo simplifica a transição do Adobe Analytics para o Customer Journey Analytics. Ao migrar projetos para o Customer Journey Analytics, os ativos são mapeados de um conjunto de relatórios do Adobe Analytics para uma visualização de dados do Customer Journey Analytics. **Você migra projetos para o Customer Journey Analytics a partir da interface do Adobe Analytics.** [Saiba mais](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration.html) | N/D | 4 de outubro de 2023 |
| **Adobe Product Analytics: Mostrar/Ocultar série** | Clique na legenda do gráfico ou nas linhas da tabela para controlar a visibilidade das séries nas visualizações.  Saiba mais (em breve) | N/D | 4 de outubro de 2023 |
| **Anotações no Adobe Product Analytics** | Os projetos de análise guiada agora oferecem suporte à capacidade de visualizar anotações. Consulte cada tipo de exibição em [Análise guiada](/help/guided-analysis/overview.md) para obter detalhes sobre como ele interage com anotações. | N/D | 4 de outubro de 2023 |
| **Gerenciador de atividades de relatórios** | O Gerente de atividades de relatórios permite ver a capacidade de gerar relatórios para cada conexão em sua organização. Ele oferece aos administradores visibilidade detalhada do consumo de relatórios, a fim de diagnosticar e corrigir problemas de capacidade facilmente durante os horários de pico de relatórios. Os principais recursos do Gerente de atividades de relatórios incluem:<ul><li>Cancelar solicitações de relatórios atuais (incluindo solicitações de análises guiadas e exportações de tabelas completas)</li><li>Restringir solicitações subsequentes por um período definido</li></ul>Além de cancelar solicitações atuais, os administradores agora podem restringir solicitações por um período definido. Os administradores podem restringir solicitações por solicitação, projeto ou usuário.  Saiba mais (em breve) | 17 de outubro de 2023 | 23 de outubro de 2023 |

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
