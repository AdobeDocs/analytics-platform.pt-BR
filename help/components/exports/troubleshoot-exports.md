---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Solução de problemas de exportações com falha
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
source-git-commit: 05cc65f3a463bc71db85d85292a172784c3d7c75
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 7%

---

# Solução de problemas de exportações com falha

Quando você [exportar tabelas completas do Analysis Workspace para destinos na nuvem](/help/analysis-workspace/export/export-cloud.md), você poderá visualizar o status dessas exportações na [Guia Exportações](/help/components/exports/manage-exports.md) e do [Guia Logs](/help/components/exports/manage-export-logs.md). Exportações com falha mostram um status de [!UICONTROL **Failed**].

## Falhas e ações comuns

As exportações podem falhar por vários motivos. A tabela a seguir descreve alguns dos motivos mais comuns, com ações que você pode tomar para resolver as falhas:

| Motivo da falha | Ação sugerida | Mais informações |
|---------|----------|---------|
| Informações de conta ou localização inválidas | Verifique se suas credenciais e outras informações estão corretas para a conta na nuvem e o local para o qual você está exportando. | [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md). |
| Uma dimensão ou métrica no relatório foi removida da visualização de dados | Entre em contato com o administrador do sistema para ver quais componentes foram removidos da visualização de dados. Talvez seja necessário usar uma visualização de dados diferente na exportação ou remover componentes da tabela que não estão mais disponíveis. | [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md) |
| Limite de linha excedido | Dependendo do tipo de licença, você pode exportar no máximo 3 milhões, 30 milhões, 150 milhões ou 300 milhões de linhas. Atualize a tabela que você está exportando para reduzir o número total de linhas. | [Exportar relatórios de Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md) |
| Expiração de exportação agendada | A exportação agendada que você configurou expirou. Atualize a expiração da exportação. | [Gerenciar exportações](/help/components/exports/manage-exports.md) |
| Dimension não suportado | <p>Qualquer dimensão que atenda a todos os critérios a seguir não é suportada na Exportação de tabela completa:</p> <ul><li>Foi criado a partir de um campo que faz parte de uma matriz de objetos</li><li>Tem persistência ativada<li>Não está usando uma dimensão de ligação</li> | <ul><li>[Uso de arrays de objetos](/help/use-cases/object-arrays.md)</li><li>Configurações de componente de [Persistência](/help/data-views/component-settings/persistence.md)<li>[Uso de dimensões e métricas de ligação no Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Uma política de governança de dados imposta por sua organização impede que os componentes da tabela sejam exportados | Entre em contato com o administrador do sistema para ver quais componentes estão impedidos de serem exportados. Remova os componentes restritos antes da exportação. | *Filtrar as políticas de governança de dados nas visualizações de dados* seção em [Rótulos e políticas](/help/data-views/data-governance.md) |

## Entre em contato com o Atendimento ao cliente da Adobe

Se o problema persistir, entre em contato com o Atendimento ao cliente da Adobe. Ao entrar em contato com o Atendimento ao cliente sobre uma exportação com falha, verifique se você tem as seguintes informações disponíveis:

* Nome da exportação

* ID de exportação

* ID da instância

* Nome da visualização de dados

* Localização

* Conta

* Conexão

* Nome da empresa
