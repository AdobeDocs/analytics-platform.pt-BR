---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9e6231e4dc9770fbb7c859b397ea8c57e7dff478
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 37%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (julho de 2023)

**Última atualização**: 13 de julho de 2023

As versões do Adobe Customer Journey Analytics operam em uma [modelo de entrega contínua](releases.md) que permite uma abordagem mais escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics é uma nova maneira de interagir com dados e insights entre canais no Customer Journey Analytics. Esses novos recursos permitem que as equipes de produtos utilizem o autoatendimento de dados e insights sobre a experiência do produto por meio de fluxos de trabalho de análise guiados. As equipes podem:<ul><li>Entender padrões no engajamento dos usuários ao longo do tempo</li><li>Controle o crescimento e a retenção da base de usuários do produto&#x200B;</li><li>Identificação de áreas de atrito no produto</li><li>Meça o impacto das versões de recursos&#x200B; e o primeiro uso</li><li>Descubra segmentos significativos de usuários para se envolver e promover durante toda a jornada ao longo da vida com o produto&#x200B;</li><li>Conecte-se à Analysis Workspace para análise e colaboração mais profundas com analistas</li></ul>O Adobe Product Analytics é um complemento pago do Customer Journey Analytics. Se sua organização quiser que a use esse recurso, entre em contato com a equipe de conta do Adobe. [Saiba mais](/help/guided-analysis/overview.md) | N/D | 17 de julho de 2023 |
| **Campos derivados** | Isto representa a versão inicial dos Campos derivados. Um campo derivado permite definir manipulações de dados (muitas vezes complexas) a qualquer momento, por meio de um criador de regras personalizável. Você pode definir ainda mais o campo derivado como um componente (métrica ou dimensão) nas visualizações de dados e, em seguida, usar o campo derivado como um componente no Workspace.<p>Essa versão é compatível com um modelo de canais de marketing e as seguintes funções:</p><ul><li>Concatenar</li><li>Caso Quando</li><li>Localizar e Substituir</li><li>Pesquisa</li><li>Análise de URL</li></ul> <p>[Saiba mais](/help/data-views/derived-fields/derived-fields.md)</p> | 10 de maio de 2023 | 2 de agosto de 2023 |
| **Suporte expandido de pesquisa para dados de Perfil e Pesquisa** | Fornece a capacidade de adicionar conjuntos de dados como pesquisas de campos no Perfil ou Conjuntos de dados de pesquisa. Anteriormente, somente os conjuntos de dados de eventos eram compatíveis. [Saiba mais](/help/connections/create-connection.md) | 21 de junho de 2023 | 12 de julho de 2023 |
| **Aprimoramentos de Report Builder** | <ul><li>Filtrar da célula para vários blocos de dados. É possível alterar os filtros em vários blocos de dados de uma célula. Use uma célula predefinida, atribua-a a vários blocos de dados e atualize os dados com base nos filtros definidos na célula. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>Mostrar e ocultar cabeçalhos de linha e coluna. Você pode mostrar ou ocultar cabeçalhos de tabelas de blocos de dados ou cabeçalhos de linhas e colunas para reformatar a tabela e alinhar blocos de dados em um relatório. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | N/D | 19 de julho de 2023 |
| **Pesquisas geográficas do Experience Edge** | O Adobe Experience Edge está adicionando um serviço de pesquisa geográfica que fornece dados geográficos unificados para todos os usuários do Experience Edge (Adobe Analytics, Customer Journey Analytics, Adobe Target, Adobe Medium Analytics, Adobe Experience Platform etc.). | N/D | 26 de julho de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-317971; AN-319234; AN-320439; AN-320519; AN-321740; AN-322444; AN-323116

## Avisos importantes para administradores do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Alterações na forma como o Customer Journey Analytics processa dados** | 22 de junho de 2023 | Recentemente, alteramos a forma como processamos dados no Customer Journey Analytics.<ul><li>Todos os dados de evento com um carimbo de data e hora menor que 24 horas são transmitidos no.</li><li>Quaisquer dados de evento com um carimbo de data e hora de mais de 24 horas (mesmo que estejam no mesmo lote que os dados mais recentes) são considerados preenchimento retroativo e serão assimilados em uma prioridade mais baixa.</li></ul> |

{style="table-layout:auto"}

## Avisos de fim da vida útil (EOL)

| Fim da vida útil do produto ou recurso | Data de adição ou atualização | Descrição |
| --- | --- | --- |
| **Migração para credenciais de servidor para servidor do OAuth do Adobe I/O** | 11 de maio de 2023 | Os clientes da API do Adobe Analytics, da API de Customer Journey Analytics e do Livestream que usam as credenciais JWT do Adobe I/O devem migrar para as credenciais de servidor para servidor do Adobe I/O OAuth por **1 de janeiro de 2025**. O Adobe I/O não permitirá que novas credenciais JWT sejam criadas a partir de 1º de maio de 2024. Os clientes que usam JWT devem criar uma nova credencial de servidor para servidor OAuth ou migrar sua credencial JWT existente para uma credencial de servidor para servidor OAuth. Os clientes também devem atualizar seus aplicativos cliente para usar as novas credenciais de servidor para servidor do OAuth. <ul><li>[Migração de credenciais da Conta de serviço (JWT)](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[Utilização das novas credenciais de servidor para servidor do OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[Perguntas frequentes](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics para 2023](/help/release-notes/2023.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
