---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 0fdf95906e17b9e90fa6ba652aa8e53f695279a4
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 76%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (maio de 2023)

**Última atualização**: 31 de maio de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Visualizações de dados do Adobe Journey Optimizer** | Os administradores do CJA têm acesso a algumas visualizações de dados adicionais no CJA, chamadas &quot;Visualização de dados do AJO (nome da sandbox)&quot;. Essas visualizações de dados são usadas para potencializar os relatórios no Adobe Journey Optimizer (AJO). Eles também podem ser usados para executar uma análise mais profunda das atividades do AJO no CJA. [Saiba mais](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html). |  | 25 de maio de 2023 |
| **Preenchimento retroativo para sandboxes que não são de produção** | Ao criar um fluxo de dados do Conector de origem do Analytics em uma sandbox que não seja de produção, o preenchimento retroativo em sandboxes que não são de produção será limitado a 3 meses. Para as sandboxes de produção ele permanecerá em 13 meses. | N/D | 26 de abril de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas de fora da organização, ou com aquelas de dentro da organização que não estejam provisionadas para o Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=pt-BR#share-public-link) <p>Essa funcionalidade está habilitada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 3 de maio de 2023 | 5 de junho de 2023 |
| **Tela inicial atualizada para o aplicativo de painéis do Analytics (aplicativo para dispositivos móveis)** | A nova tela inicial atualizada permite visualizar todos os cartões de pontuação em uma lista consolidada.  Se um único logon tiver acesso a mais de uma organização, todos os cartões de pontuação das organizações estarão disponíveis em uma única lista. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | N/D | 10 de maio de 2023 |
| **Campos derivados** | Isto representa a versão inicial dos Campos derivados. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável. É possível definir ainda mais o campo derivado como um componente (métrica ou dimensão) nas visualizações de dados e então usá-lo como um componente no espaço de trabalho.<p>Essa versão é compatível com um modelo de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html?lang=pt-BR)</p> | 10 de maio de 2023 | 2 de agosto de 2023 |
| **Report Builder para CJA - Selecionar visualização de dados da célula** | Esse recurso permite que os usuários selecionem a visualização de dados para um bloco de dados de uma célula. Isso é útil se você criar uma pasta de trabalho e tiver várias visualizações de dados com uma construção de dados semelhante e quiser reutilizar essa pasta de trabalho várias vezes, com visualizações de dados diferentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=pt-BR) | N/D | 24 de maio de 2023 |
| **Classificar componentes no Analysis Workspace** | <p>Uma nova opção Classificar está disponível ao visualizar componentes no painel esquerdo ou no Dicionário de dados no Analysis Workspace. É possível classificar componentes por Recomendado (os mais usados), Alfabético ou Categórico (tipo).</p><p>Anteriormente, só era possível pesquisar ou filtrar componentes. [Saiba mais](/help/components/overview.md)</p> | N/D | TBD |
| **Excluir linhas que contenham dimensões dinâmicas de uma Tabela de forma livre** | Em uma Tabela de forma livre no Analysis Workspace, agora é possível excluir rapidamente linhas específicas que contenham dimensões dinâmicas usando o ícone x. Ao fazer isso, uma regra de filtro &quot;Sempre excluir itens&quot; é aplicada automaticamente.<p>Anteriormente, a única maneira de excluir linhas que continham dimensões dinâmicas era criar manualmente uma regra na caixa de diálogo Filtro. [Saiba mais](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | N/D | 17 de maio de 2023 |
| **Novo botão para adicionar uma visualização dentro de um painel** | Um novo botão agora está disponível na parte inferior de cada painel no Analysis Workspace, permitindo que você adicione uma visualização rapidamente. <p>Anteriormente, os únicos métodos para adicionar uma visualização a um painel eram arrastar uma visualização do painel esquerdo, duplicar ou copiar uma visualização já existente ou criar um painel em branco. [Saiba mais](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | N/D | 17 de maio de 2023 |
| **Deep Linking (aplicativo para dispositivos móveis)** | Permite que usuários enviem links para cartões de pontuação que os levarão diretamente ao projeto do cartão de pontuação no aplicativo. Isso facilita ainda mais o compartilhamento de projetos e aumenta o engajamento de um público menos técnico. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | N/D | 17 de maio de 2023 |
| **Legendas inteligentes** | Enriqueça a narrativa para usuários com resumos em linguagem natural de um [!UICONTROL Linha] visualização. [Saiba mais](/help/analysis-workspace/visualizations/intelligent-captions.md) | 17 de maio de 2023 | 1 de junho de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-316412; AN-317105; AN-318122; AN-317353

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | N/D | N/D |

## Avisos de fim da vida útil (EOL) {#eol}

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para as credenciais de servidor para servidor do AdobeIO OAuth** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics, da API CJA e do Livestream que usam as credenciais JWT do AdobeIO devem migrar para as credenciais de servidor para servidor do AdobeIO OAuth ao **1 de janeiro de 2025**. O AdobeIO não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam o JWT devem criar uma nova credencial OAuth de servidor para servidor ou migrar sua credencial JWT existente para uma credencial OAuth de servidor para servidor. Os clientes também devem atualizar seus aplicativos clientes para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Usar as novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
