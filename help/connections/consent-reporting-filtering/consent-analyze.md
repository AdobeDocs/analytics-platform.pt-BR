---
title: Analisar dados de política de consentimento no Customer Journey Analytics
description: Saiba como usar dimensões, métricas e modelos de política de consentimento para criar relatórios sobre a associação de política de consentimento do visitante no Analysis Workspace.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 2%

---

# Analisar dados de política de consentimento

Você pode assimilar dados de política de consentimento de conjuntos de dados de perfil da Experience Platform em uma conexão do Customer Journey Analytics.

Depois de [criar um relatório de consentimento e uma configuração de filtragem](/help/connections/consent-reporting-filtering/consent-configure.md), os dados da política de consentimento ficam disponíveis como novos componentes nas visualizações de dados na conexão configurada. Você pode usar esses componentes em qualquer lugar no Analysis Workspace se tiver acesso a uma visualização de dados em que eles existem.

## Componentes da política de consentimento

Os relatórios de consentimento adicionam os seguintes componentes às visualizações de dados. Esses componentes são lidos no campo `consentPoliciesIDMap` em seu conjunto de dados de Perfil, e os nomes e descrições da política são provenientes do conjunto de dados de pesquisa de política de consentimento.

### Dimensões

| Dimensão | Descrição |
|---------|----------|
| **[!UICONTROL ID da Política de Consentimento]** | O identificador de uma política de consentimento que um visitante corresponde. |
| **[!UICONTROL Nome da Política]** | O nome amigável da política de consentimento, do conjunto de dados de pesquisa de política de consentimento. |
| **[!UICONTROL Descrição da política]** | A descrição da política de consentimento do conjunto de dados de pesquisa de política de consentimento. |

### Métricas

| Métrica | Descrição |
|---------|----------|
| **[!UICONTROL Visitantes com consentimento]** | O número de visitantes que correspondem a uma política de consentimento. |
| **[!UICONTROL Eventos com Consentimento]** | O número de eventos associados a visitantes que correspondem a uma política de consentimento. |
| **[!UICONTROL Políticas de consentimento exclusivas]** | O número de políticas de consentimento distintas representadas na janela de relatórios. |

### Campo derivado

Um campo derivado faz referência ao campo `consentPoliciesIDMap` para extrair IDs de política de consentimento. Você pode usar esse campo derivado como a base para dimensões adicionais baseadas em consentimento. Para obter mais informações sobre campos derivados, consulte [Campos derivados](/help/data-views/derived-fields/derived-fields.md).

## Usar componentes de política de consentimento no Analysis Workspace

Para relatar a associação à política de consentimento:

1. No Analysis Workspace, abra um projeto que use uma visualização de dados configurada para relatórios de consentimento.

1. No painel Componentes, arraste uma dimensão de política de consentimento, como **[!UICONTROL Nome da política]**, para uma tabela de forma livre.

1. Adicionar uma métrica de consentimento, como **[!UICONTROL Visitantes com consentimento]**, à tabela.

1. Detalhe os resultados por qualquer outra dimensão, como Página ou Canal, para entender como os visitantes que consentiram se comportam.

## Usar o modelo de análise de política de consentimento

Quando uma visualização de dados é configurada para relatórios de consentimento, o Customer Journey Analytics disponibiliza automaticamente um modelo de análise de política de consentimento no Analysis Workspace. Esse modelo fornece um ponto de partida para relatórios sobre a associação à política de consentimento do visitante.

Para obter informações sobre como acessar modelos, consulte [Acessar e executar um modelo](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template).
