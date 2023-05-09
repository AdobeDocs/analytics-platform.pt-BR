---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: b313600ff215dea5a869e5a6125120a64f50235b
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 27%

---

# Notas de versão atuais do Customer Journey Analytics (CJA) (maio de 2023)

**Última atualização**: 8 de maio de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Preenchimento retroativo para sandboxes de não produção** | Ao criar um fluxo de dados do Conector de origem do Analytics em uma sandbox de não produção, o preenchimento retroativo em sandboxes de não produção será limitado a 3 meses. Ficará em 13 meses para as sandboxes de produção. | N/D | 26 de abril de 2023 |
| **Compartilhamento de links para projetos (sem necessidade de logon)** | Agora você pode compartilhar links de somente leitura para projetos do Analysis Workspace com pessoas que não têm acesso ao Adobe Analytics. Isso inclui o compartilhamento com pessoas fora da organização ou pessoas dentro da organização que não estão provisionadas para a Adobe Analytics. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>Essa funcionalidade é ativada por padrão e pode ser desativada pelo administrador do sistema. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3 de maio de 2023 | Junho de 2023 |
| **Tela inicial atualizada para o aplicativo de painéis do Analytics (Aplicativo móvel)** | A nova tela inicial atualizada permite visualizar todos os scorecards em uma lista de scorecards consolidada.  Se você tiver acesso a mais de uma organização em um logon, todos os scorecards das organizações estarão disponíveis em uma única lista. | N/D | 10 de maio de 2023 |
| **Campos derivados** | Representa a versão inicial dos campos Derivados. Um campo derivado permite definir (muitas vezes complexas) manipulações de dados dinamicamente, por meio de um construtor de regras personalizável. Além disso, é possível definir o campo derivado como um componente (métrica ou dimensão) nas Visualizações de dados e usar o campo derivado como um componente no Workspace.<p>Esta versão é compatível com um template de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 10 de maio de 2023 | TBD |
| **Report Builder para CJA - Selecionar visualização de dados da célula** | Esse recurso permite que os usuários selecionem a visualização de dados para um bloco de dados de uma célula. Isso é útil se você criar uma pasta de trabalho e tiver várias visualizações de dados com construção de dados semelhante e quiser reutilizar uma pasta de trabalho várias vezes, com visualizações de dados diferentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | N/D | 24 de maio de 2023 |
| **Classificar componentes no Analysis Workspace** | <p>Uma nova opção Classificar está disponível ao visualizar componentes no painel esquerdo ou no Dicionário de dados no Analysis Workspace. Você pode classificar componentes por Recomendado (os mais usados), Alfabético ou Categórico (tipo).</p><p>Anteriormente, você só podia pesquisar ou filtrar componentes. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=en)</p> | N/D | 10 de maio de 2023 |
| **Excluir linhas que contenham dimensões dinâmicas de uma tabela de forma livre** | Em uma tabela de forma livre no Analysis Workspace, agora é possível excluir rapidamente linhas específicas que contêm dimensões dinâmicas usando o ícone x. Ao fazer isso, uma regra de filtro &quot;Não é igual&quot; é aplicada automaticamente.<p>Anteriormente, a única maneira de excluir linhas que continham dimensões dinâmicas era criar manualmente uma regra na caixa de diálogo Filtro . [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=en)</p> | N/D | 10 de maio de 2023 |
| **Novo botão para adicionar uma visualização em um painel** | Um novo botão agora está disponível na parte inferior de cada painel no Analysis Workspace, permitindo que você adicione uma visualização rapidamente. <p>Anteriormente, os únicos métodos para adicionar uma visualização a um painel eram arrastar uma visualização do painel esquerdo, duplicar ou copiar uma visualização existente ou criar um painel em branco. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=en#quick-viz)</p> | N/D | 17 de maio de 2023 |
| **Deep Linking (Aplicativo Móvel)** | Permite que usuários enviem links para scorecards que os levarão diretamente ao projeto scorecard no aplicativo. Isso facilita ainda mais o compartilhamento de projetos e aumenta o engajamento de um público-alvo menos técnico. | N/D | 17 de maio de 2023 |
| **Legendas inteligentes** | Enriqueça a narrativa de usuários com resumos em linguagem natural de uma visualização em Linha. | 17 de maio de 2023 | 1 de junho de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-316412; AN-317105; AN-318122; AN-317353

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | N/D | N/D |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do CJA para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
