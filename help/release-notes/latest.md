---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 46156d663b4a5559ee0769c4170323b3891d4272
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 36%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (junho de 2024)

**Última atualização**: quinta-feira, 12 de junho de 2024

Essas notas de versão abrangem o período de 6 de junho de 2024 a julho de 2024. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Assistente de IA para o Customer Journey Analytics** | Permite fazer perguntas em linguagem natural na interface do Customer Journey Analytics e fornece respostas com base na documentação do produto. [Saiba mais](/help/ai-assistant.md) | | 6 de junho de 2024 |
| **Compilação baseada em gráfico: compilação usando exportação de gráfico do UIS** | Por meio da compilação baseada em gráfico, é possível usar o Gráfico de identidade para obter uma melhor visualização da jornada do cliente ao:<ul><li>Associar conjuntos de dados com identificadores diferentes sem precisar extrair, transformar e carregar dados adicionais para refletir um único identificador.</li><li>Aprimoramento da cobertura de identidade preferencial ou dourada para um único conjunto de dados ao compartilhar identidades entre conjuntos de dados.</li><li>Alinhamento dos perfis criados no Real-time Customer Data Platform e no Journey Optimizer com as pessoas no Customer Journey Analytics.</li></ul>(Link da documentação em breve) |  | sábado, 28 de junho de 2024 |
| **Transformação de esquema B2B de pessoa para conta** | Para oferecer suporte a pesquisas com base em pessoas em dados B2B (incluindo contas, oportunidades, listas de marketing e campanhas), você pode transformar conjuntos de dados de pesquisa B2B. Essa transformação está disponível somente para conjuntos de dados com dados para esquemas de pesquisa B2B, com base nas seguintes classes:<ul><li>Relação pessoal da conta de negócios XDM</li><li>Relação pessoal de oportunidade de negócios XDM</li><li>Membros da lista de marketing de negócios XDM</li><li>Membros da campanha de negócios XDM</li></ul>[Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 5 de junho de 2024 |
| **Campos derivados - Função matemática** | Permite executar operadores matemáticos simples nas exibições de dados para responder perguntas sobre seus usuários. Por exemplo, você pode combinar as receitas do produto, da garantia e do envio.  <p>[Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 5 de junho de 2024 |
| **Campos derivados - Função próxima ou anterior** | Permite que você observe qual é o valor seguinte ou anterior. Por exemplo, com quais canais de marketing alguém interagiu antes do canal de marketing selecionado? Ou, com o que os usuários da página interagiram antes ou depois da página selecionada? Com quais usuários de canal mais populares interagem antes de entrar na loja? <p>[Saiba mais](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous)</p> | | 12 de junho de 2024 |
| **Campos Derivados - Função Resumo** | Fornece a capacidade de aplicar funções do tipo agregação a métricas ou dimensões em níveis de evento, sessão e usuário. (Link da documentação em breve) | | quinta-feira, 26 de junho de 2024 |
| **Campos Derivados - Função de Desduplicação** | Ajuda a impedir a contagem repetida de um valor. Pode ser aplicado no nível do Usuário ou da Sessão ou com base no valor exclusivo de uma dimensão. (Link da documentação em breve) |  | quinta-feira, 26 de junho de 2024 |
| **Priorização e latência de assimilação** | Agora é possível assimilar os dados de eventos no Customer Journey Analytics em 90 minutos (SLT), independentemente de os dados terem 24 horas, 48 horas ou 7 dias. Observe que esse recurso é diferente com base no pacote SKU que sua empresa adquiriu:<ul><li>Básica de assimilação de prioridade do CJA: dados de 24 horas no processamento SLT de 90 minutos (disponível para a CJA Foundation e o CJA Select)</li><li>Assimilação prioritária do CJA intermediária: dados de 72 horas no processamento SLT de 90 minutos (disponível para o CJA Prime)</li><li>Assimilação prioritária do CJA Avançada: dados com 1 semana de duração no processamento SLT de 90 minutos (disponível para o CJA Ultimate)</li></ul> |  | 12 de junho de 2024 |
| **Compartilhar contas e locais usados para exportação e importação** | Agora os usuários podem disponibilizar as contas e os locais que criam para todos os usuários em sua organização. Somente os proprietários de contas e locais e os administradores do sistema podem editar e excluir contas e locais. Anteriormente, contas e locais podiam ser usados somente pelo usuário que os criava. Essas configurações estão disponíveis quando os usuários [configurar contas de exportação da nuvem](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) e [configurar locais de exportação da nuvem](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 de junho de 2024 | 30 de junho de 2024 |
| **Selecionar vários campos em um filtro suspenso** | Quando vários campos são adicionados a um filtro suspenso, os usuários podem selecionar mais de um campo por vez. O painel é filtrado para incluir qualquer um dos campos selecionados. <p>Anteriormente, os usuários podiam selecionar apenas um campo por vez em um filtro suspenso.</p><p>(Link de documentação em breve.)</p> |  | quinta-feira, 19 de junho de 2024 |
| **Sumário de projetos do Workspace** | Um novo sumário está disponível para projetos. O índice fornece links que permitem aos usuários ir rapidamente para painéis e visualizações no projeto. <p>O índice pode ser ativado para projetos individuais ou para todos os projetos de um determinado usuário.</p><p>(Link de documentação em breve.)<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | quinta-feira, 19 de junho de 2024 |
| **Criar hiperlinks para itens de dimensão em uma tabela de forma livre** | É possível criar hiperlinks para um ou mais itens de dimensão para torná-los clicáveis em uma tabela de forma livre no Analysis Workspace. <p>Você pode criar hiperlinks para itens de dimensão com valores de URL ou criar URLs personalizados para itens de dimensão com valores que não sejam de URL.</p><p>Você pode criar URLs personalizados dinâmicos para vários itens de dimensão usando variáveis. As variáveis podem fazer referência ao valor de um item de dimensão ou à dimensão de detalhamento.</p><p>(Link de documentação em breve.)<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | quinta-feira, 19 de junho de 2024 |
| **Use a visualização de dados do Customer Journey Analytics com o Adobe Journey Optimizer** | Uma nova opção de configuração no Customer Journey Analytics permite designar uma visualização de dados de Customer Journey Analytics a ser usada com o Adobe Journey Optimizer, sem a necessidade de configuração manual. <!-- add this in: <p>For information about how to enable this configuration option, see the [Compatibility](/help/data-views/create-dataview.md#compatibility) section in [Create or edit a data view](/help/data-views/create-dataview.md).</p> --><p>Anteriormente, você tinha que configurar manualmente uma conexão e visualizações de dados ao visualizar dados do Adobe Journey Optimizer no Customer Journey Analytics.</p><p>(Link da documentação em breve)</p> |  | quinta-feira, 19 de junho de 2024 |
| **Os públicos-alvo são publicados em uma nova seção “Públicos-alvo” na Experience Platform** | Os públicos-alvo publicados a partir do Customer Journey Analytics agora estão disponíveis na nova seção “Públicos-alvo” na Adobe Experience Platform.<p>Anteriormente, os públicos-alvo publicados a partir do Customer Journey Analytics apareciam na seção “Segmentos” da Experience Platform. </p><p>Esta melhoria fornece os seguintes benefícios:</p><ul><li>Os públicos-alvo não possuem mais um atraso de 1 hora para exibição na Experience Platform, pois são disponibilizados segundos após a publicação.</li><li>Os públicos-alvo podem ser classificados na Experience Platform usando a coluna “Origem”, que exibe o aplicativo a partir do qual o público-alvo foi originalmente publicado.</li><li>As opções Filtrar e Classificar da Experience Platform permitem encontrar os públicos-alvo relevantes com mais rapidez.</li></ul> <p>(Link da documentação em breve)</p> |  | segunda-feira, 14 de julho de 2024 |

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
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
