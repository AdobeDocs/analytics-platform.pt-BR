---
title: Casos de uso de relatório e filtragem de consentimento
description: Explore casos de uso para relatórios sobre a associação à política de consentimento do visitante e filtragem de visitantes que não consentiram no momento da assimilação no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 585
ht-degree: 0%

---

# Casos de uso de relatórios e filtragem de consentimento

O relatório e a filtragem de consentimento ajudam a relatar sobre a associação à política de consentimento do visitante e, opcionalmente, excluem visitantes que não consentiram antes que seus dados entrem no Customer Journey Analytics. Para obter informações gerais, consulte [Visão geral do relatório e da filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-overview.md).

Este artigo descreve casos de uso de exemplo. Antes de analisá-las, familiarize-se com as considerações abaixo, pois elas afetam os resultados exibidos em seus relatórios.

## Considerações sobre relatórios

* **A filtragem se aplica no nível de conexão**: quando você habilita a filtragem, todas as exibições de dados na conexão configurada herdam o mesmo comportamento. Não é possível filtrar uma visualização de dados em uma conexão de forma diferente de outra.

* **A filtragem usa lógica de inclusão**: os dados de um visitante são assimilados somente se o visitante corresponder a todas as políticas de consentimento que se aplicam às ações de marketing habilitadas. Um visitante que não tenha uma política aplicável é excluído.

* **Dados excluídos não são recuperáveis**: como a filtragem ocorre no momento da assimilação, os dados excluídos não são armazenados no Customer Journey Analytics. Alterar a configuração posteriormente não recupera os dados excluídos de datas anteriores.

* **A associação à política de consentimento vem do conjunto de dados de Perfil**: os relatórios refletem a associação à política de consentimento presente no campo `consentPoliciesIDMap` do conjunto de dados de Perfil. Um visitante deve ter um evento correspondente na conexão para aparecer no relatório.

## Exemplo de casos de uso

### Caso de uso 1: Relatório de consentimento sem filtrar dados

Entenda quantos visitantes correspondem a cada política de consentimento antes de decidir se deseja filtrar, para responder a perguntas como:

* _&quot;Quantos de nossos visitantes consentiram com o uso de análises?&quot;_
* _&quot;Quais políticas de consentimento têm a maior e menor cobertura entre nossos visitantes?&quot;_

**Fluxo de configuração:**

1. Crie uma configuração e selecione a sandbox, o Conjunto de dados de perfil e a conexão que contêm seus dados de associação de política de consentimento.

1. Deixe as opções de filtragem do **[!UICONTROL Analytics]** e do **[!UICONTROL Data science]** desativadas.

1. No Analysis Workspace, crie uma tabela de forma livre com a dimensão **[!UICONTROL Nome da política]** e a métrica **[!UICONTROL Visitantes com consentimento]** para ver a cobertura por política.

Use esses insights para decidir se ativa a filtragem e para quais ações de marketing.

### Caso de uso 2: excluir visitantes que não consentiram com os relatórios do Analytics

Certifique-se de que os relatórios padrão incluam somente visitantes que consentiram no uso de análises para responder perguntas como:

* _&quot;Como nosso público-alvo se comporta quando relatamos apenas o consentimento dos visitantes?&quot;_
* _&quot;Podemos ter certeza de que dados de visitantes sem consentimento nunca entram em nossos relatórios de análise?&quot;_

**Fluxo de configuração:**

1. Crie ou edite uma configuração para a conexão que alimenta os relatórios de análise.

1. Habilitar a opção de filtragem **[!UICONTROL Analytics]**.

1. Confirme a configuração. A partir desse ponto, o Customer Journey Analytics assimilará os dados de um visitante somente se ele corresponder a todas as políticas de consentimento que se aplicam à ação de marketing do Analytics.

Como a filtragem ocorre no momento da assimilação, os relatórios downstream, as exportações e as APIs refletem automaticamente apenas o consentimento dos visitantes, sem a necessidade de alterações no tempo do relatório.

### Caso de uso 3: Filtrar casos de uso de análise e ciência de dados de forma independente

Aplique diferentes requisitos de consentimento a relatórios padrão e casos de uso de ciência de dados para responder a perguntas como:

* _&quot;É possível incluir um conjunto mais amplo de visitantes na análise, aplicando um consentimento mais estrito para o aprendizado de máquina?&quot;_

**Fluxo de configuração:**

1. Crie ou edite uma configuração para a conexão relevante.

1. Habilite a opção **[!UICONTROL Analytics]**, a opção **[!UICONTROL Data science]** ou ambas, dependendo dos requisitos de consentimento para cada caso de uso.

1. Confirme a configuração. O Customer Journey Analytics avalia as políticas de consentimento que se aplicam a cada ação de marketing ativada de maneira independente.

Use essa abordagem quando sua organização aplicar diferentes requisitos de consentimento a diferentes categorias de uso de dados.
