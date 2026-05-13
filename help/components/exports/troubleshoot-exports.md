---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Solução de problemas de exportações com falha
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
TQID: https://experienceleague.adobe.com/pKXaX-DMxsFn9Y39AjqL1VGaSM--WFda9fuD7zJLgoI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 390
ht-degree: 7%

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
