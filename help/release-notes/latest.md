---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 1534b628841a5b4588379b944822073f3288d710
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 79%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (junho de 2024)

**Última atualização**: quarta-feira, 18 de junho de 2024

Essas notas de versão abrangem o período de lançamento de 6 de junho de 2024 a julho de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Assistente de IA para o Customer Journey Analytics** | Permite fazer perguntas em linguagem natural na interface do Customer Journey Analytics e fornece respostas com base na documentação do produto. [Saiba mais](/help/ai-assistant.md) | | 6 de junho de 2024 |
| **Compilação baseada em gráfico** | Por meio da compilação baseada em gráfico, é possível usar o gráfico de identidade do Serviço de identidade do Experience Platform para obter uma melhor visualização da jornada do cliente:<ul><li>Associar conjuntos de dados com identificadores diferentes sem precisar extrair, transformar e carregar dados adicionais para refletir um único identificador.</li><li>Aprimorar a cobertura de identidade preferencial ou dourada para um único conjunto de dados ao compartilhar identidades entre conjuntos de dados.</li><li>Alinhamento dos perfis criados na Real-Time Customer Data Platform e no Journey Optimizer com pessoas no Customer Journey Analytics.</li></ul>[Saiba mais](/help/stitching/overview.md) |  | 28 de junho de 2024 |
| **Transformação de esquema B2B de pessoa para conta** | Para oferecer suporte a pesquisas com base em pessoas em dados B2B (incluindo contas, oportunidades, listas de marketing e campanhas), você pode transformar conjuntos de dados de pesquisa B2B. Essa transformação está disponível apenas para conjuntos de dados com dados para esquemas de pesquisa B2B, com base nas seguintes classes:<ul><li>Relação pessoal da conta de negócios XDM</li><li>Relação pessoal de oportunidade de negócios XDM</li><li>Membros da lista de marketing de negócios XDM</li><li>Membros da campanha de negócios XDM</li></ul>[Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5 de junho de 2024 |
| **Campos derivados - Função matemática** | Permite executar operadores matemáticos simples nas exibições de dados para responder perguntas sobre seus usuários. Por exemplo, você pode combinar produto, garantia e receita de envio. [Saiba mais](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 5 de junho de 2024 |
| **Campos derivados: função Próximo ou Anterior** | Permite que você observe qual é o valor seguinte ou anterior. Por exemplo, quais foram os canais de marketing anteriores com os quais alguém interagiu antes do canal de marketing selecionado? Ou, com o que os usuários da página interagiram antes ou depois da página selecionada? Com quais usuários de canal mais populares interagem antes de entrar na loja? [Saiba mais](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 12 de junho de 2024 |
| **Campos Derivados - Função Resumo** | Fornece a capacidade de aplicar funções do tipo agregação a métricas ou dimensões em níveis de evento, sessão e usuário. [Saiba mais](/help/data-views/derived-fields/derived-fields.md#summarize) | | 26 de junho de 2024 |
| **Campos derivados: função Desduplicação** | Ajuda a impedir a contagem repetida de um valor. Pode ser aplicado no nível do usuário ou da sessão ou com base no valor único de uma dimensão. (Link da documentação em breve) |  | quinta-feira, 10 de julho de 2024 |
| **Priorização e latência de assimilação** | Agora é possível assimilar os dados de eventos no Customer Journey Analytics em 90 minutos (SLT), independentemente de os dados terem 24 horas, 48 horas ou 7 dias. Observe que esse recurso é diferente com base no pacote SKU que sua empresa adquiriu:<ul><li>Assimilação prioritária do CJA básica: dados com 24 horas no processamento SLT de 90 minutos (disponível para o CJA Foundation e o CJA Select)</li><li>Assimilação prioritária do CJA intermediária: dados de 72 horas no processamento SLT de 90 minutos (disponível para o CJA Prime)</li><li>Assimilação prioritária do CJA avançada: dados com 1 semana no processamento SLT de 90 minutos (disponível para o CJA Ultimate)</li></ul> |  | 12 de junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais, além dos administradores do sistema, podem editar e excluir contas e locais. Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava. Essas configurações estão disponíveis quando os usuários [configuram contas de exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) e [configuram locais de exportação na nuvem](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 de junho de 2024 | Meados de julho de 2024 |
| **Selecionar vários campos em um filtro suspenso** | Quando vários campos são adicionados a um filtro suspenso, os usuários podem selecionar mais de um campo por vez. O painel é filtrado para incluir qualquer um dos campos selecionados. <p>Anteriormente, os usuários podiam selecionar apenas um campo por vez em um filtro suspenso.</p><p>A opção para exigir uma seleção em um filtro suspenso foi movida para o menu ao clicar com o botão direito em um filtro suspenso.</p><p>Anteriormente, os usuários podiam clicar no (x) ao lado da opção Sem filtro no menu suspenso.</p><p>Para obter mais informações, consulte [Filtros suspensos estáticos](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) in [Visão geral dos painéis](/help/analysis-workspace/c-panels/panels.md).</p><p>[Exibir uma demonstração em vídeo desse recurso](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/use-multi-select-drop-down-filters).</p> |  | 19 de junho de 2024 |
| **Índice de projetos do Workspace** | Um novo índice está disponível para projetos. O índice fornece links que permitem que os usuários se movam rapidamente entre painéis e visualizações no projeto. <p>O índice está disponível no painel esquerdo em todos os projetos.</p><p>Para obter mais informações, consulte o [Índice do projeto](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md).</p><p>[Exibir uma demonstração em vídeo desse recurso](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/navigating-workspace-projects/create-a-toc-in-analysis-workspace).</p> |  | 19 de junho de 2024 |
| **Criar hiperlinks para itens de dimensão em uma tabela de forma livre** | É possível criar hiperlinks para um ou mais itens de dimensão para torná-los clicáveis em uma tabela de forma livre no Analysis Workspace. <p>Você pode criar hiperlinks para itens de dimensão com valores de URL ou criar URLs personalizados para itens de dimensão com valores que não sejam de URL.</p><p>Você pode criar URLs personalizados dinâmicos para vários itens de dimensão usando variáveis. As variáveis podem fazer referência ao valor de um item de dimensão ou à dimensão de detalhamento.</p><p>Para obter mais informações, consulte [Criar hiperlinks para dimensões em uma tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md).</p><p>[Exibir uma demonstração em vídeo desse recurso](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/tips-and-tricks/create-hyperlinks-in-freeform-tables).</p> |  | 19 de junho de 2024 |
| **Use a visualização de dados do Customer Journey Analytics com o Adobe Journey Optimizer** | Uma nova opção de configuração no Customer Journey Analytics permite designar uma visualização de dados de Customer Journey Analytics a ser usada com o Adobe Journey Optimizer, sem a necessidade de configuração manual. <p>Para obter informações sobre como ativar essa opção de configuração, consulte a [Compatibilidade](/help/data-views/create-dataview.md#compatibility) seção em [Criar ou editar uma visualização de dados](/help/data-views/create-dataview.md).</p><p>Anteriormente, você tinha que configurar manualmente uma conexão e visualizações de dados ao visualizar dados do Journey Optimizer no Customer Journey Analytics.</p> |  | 19 de junho de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> <p>(Link da documentação em breve)</p> |  | 14 de julho de 2024 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-345454; AN-349816; AN-349905; AN-350617

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/D | | |

{style="table-layout:auto"}

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2024](/help/release-notes/2024.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do complemento de coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
