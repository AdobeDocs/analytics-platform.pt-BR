---
title: Exibir as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8f299dad39678047d362291cfe8a2a3c116071dd
workflow-type: ht
source-wordcount: '571'
ht-degree: 100%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (agosto de 2023)

**Última atualização**: 24 de agosto de 2023

Essas notas de versão abrangem o período de lançamento de 9 de agosto a 13 de setembro de 2023. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Aprimoramentos do Report Builder** | <ul><li>É possível baixar uma tarefa agendada na guia Pastas de trabalho e, em seguida, nomeá-la, salvá-la e compartilhá-la. [Saiba mais](/help/report-builder/schedule-reportbuilder.md)</li><li>A data inicial como dimensão permite apresentar a data inicial do bloco de dados como uma dimensão na saída do bloco de dados. [Saiba mais](/help/report-builder/create-a-data-block.md) </li></ul> | N/D | 17 de agosto de 2023 |
| **Conversão de moeda** | A jornada do cliente está recebendo compatibilidade com várias moedas. É possível converter moedas nas configurações das visualizações de dados. [Saiba mais](/help/data-views/component-settings/format.md) | N/D | 30 de agosto de 2023 |
| **Suporte para classificações do A4T no conector de origem do Analytics** | Estamos adicionando uma ID de correlação para facilitar a junção de dados de classificação em atividades do Adobe Target e eventos de experiência. | N/D | 11 de setembro de 2023 |
| **Gerenciador de atividades de relatórios** | Fornece uma visão detalhada aos administradores sobre o consumo de relatórios em cada conexão, permitindo diagnosticar e corrigir problemas de capacidade facilmente durante os momentos de pico de relatórios. | N/D | 12 de setembro de 2023 |
| **Acesso do Power BI e do Tableau às visualizações de dados do Customer Journey Analytics** | O conector SQL do Adobe Customer Journey Analytics permite acesso SQL a visualizações de dados definidas no Customer Journey Analytics. Analistas e engenheiros de dados mais familiarizados com o Power BI, Tableau ou outras ferramentas de business intelligence e visualização agora podem criar relatórios e painéis com base nas mesmas visualizações de dados que os usuários do Customer Journey Analytics estão usando nos seus projetos do Analysis Workspace. [Saiba mais](/help/data-views/sql-connector.md) | N/D | 12 de setembro de 2023 |

{style="table-layout:auto"}

## Correções no Customer Journey Analytics

AN-309141; AN-319198; AN-324576; AN-324939; AN-325138; AN-325554

## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Alterações na forma como o Customer Journey Analytics processa dados** | 22 de junho de 2023 | Recentemente, alteramos a forma como processamos dados no Customer Journey Analytics.<ul><li>Todos os dados de evento com um carimbo de data e hora inferior a 24 horas são transmitidos.</li><li>Quaisquer dados de evento com um carimbo de data e hora superior a 24 horas (mesmo que estejam no mesmo lote que os dados mais recentes) são considerados de preenchimento retroativo e serão assimilados com uma prioridade mais baixa.</li></ul> |

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
