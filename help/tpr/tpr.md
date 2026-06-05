---
title: Relatório de População Total
description: Use os relatórios de população total no Customer Journey Analytics para analisar perfis e contas em seus conjuntos de dados, independentemente da atividade do evento ou dos intervalos de datas do painel.
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: f7bbbaf0b737ab33088c7c585d6415f93deff4c8
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 4%

---

# Relatório de população total

Os relatórios de população total apresentam a capacidade de analisar e relatar entidades definidas em conjuntos de dados de perfil e pesquisa e além de séries de eventos com base no tempo de conjuntos de dados de eventos. Essa capacidade permite novas classes de consultas, métricas e definições de público-alvo que refletem o escopo completo de uma base de clientes empresariais.

O Customer Journey Analytics é construído em torno de eventos. Cada métrica, cada visualização, cada painel, cada relatório é ancorado em um intervalo de datas e em eventos que ocorrem durante esse intervalo de datas. Você faz perguntas sobre as soluções, como:

| Pergunta | Evento | Intervalo de data e hora |
|---|---|---|
| Quantas pessoas fizeram uma compra na semana passada? | compra | semana passada |
| Quantas contas visitaram a página de preços no primeiro trimestre? | visita | T1 |

O intervalo de datas do painel do espaço de trabalho filtra os dados, e suas dimensões e métricas descrevem o que aconteceu durante esse intervalo de datas.

Mas nem todas as perguntas que sua empresa precisa responder são sobre algo que aconteceu. Às vezes, você precisa saber sobre sua própria população.

| Pergunta | Evento | Intervalo de data e hora |
|---|---|---|
| Quantos clientes ativos temos agora? | N/D | N/D |
| Quantas contas existem em nosso banco de dados? | N/D | N/D |
| Quantos de nossos membros não fizeram uma compra nos últimos 30 dias? | N/D | últimos 30 dias |

Essas perguntas não são sobre eventos, mas sobre pessoas e contas que existem, quer essas pessoas ou contas tenham ou não feito algo recentemente.

Os relatórios de população total apresentam uma nova classe de métricas que informam dados de perfil. Esses dados de perfil, que podem conter pessoas e contas, nos conjuntos de dados de perfil são independentes do intervalo de datas de um painel. Com os relatórios de população total, é possível combinar métricas de população e métricas de evento na mesma análise, fornecendo uma imagem mais abrangente de quem são seus clientes e o que o cliente fez.

O relatório de população total permite que o Customer Journey Analytics relate todas as entidades definidas nos conjuntos de dados de perfil e pesquisa, independentemente da atividade do evento. Esses relatórios incluem:

* **Consultas baseadas em perfil**: Analisar atributos (independentemente dos eventos) de perfis (todas as pessoas, contas, oportunidades e grupos de compras).
* **Perfil menos consultas de evento**: identifique perfis (todas as pessoas, contas, oportunidades e grupos de compras) que não executaram uma ação ou experiência específica durante a janela de relatórios.
* **Pesquisas compartilhadas**: dão suporte à reutilização de conjuntos de dados de pesquisa em várias entidades para reduzir os custos de assimilação e melhorar o desempenho.

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## Métricas de relatório de população total

As métricas de relatório de população total se comportam de forma diferente das métricas normalmente usadas no Customer Journey Analytics:

* As métricas de relatório de população total não estão vinculadas ao intervalo de datas do painel. Uma métrica de relatório de população total como **[!UICONTROL Total de pessoas (Perfil)]** retorna a população atual do conjunto de dados do seu perfil, independentemente do intervalo de datas aplicado ao painel. Os filtros de data e as comparações de intervalo de datas não afetam as métricas de relatório da população total da maneira como esses filtros e comparações afetam as métricas de evento.
* O relatório de população total requer um conjunto de dados de perfil na conexão. As métricas de relatório de população total só aparecem quando sua conexão inclui pelo menos um conjunto de dados de perfil junto com pelo menos um conjunto de dados de evento. As conexões somente com conjuntos de dados de evento continuam a funcionar exatamente como antes e não mostram as métricas de relatório de população total.

No Workspace, as métricas de população total são marcadas com um ícone distinto (TBD), para que você possa identificar rapidamente quais métricas respeitam o intervalo de datas do painel e quais métricas não respeitam. As métricas de população total podem ser usadas junto com as métricas de evento na maioria dos lugares, mas os tipos de visualização que dependem das sequências de eventos (como Fallout e Fluxo) não são compatíveis.

### Métricas padrão de relatório de população total

Por padrão, o sistema inclui três métricas padrão de relatório de população total, disponíveis em qualquer visualização de dados cuja conexão inclui um conjunto de dados de perfil:

