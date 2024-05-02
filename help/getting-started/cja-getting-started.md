---
title: Introdução ao Customer Journey Analytics
description: Entenda os pré-requisitos e o fluxo de trabalho necessários para implementar o Customer Journey Analytics.
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 88%

---

# Introdução ao Customer Journey Analytics

Para implementar o Customer Journey Analytics, é necessário seguir esse fluxo de trabalho. Algumas tarefas iniciais são executadas na Adobe Experience Platform e outras no Customer Journey Analytics.

## Pré-requisitos

O Customer Journey Analytics está disponível para clientes que

* são provisionados para a [Adobe Experience Platform](https://www.adobe.com/br/experience-platform.html) e
* adquiriram a SKU do Customer Journey Analytics.

## Fluxo de trabalho

| Tarefa | Detalhes |
| --- | --- |
| **Etapa 1: Se estiver atualizando do Adobe Analytics para o Customer Journey Analytics: escolha um caminho de atualização e envie dados para o Adobe Experience Platform** | Há vários caminhos disponíveis ao atualizar do Adobe Analytics para o Customer Journey Analytics. Cada caminho de atualização possível tem suas próprias vantagens e desvantagens, e um caminho que seja adequado para uma organização pode não fazer sentido para outra. <p>Para começar a atualização do Adobe Analytics para o Customer Journey Analytics, consulte [Introdução à atualização para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **Etapa 2: Transfira outros dados para a Adobe Experience Platform** | Esta etapa, realizada na Adobe Experience Platform, envolve várias subetapas:<ul><li>**Etapa 2a: Prepare seu esquema de dados**: Use o [Adobe Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=pt-BR) para padronizar os dados de experiência do cliente e [definir schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=pt-BR) para o gerenciamento da experiência do cliente.</li><li>**Etapa 2b: crie um conjunto de dados com base no esquema**: os dados da Platform consistem em conjuntos de dados, como conjuntos de dados de email, de CRM, de POS, do Adobe Analytics etc. Cada conjunto de dados consiste de um esquema e lotes de dados. Você pode [criar um conjunto de dados na Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=pt-BR).</li><li>**Etapa 2c: assimilar dados na Experience Platform**: Aqui, você tem várias opções.</li></ul> |
| **Etapa 3: Criar conexões entre conjuntos de dados da plataforma e do Customer Journey Analytics** | Uma conexão permite integrar conjuntos de dados da Adobe Experience Platform ao Espaço de trabalho. Para criar relatórios sobre conjuntos de dados da Experience Platform, primeiro é necessário estabelecer uma conexão entre os conjuntos de dados na Experience Platform e no Espaço de trabalho.<br>Consulte [Criar ou editar uma conexão](/help/connections/create-connection.md). |
| **Etapa 4: Criar visualizações de dados** | Uma visualização de dados é uma visualização “filtrada” dos dados. É possível criar visualizações de dados diferentes para a mesma conexão, com configurações diferentes para o tempo limite da visita, atribuição etc. É possível criar várias visualizações de dados para um único conjunto de dados.<br>Consulte [Criar uma visualização de dados](/help/data-views/create-dataview.md). |
| **Etapa 5: importar o uso da API de relatórios**</br> Aplica-se somente ao migrar do Adobe Analytics | A API de relatórios do Customer Journey Analytics está no mesmo formato, mas usa um ponto de acesso diferente. Importe o uso da API de relatórios do Adobe Analytics para a do Customer Journey Analytics. |
| **Etapa 6: casos de uso de contas para feeds de dados e data warehouse**</br> Aplica-se somente ao migrar do Adobe Analytics | Decida como usar as opções de exportação disponíveis no Customer Journey Analytics para replicar melhor os recursos de feed de dados e data warehouse usados no Adobe Analytics. <!-- link to docs Rob is creating --> |
| **Etapa 7: migrar projetos e componentes**</br> Aplica-se somente ao migrar do Adobe Analytics | A área de migração de componentes do Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics.<p>O processo de migração inclui:</p><ul><li>Recriação de projetos do Adobe Analytics no Customer Journey Analytics.</li><li>Mapeamento de dimensões e métricas de conjuntos de relatórios do Adobe Analytics de acordo com as dimensões e métricas das visualizações de dados do Customer Journey Analytics.</li></ul><p>Antes de iniciar a migração, [prepare-se para migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=pt-BR).</p><p>Depois de fazer todos os preparativos necessários, você poderá [migrar os componentes e projetos do Adobe Analytics para o Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=pt-BR).</p> |
| **Etapa 8: planejar a integração de usuários** | Como no Adobe Analytics, o Analysis Workspace é a principal ferramenta voltada para usuários do Customer Journey Analytics. No entanto, é necessário considerar algumas diferenças importantes de se usar o Analysis Workspace no Customer Journey Analytics.<p>Dê a seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics.</p><p>Para mais informações sobre algumas das principais diferenças entre o Adobe Analytics e o Customer Journey Analytics, consulte o [Guia para usuários do Adobe Analytics](/help/getting-started/aa-to-cja-user.md).</p> |
| **Etapa 9: relatório dos dados entre canais no Workspace** | Depois de criar conexões e visualizações de dados, analise os dados que você trouxe usando o potencial e a flexibilidade do Analysis Workspace.<br>Consulte [Fazer análise básica](/help/analysis-workspace/perform-basic-analysis.md) e [Fazer análise avançada](/help/analysis-workspace/perform-adv-analysis.md). |

## Guias de início rápido

A seção [Assimilação de dados](../data-ingestion/data-ingestion.md) fornece guias de início rápido sobre o fluxo de trabalho acima. Esses guias de início rápido ilustram como assimilar dados de uma variedade de fontes (incluindo o Adobe Analytics) na Adobe Experience Platform e, em seguida, usar esses dados no Customer Journey Analytics.
