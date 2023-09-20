---
description: Gerenciar logs para exportações existentes
keywords: Analysis Workspace
title: Solução de problemas de exportações com falha
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 3%

---

# Solução de problemas de exportações com falha

Quando você [exportar tabelas completas do Analysis Workspace para destinos na nuvem](/help/analysis-workspace/export/export-cloud.md), você poderá visualizar o status dessas exportações na [Guia Exportações](/help/components/exports/manage-exports.md) e do [Guia Logs](/help/components/exports/manage-export-logs.md). Exportações com falha mostram um status de [!UICONTROL **Failed**].

As exportações podem falhar por vários motivos. A tabela a seguir descreve alguns dos motivos mais comuns, com ações que você pode tomar para resolver as falhas:

| Motivo da falha | Ação sugerida | Mais informações |
|---------|----------|---------|
| Informações de conta ou localização inválidas | Verifique se suas credenciais e outras informações estão corretas para a conta na nuvem e o local para o qual você está exportando. | [Configurar contas de exportação da nuvem](/help/components/exports/cloud-export-accounts.md) e [Configurar locais de exportação da nuvem](/help/components/exports/cloud-export-locations.md). |
| Uma dimensão ou métrica no relatório foi removida da visualização de dados | Entre em contato com o administrador do sistema para ver quais componentes foram removidos da visualização de dados. Talvez seja necessário usar uma visualização de dados diferente na exportação ou remover componentes da tabela que não estão mais disponíveis. | [Exportar dados do Customer Journey Analytics para a nuvem](/help/analysis-workspace/export/export-cloud.md) |
| Uma política de governança de dados imposta por sua organização impede que os componentes da tabela sejam exportados | Entre em contato com o administrador do sistema para ver quais componentes estão impedidos de serem exportados. Remova os componentes restritos antes da exportação. | *Filtrar as políticas de governança de dados nas visualizações de dados* seção em [Rótulos e políticas](/help/data-views/data-governance.md) |