* **Total de pessoas (Perfil)**: a contagem total de pessoas no conjunto de dados do perfil.
* **Total de contas (Perfil)**: a contagem total de contas no conjunto de dados do perfil. [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **Total de Pessoas (Perfil + Evento)**: uma contagem de união que combina pessoas com escopo de perfil com pessoas com escopo de evento.

Você também pode criar métricas personalizadas com qualquer um dos três escopos, usando campos dos conjuntos de dados do seu perfil.

## Requisitos, pré-requisitos e considerações

Para que os relatórios de população total funcionem corretamente, os pré-requisitos, requisitos e considerações devem ser considerados.

### Requisitos de conexão

Para uma conexão para suportar relatórios de população total:

* Pelo menos um conjunto de dados de evento é necessário para a conexão. Conexões somente de perfil não são suportadas.
* Pelo menos um conjunto de dados de perfil deve ser adicionado à conexão. As métricas de relatório de população total não aparecem nas visualizações de dados que são criadas em conexões que contêm apenas dados de evento.
* As pesquisas compartilhadas devem ser configuradas para cada conjunto de dados de perfil. As pesquisas compartilhadas definem como cada conjunto de dados de perfil é unido aos eventos em sua conexão especificando a chave correspondente, o namespace (para campos do mapa de identidade) e o caminho de associação.

#### Configuração do conjunto de dados do perfil

Quando um conjunto de dados de perfil é adicionado a uma conexão, o Customer Journey Analytics preenche uma configuração de pesquisa compartilhada padrão com base no tipo de conjunto de dados:

* Para conjuntos de dados de perfis de pessoas: o padrão é corresponder por contêiner definido como [!UICONTROL Pessoa], com o mapa de identidade como o campo de chave. Você pode editar esse padrão. Por exemplo, para escolher um namespace específico no mapa de identidade em vez da chave primária. Ou para especificar um namespace secundário para casos em que o primeiro namespace não é preenchido (o que é comum com conjuntos de dados compilados).
* Para conjuntos de dados de perfil de conta [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: o padrão é corresponder por contêiner definido como [!UICONTROL Conta] (ou [!UICONTROL Conta Global], se as contas globais estiverem habilitadas na conexão). O campo de conta pode ser um único identificador ou um mapa de identidade. Quando o campo de conta é um mapa de identidade, você seleciona o namespace a ser usado.

Você pode configurar várias pesquisas compartilhadas em um único conjunto de dados de perfil para oferecer suporte a vários caminhos de associação para seus eventos. Quando o mesmo mapa de identidade é usado como o campo principal em várias pesquisas compartilhadas, as seleções de namespace devem ser consistentes.

### Requisitos de visualização de dados

Para que as métricas de relatório de população total funcionem corretamente em uma visualização de dados:

* A conexão deve incluir um conjunto de dados de perfil (consulte [Requisitos de conexão](#connection-requirements)). Se você remover o último conjunto de dados de perfil restante de uma conexão, as métricas de relatório de população total não estarão disponíveis nas visualizações de dados criadas com base nele.
* [Os segmentos de nível de visualização de dados](/help/data-views/create-dataview.md#settings-segments) não devem ser explícitos para eventos. Se um segmento aplicado diretamente à visualização de dados for definido inteiramente em termos de condições de escopo de evento (por exemplo, `hit where page = X`), o relatório de população total não será possível nessa visualização de dados. Antes de depender das métricas de relatório de população total, valide se os segmentos de nível de visualização de dados são compatíveis com os relatórios de escopo de perfil.
* O escopo da métrica deve ser definido corretamente. Ao criar um componente de métrica personalizado no construtor de visualizações de dados, selecione o escopo apropriado (evento, perfil ou perfil + evento) com base no conjunto de dados do campo e em como você deseja que a métrica se comporte. O escopo não pode ser alterado depois que a métrica é usada em públicos ou relatórios recorrentes sem romper essas dependências.

### Compatibilidade com o Workspace

As métricas do relatório de população total podem ser usadas junto com as métricas baseadas em eventos na maioria dos contextos do Workspace: [tabelas de forma livre](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), [linha](/help/analysis-workspace/visualizations/line.md), [barra](/help/analysis-workspace/visualizations/bar.md) e [visualizações de barra horizontal](/help/analysis-workspace/visualizations/horizontal-bar.md), [tabelas de coorte](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) quando configuradas adequadamente e assim por diante. Alguns tipos de visualização não são compatíveis, pois dependem inerentemente das sequências de eventos:

* [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [Fluxo](/help/analysis-workspace/visualizations/c-flow/flow.md)
* tipos de visualização adicionais não suportados que serão confirmados antes da publicação.

Quando você adiciona uma métrica de relatório de população total a uma visualização não compatível, o Workspace indica que a métrica não pode ser usada nesse contexto.

### Considerações sobre o público

Os públicos-alvo criados com base nas métricas de relatório de população total dependem das métricas que permanecem presentes na visualização de dados:

* Um público-alvo recorrente que usa uma métrica de relatório de população total falha e passa para um estado ERRO se a métrica de relatório de população total for removida da visualização de dados.
* A interface do Customer Journey Analytics impede a remoção de uma métrica, enquanto qualquer público recorrente ativo depende da métrica e fornece orientação sobre a dependência antes de confirmar a remoção.

### Permissões

A ser confirmado: quaisquer requisitos de acesso a funções ou recursos na organização IMS do cliente ou no perfil de produto antes que as métricas de relatório de população total estejam visíveis. Vale a pena sinalizar para PM antes da publicação.
