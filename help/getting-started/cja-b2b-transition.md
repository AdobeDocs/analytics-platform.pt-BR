---
title: Guia de transição
description: Saiba como fazer a transição do Customer Journey Analytics para o Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# Guia de transição

Este guia discute como fazer a transição do Customer Journey Analytics para o B2B edition do Customer Journey Analytics.

O artigo pressupõe que você já usa o Customer Journey Analytics até certo ponto:

* Você tem [conexões](/help/connections/overview.md) que assimilam dados na Customer Journey Analytics.
* Você tem [visualizações de dados](/help/data-views/data-views.md) que usam os dados dessas conexões.
* Você tem [projetos](/help/analysis-workspace/home.md) com relatórios e visualizações que usam essas visualizações de dados.

Se você não tiver usado o Customer Journey Analytics antes, consulte o [guia de início rápido do B2B edition](cja-b2b-quick-start-guide.md).

Se você for um usuário do Adobe Analytics e planeja usar o Customer Journey Analytics B2B edition, primeiro consulte a [documentação de atualização do Adobe Analytics para o Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Implementação existente

A implementação existente do Customer Journey Analytics não é alterada depois que você é licenciado e provisionado para o Customer Journey Analytics B2B edition.

Todas as conexões existentes são consideradas [conexões baseadas em pessoas](cja-b2b-concepts-features.md#connections-and-identifiers) e continuam a funcionar sem nenhuma atualização. Tudo que depende dos dados dessas conexões com base em pessoas, como visualizações de dados, projetos do espaço de trabalho, segmentos, exportações programadas, alertas e muito mais, continua funcionando conforme planejado e planejado originalmente.

>[!IMPORTANT]
>
>Você não pode alterar as conexões com base em pessoas existentes para uma conexão com base em conta. É necessária uma nova conexão baseada em conta para usar os recursos do B2B edition.
>


## Implementar recursos B2B

Para implementar recursos B2B na implementação existente, é necessário seguir estas etapas:

1. Modelar seus dados B2B. O Customer Journey Analytics B2B edition presume pelo menos dados de eventos de série temporal baseados em conta e se beneficia de dados adicionais de perfil ou registro de pesquisa. Como dados de conta, dados de grupo de compras, dados de oportunidade, dados de membro da lista de marketing e muito mais.

   * Defina qual identificador você deseja usar como o identificador de conta principal (ID da conta). Geralmente, um CRM existente ou outra ferramenta (por exemplo: Demandbase) ajuda a determinar esse identificador.
   * Identifique identificadores adicionais para os outros dados B2B que você planeja usar: identificador de conta global, identificador de oportunidade, identificador de grupo de compra e identificador de pessoa.

1. Prepare seus dados B2B. Adicione e colete identificadores de conta em todos os dados de evento de série temporal e dados de registro relevantes. Da mesma forma, verifique se os dados do evento de série temporal e o registro de pesquisa contêm outros identificadores para eventos relevantes. Por exemplo: um evento que sinaliza a mudança para outro estágio de vendas deve ter um identificador de oportunidade. E esse identificador deve fazer parte dos dados de pesquisa da oportunidade.

1. [Criar uma nova conexão baseada em conta](/help/connections/create-connection.md#account-based-connection). Selecione quais contêineres opcionais você deseja incluir, [adicione conjuntos de dados](/help/connections/create-connection.md#add-datasets) e defina as [configurações para cada conjunto de dados](/help/connections/create-connection.md#dataset-settings). Use [correspondência por contêiner](cja-b2b-concepts-features.md#match-by-container) para conjuntos de dados de registro de pesquisa sempre que possível.

1. [Criar visualizações de dados](/help/data-views/create-dataview.md) com base em sua nova conexão.

   * Adicione todos os campos relevantes como métricas ou dimensões dos dados assimilados.
   * Aplique configurações de componente (como persistência, atribuição e muito mais), se necessário.
   * Adicione outros campos derivados quando apropriado.

1. [Crie projetos do espaço de trabalho](/help/analysis-workspace/build-workspace-project/create-projects.md) para criar relatórios e obter insights sobre seus dados B2B. Use recursos B2B específicos, como [containers](cja-b2b-concepts-features.md#containers), para obter insights profundos.

   Você pode combinar relatórios e insights B2B (com base em pessoas) e B2B (com base em contas) usando vários [painéis](/help/analysis-workspace/c-panels/panels.md) em um projeto do espaço de trabalho.
