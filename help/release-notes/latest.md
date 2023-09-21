---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 82%

---

# Notas da versão atual do Adobe Customer Journey Analytics (setembro de 2023)

**Última atualização**: 13 de setembro de 2023

Essas notas de versão abrangem o período de lançamento de 13 de setembro de 2023 a 3 de outubro de 2023. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Suporte para classificações do A4T no conector de origem do Analytics** | O campo `_experience.decisioning.propositions.scopeDetails.correlationID` agora está disponível no esquema do conector de origem do Adobe Analytics. Esse campo é compatível com as classificações do A4T e será preenchido a partir de setembro de 2023. | | N/D | 12 de setembro de 2023 |
| **Atualizações para campos derivados** | As seguintes atualizações foram feitas na funcionalidade de campos derivados:<ul><li>A função [!UICONTROL Pesquisa] foi renomeada para [!UICONTROL Classificar], com opções adicionais para carregar dados de arquivos CSV. **(Versões de 27 de setembro de 2023)**</li><li>Funções adicionais estão disponíveis para uso ao definir um campo derivado: [!UICONTROL Aparar], [!UICONTROL Minúsculas] e [!UICONTROL Pesquisa].</li><li>As definições de campo derivado agora também aceitam campos de conjuntos de dados de [!UICONTROL Pesquisa] e [!UICONTROL Perfil].</li></ul>[Saiba mais](/help/data-views/derived-fields/derived-fields.md) | N/D | 13 de setembro de 2023 |
| **Novos recursos no Adobe Product Analytics** | <ul><li>**Detecção de anomalias**: compare os eventos com os valores esperados baseados em tendências históricas. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**Visualização da frequência de uso das tendências**: meça a adoção de seus recursos por frequência de uso. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html?lang=pt-BR)</li><li>**Preferências do usuário**: configure várias preferências de usuário, como paletas de cores e formato de número. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=pt-BR)</li></ul> | N/D | 18 de setembro de 2023 |
| **Pesquisas de dispositivo do Experience Edge** | Habilite a coleção automática de dados do tipo de dispositivo por meio da rede de borda da Experience Platform. Esse serviço do Experience Edge beneficia o Customer Journey Analytics juntamente com outros aplicativos da Experience Platform. (link da documentação a seguir) | N/D | 27 de setembro de 2023 |
| **Novas colunas disponíveis ao gerenciar componentes** | As novas colunas a seguir estão disponíveis no [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md) e a variável [Gerenciador de filtros](/help/components/filters/manage-filters.md) ao gerenciar componentes:<ul><li>Usado em</li><li>Última utilização</li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado. Você pode usar o Dicionário de dados junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> | 20 de setembro de 2023 | 4 de outubro de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-310972; AN-319509; AN-322245; AN-323411; AN-323719; AN-326101; AN-326125; AN-326888


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
