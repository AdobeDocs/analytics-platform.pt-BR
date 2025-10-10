---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Solução de problemas de exportações com falha
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 8%

---

# Solução de problemas de exportações com falha

Ao [exportar tabelas completas do Analysis Workspace para destinos na nuvem](/help/analysis-workspace/export/export-cloud.md), você pode visualizar o status dessas exportações na [guia Exportações](/help/components/exports/manage-exports.md) e na [guia Logs](/help/components/exports/manage-export-logs.md). Exportações com falha mostram um status de [!UICONTROL **Falha**].

## Falhas e ações comuns

As exportações podem falhar por vários motivos. A tabela a seguir descreve alguns dos motivos mais comuns, com ações que você pode tomar para resolver as falhas:

| Motivo da falha | Ação sugerida | Mais informações |
|---------|----------|---------|
| Localização ou informações da conta inválidas | Verifique se suas credenciais e outras informações estão corretas para a conta na nuvem e o local para o qual você está exportando. | [Configurar contas de exportação na nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar locais de exportação na nuvem](/help/components/exports/cloud-export-locations.md). |
| Uma dimensão ou métrica no relatório foi removida da visualização de dados | Entre em contato com o administrador do sistema para ver quais componentes foram removidos da visualização de dados. Talvez seja necessário usar uma visualização de dados diferente na exportação ou remover componentes da tabela que não estão mais disponíveis. | [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md) |
| Limite de linha excedido | Dependendo do tipo de licença, você pode exportar no máximo 3 milhões, 30 milhões, 150 milhões ou 300 milhões de linhas. Atualize a tabela que você está exportando para reduzir o número total de linhas. | [Exportar relatórios do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md) |
| Expiração de exportação agendada | A exportação agendada que você configurou expirou. Atualize a expiração da exportação. | [Gerenciar exportações](/help/components/exports/manage-exports.md) |
| Dimension não compatível | <p>Qualquer dimensão que atenda a todos os critérios a seguir não é suportada na Exportação de tabela completa:</p> <ul><li>Foi criado a partir de um campo que faz parte de uma matriz de objetos</li><li>Tem persistência ativada<li>Não está usando uma dimensão de ligação</li> | <ul><li>[Uso de matrizes de objetos](/help/use-cases/object-arrays.md)</li><li>[Configurações de componente de Persistência](/help/data-views/component-settings/persistence.md)<li>[Usar dimensões e métricas de ligação no Customer Journey Analytics](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| Uma política de governança de dados imposta por sua organização impede que os componentes da tabela sejam exportados | Entre em contato com o administrador do sistema para ver quais componentes estão impedidos de serem exportados. Remova os componentes restritos antes da exportação. | *Filtrar as políticas de Governança de Dados na seção de visualizações de dados* em [Rótulos e políticas](/help/data-views/data-governance.md) |

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
