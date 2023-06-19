---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fdef4a33154f443722ad4625c83f91bea7e047d
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 91%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (junho de 2023)

**Última atualização**: 19 de junho de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Destaques da versão {#highlights}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Legendas inteligentes** | Enriqueça a narrativa para usuários com resumos em linguagem natural de uma visualização em [!UICONTROL linha]. [Saiba mais](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de maio de 2023 | 1 de junho de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=pt-BR#share-public-link) <p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=pt-BR#company-preferences)</p> | 3 de maio de 2023 | 6 de junho de 2023 |
| **Campos derivados** | Isto representa a versão inicial dos Campos derivados. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável. Você pode definir ainda mais o campo derivado como um componente (métrica ou dimensão) nas visualizações de dados e, em seguida, usar o campo derivado como um componente no Workspace.<p>Essa versão é compatível com um modelo de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de maio de 2023 | 14 de junho de 2023 |
| **Acesso do Power BI e do Tableau às visualizações de dados do CJA** | O Conector SQL do Customer Journey Analytics (CJA) permite acesso SQL a visualizações de dados definidas no CJA. Analistas e engenheiros de dados mais familiarizados com o Power BI, Tableau ou outras ferramentas de business intelligence e visualização agora podem criar relatórios e painéis com base nas mesmas visualizações de dados que os usuários do CJA estão usando para seus projetos do Analysis Workspace. [Saiba mais](/help/data-views/sql-connector.md) |  | 30 de junho de 2023 |
| **Pesquisas geográficas do Experience Edge** | Você poderá criar relatórios usando dados de geolocalização no CJA assim que as Pesquisas geográficas do Experience Edge estiverem habilitadas para a sua sequência de dados. |  | 30 de junho de 2023 |
| **Suporte de pesquisa expandido para perfil e dados de pesquisa** | Você poderá adicionar conjuntos de dados de pesquisa, não apenas a conjuntos de dados de evento, mas também a conjuntos de dados de perfil e pesquisa. | 28 de junho de 2023 | 12 de julho de 2023 |
| **Suporte à conversão de moeda** | A conversão de moeda é compatível como parte da formatação de um componente de métrica em uma Visualização de dados. [Saiba mais](../data-views/component-settings/format.md#currency) | 7 de junho de 2023 | 21 de junho de 2023 |

{style="table-layout:auto"}

## Outros novos recursos ou atualizações {#other-new}

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizações de dados do Adobe Journey Optimizer** | Os administradores do CJA têm acesso a algumas visualizações de dados adicionais no CJA, chamadas “Visualização de dados do AJO (nome da sandbox)”. Essas visualizações de dados são usadas para potencializar os relatórios no Adobe Journey Optimizer (AJO). Elas também podem ser usadas para executar uma análise mais profunda das atividades do AJO no CJA. [Saiba mais](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html?lang=pt-BR). | | 25 de maio de 2023 |
| **Preenchimento retroativo para sandboxes que não são de produção** | Ao criar um fluxo de dados do Conector de origem do Analytics em uma sandbox que não seja de produção, o preenchimento retroativo em sandboxes que não são de produção será limitado a 3 meses. Para as sandboxes de produção ele permanecerá em 13 meses. | N/D | 26 de abril de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=pt-BR#share-public-link) <p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=pt-BR#ims-organization-preferences)</p> | 3 de maio de 2023 | 6 de junho de 2023 |
| **Tela inicial atualizada para o aplicativo de painéis do Analytics (aplicativo para dispositivos móveis)** | A nova tela inicial atualizada permite visualizar todos os cartões de pontuação em uma lista consolidada.  Se um único logon tiver acesso a mais de uma organização, todos os cartões de pontuação das organizações estarão disponíveis em uma única lista. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html?lang=pt-BR#use-dashboards) | N/D | 10 de maio de 2023 |
| **Report Builder para CJA - Selecionar visualização de dados da célula** | Esse recurso permite que os usuários selecionem a visualização de dados para um bloco de dados de uma célula. Isso é útil se você criar uma pasta de trabalho e tiver várias visualizações de dados com uma construção de dados semelhante e quiser reutilizar essa pasta de trabalho várias vezes, com visualizações de dados diferentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=pt-BR) | N/D | 24 de maio de 2023 |
| **Página de aprendizado atualizada para o CJA** | A guia Aprendizado na página de aterrissagem do Customer Journey Analytics agora tem conteúdo específico do CJA, incluindo conteúdo focado na transição do Adobe Analytics para o CJA.<p>Os seguintes aprimoramentos adicionais também estão disponíveis na guia Aprendizado:</p><ul><li>Design aprimorado que mostra mais conteúdo de aprendizagem em uma única página com navegação aprimorada</li><li>Capacidade de personalizar o conteúdo de aprendizagem por nível de experiência (iniciante, intermediário e avançado)</li></ul><p>Anteriormente, a guia Aprendizado no CJA continha informações idênticas à guia Aprendizado no Adobe Analytics.</p> [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | N/D | 30 de junho de 2023 |
| **Classificar componentes no Analysis Workspace** | <p>Uma nova opção Classificar está disponível ao visualizar componentes no painel esquerdo ou no Dicionário de dados no Analysis Workspace. É possível classificar componentes por Recomendado (os mais usados), Alfabético ou Categórico (tipo).</p><p>Anteriormente, só era possível pesquisar ou filtrar componentes. [Saiba mais](/help/components/overview.md)</p> | N/D | 7 de junho de 2023 |
| **Excluir linhas que contenham dimensões dinâmicas de uma Tabela de forma livre** | Em uma Tabela de forma livre no Analysis Workspace, agora é possível excluir rapidamente linhas específicas que contenham dimensões dinâmicas usando o ícone x. Ao fazer isso, uma regra de filtro “Sempre excluir itens” é aplicada automaticamente.<p>Anteriormente, a única maneira de excluir linhas que continham dimensões dinâmicas era criar manualmente uma regra na caixa de diálogo Filtro. [Saiba mais](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 de maio de 2023 |
| **Novo botão para adicionar uma visualização dentro de um painel** | Um novo botão agora está disponível na parte inferior de cada painel no Analysis Workspace, permitindo que você adicione uma visualização rapidamente. <p>Anteriormente, os únicos métodos para adicionar uma visualização a um painel eram arrastar uma visualização do painel esquerdo, duplicar ou copiar uma visualização já existente ou criar um painel em branco. [Saiba mais](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 de maio de 2023 |
| **Deep Linking (aplicativo para dispositivos móveis)** | Permite que usuários enviem links para cartões de pontuação que os levarão diretamente ao projeto do cartão de pontuação no aplicativo. Isso facilita ainda mais o compartilhamento de projetos e aumenta o engajamento de um público menos técnico. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html?lang=pt-BR#share-scorecards-using-a-shareable-link) | N/D | 17 de maio de 2023 |
| **Legendas inteligentes** | Enriqueça a narrativa para usuários com resumos em linguagem natural de uma visualização em [!UICONTROL linha]. [Saiba mais](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de maio de 2023 | 1 de junho de 2023 |

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
| **Migração para as credenciais de servidor para servidor do AdobeIO OAuth** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics, da API do CJA e do Livestream que usam as credenciais JWT do AdobeIO devem migrar para as credenciais de servidor para servidor do AdobeIO OAuth até **1º de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
