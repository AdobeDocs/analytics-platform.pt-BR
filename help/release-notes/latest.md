---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 86b411ac28aaa78914c6f105af2716e1b3a4150c
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 67%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (junho de 2023)

**Última atualização**: 6 de junho de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Destaques da versão {#highlights}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Legendas inteligentes** | Enriqueça a narrativa para usuários com resumos em linguagem natural de um [!UICONTROL Linha] visualização. [Saiba mais](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de maio de 2023 | 1 de junho de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=pt-BR#share-public-link) <p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=pt-BR#company-preferences)</p> | 3 de maio de 2023 | 6 de junho de 2023 |
| **Campos derivados** | Isto representa a versão inicial dos Campos derivados. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável. É possível definir ainda mais o campo derivado como um componente (métrica ou dimensão) nas visualizações de dados e então usá-lo como um componente no espaço de trabalho.<p>Essa versão é compatível com um modelo de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de maio de 2023 | 21 de junho de 2023 |
| **Acesso do Power BI e do Tableau às visualizações de dados do CJA** | O Conector SQL do Customer Journey Analytics (CJA) permite acesso SQL a visualizações de dados definidas no CJA. Engenheiros e analistas de dados mais familiarizados com o Power BI, Tableau ou outras ferramentas de business intelligence e visualização agora podem criar relatórios e painéis com base nas mesmas visualizações de dados que os usuários do CJA estão usando para seus projetos do Analysis Workspace. [Saiba mais](/help/data-views/sql-connector.md) |  | 30 de junho de 2023 |
| **Pesquisas geográficas da Experience Edge** | Você poderá criar relatórios usando dados de geolocalização no CJA assim que as Pesquisas geográficas de borda da experiência estiverem ativadas para a sua sequência de dados. |  | 30 de junho de 2023 |
| **Suporte expandido de pesquisa para perfil e dados de pesquisa** | Você poderá adicionar conjuntos de dados de pesquisa não apenas a conjuntos de dados de evento, mas também a conjuntos de dados de perfil e pesquisa. | 21 de junho de 2023 | 12 de julho de 2023 |
| **Suporte para conversão de moeda** | O CJA oferecerá suporte à conversão de moeda como parte da formatação de um componente de métrica em uma visualização de dados. | 21 de junho de 2023 | 19 de julho de 2023 |

{style="table-layout:auto"}

## Outros novos recursos ou atualizações {#other-new}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizações de dados do Adobe Journey Optimizer** | Os administradores do CJA têm acesso a algumas visualizações de dados adicionais no CJA, chamadas &quot;Visualização de dados do AJO (nome da sandbox)&quot;. Essas visualizações de dados são usadas para potencializar os relatórios no Adobe Journey Optimizer (AJO). Eles também podem ser usados para executar uma análise mais profunda das atividades do AJO no CJA. [Saiba mais](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). |  | 25 de maio de 2023 |
| **Preenchimento retroativo para sandboxes que não são de produção** | Ao criar um fluxo de dados do Conector de origem do Analytics em uma sandbox que não seja de produção, o preenchimento retroativo em sandboxes que não são de produção será limitado a 3 meses. Para as sandboxes de produção ele permanecerá em 13 meses. | N/D | 26 de abril de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=pt-BR#share-public-link) <p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 de maio de 2023 | 6 de junho de 2023 |
| **Tela inicial atualizada para o aplicativo de painéis do Analytics (aplicativo para dispositivos móveis)** | A nova tela inicial atualizada permite visualizar todos os cartões de pontuação em uma lista consolidada.  Se um único logon tiver acesso a mais de uma organização, todos os cartões de pontuação das organizações estarão disponíveis em uma única lista. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/D | 10 de maio de 2023 |
| **Campos derivados** | Isto representa a versão inicial dos Campos derivados. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável. É possível definir ainda mais o campo derivado como um componente (métrica ou dimensão) nas visualizações de dados e então usá-lo como um componente no espaço de trabalho.<p>Essa versão é compatível com um modelo de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=pt-BR)</p> | 10 de maio de 2023 | 2 de agosto de 2023 |
| **Report Builder para CJA - Selecionar visualização de dados da célula** | Esse recurso permite que os usuários selecionem a visualização de dados para um bloco de dados de uma célula. Isso é útil se você criar uma pasta de trabalho e tiver várias visualizações de dados com uma construção de dados semelhante e quiser reutilizar essa pasta de trabalho várias vezes, com visualizações de dados diferentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=pt-BR) | N/D | 24 de maio de 2023 |
| **Classificar componentes no Analysis Workspace** | <p>Uma nova opção Classificar está disponível ao visualizar componentes no painel esquerdo ou no Dicionário de dados no Analysis Workspace. É possível classificar componentes por Recomendado (os mais usados), Alfabético ou Categórico (tipo).</p><p>Anteriormente, só era possível pesquisar ou filtrar componentes. [Saiba mais](/help/components/overview.md)</p> | N/D | TBD |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-318343; AN-319453

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | N/D | N/D |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do AdobeIO OAuth** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics, da API CJA e do Livestream que usam as credenciais JWT do AdobeIO devem migrar para as credenciais de servidor para servidor do AdobeIO OAuth ao **1 de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam o JWT devem criar uma nova credencial OAuth de servidor para servidor ou migrar sua credencial JWT existente para uma credencial OAuth de servidor para servidor. Os clientes também devem atualizar seus aplicativos clientes para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Usar as novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
