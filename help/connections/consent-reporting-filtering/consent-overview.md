---
title: Visão geral da filtragem e do relatório de consentimento
description: Saiba como criar relatórios sobre a associação à política de consentimento do visitante e filtrar visitantes que não consentiram no momento da assimilação no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8did: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 1058
ht-degree: 2%

---

# Visão geral do relatório e da filtragem de consentimento

O relatório e a filtragem de consentimento usam os dados de associação à política de consentimento armazenados em seus conjuntos de dados de perfil do Adobe Experience Platform para ajudar você a relatar o consentimento do visitante e, opcionalmente, excluir visitantes que não consentiram antes que seus dados sejam assimilados na Customer Journey Analytics.

## Pré-requisitos

Antes de configurar o relatório de consentimento e a filtragem, verifique se:

* Sua organização licenciou o Adobe Healthcare Shield ou o Privacy &amp; Security Shield.
* Você tem permissões de administrador do sistema no Customer Journey Analytics.
* A sandbox que você deseja usar contém um conjunto de dados de Perfil com dados de associação de política de consentimento no campo `consentPoliciesIDMap`.
* A conexão que você deseja configurar já existe. Para obter mais informações, consulte [Criar ou editar uma conexão](/help/connections/create-connection.md).

O diagrama a seguir e a tabela associada mostram uma representação de alto nível de como o relatório e a filtragem de consentimento disponibilizam os dados de política de consentimento no Analysis Workspace e filtram os dados do visitante no momento da assimilação:

![Visão geral do relatório e da filtragem de consentimento](assets/consent-overview.png)

| Número | Recurso | Função |
|---------|----------|---------|
| 1 | Configuração de relatórios e filtragem de consentimento | A interface de configuração no Customer Journey Analytics usada para ativar o relatório de consentimento e, opcionalmente, a filtragem de consentimento. |
| 2 | Sandbox | Deve conter o conjunto de dados Perfil que inclui os dados de associação de política de consentimento que você deseja relatar. |
| 3 | Conjunto de dados Perfil | Inclui os dados de associação da política de consentimento para cada visitante. A associação à política de consentimento é armazenada no campo `consentPoliciesIDMap` de um conjunto de dados de Perfil. Esse conjunto de dados de Perfil é adicionado à conexão selecionada. <p>O perfil de cada visitante lista as políticas de consentimento correspondentes ao visitante. O Customer Journey Analytics lê este campo para disponibilizar políticas de consentimento para relatórios e para avaliar quais visitantes incluir durante a assimilação.</p> |
| 4 | Conjunto de dados de pesquisa de política de consentimento | Fornece nomes e descrições amigáveis de políticas para relatórios. O conjunto de dados de pesquisa é criado automaticamente e mantido em sincronia com o Experience Platform. Existe um máximo de um conjunto de dados de pesquisa de política de consentimento por sandbox. |
| 5 | Conexão | A conexão em que o relatório e a filtragem de consentimento são aplicados. Todas as visualizações de dados na conexão herdam a configuração. |
| 6 | Componentes da política de consentimento | Novas dimensões, métricas e um campo derivado que representam associação à política de consentimento. Esses componentes são criados automaticamente e estão disponíveis para relatórios no Analysis Workspace. |
| 7 | Filtragem de tempo de assimilação | Quando a filtragem está ativada, os visitantes que não consentem são excluídos durante a assimilação com base nas ações de marketing configuradas. |

## Relatório de consentimento vs. filtragem

Os relatórios e a filtragem de consentimento são dois recursos separados. Você pode ativar os relatórios de consentimento por conta própria ou ativar os relatórios e a filtragem juntos.

### Relatório de consentimento

Ao ativar o relatório de consentimento, o Customer Journey Analytics adiciona um conjunto de componentes da política de consentimento às visualizações de dados na conexão configurada. Esses componentes permitem usar o Analysis Workspace para informar sobre quais visitantes correspondem às várias políticas de consentimento, usando os dados de associação da política de consentimento em seus conjuntos de dados de perfil do Experience Platform.

Para manter os relatórios legíveis, o Customer Journey Analytics sincroniza os nomes e as descrições da política do Experience Platform em um conjunto de dados de pesquisa de política de consentimento. Quando uma política é criada, atualizada, renomeada ou excluída no Experience Platform, o conjunto de dados de pesquisa é atualizado automaticamente.

Para obter informações sobre os componentes criados pelos relatórios de consentimento, consulte [Analisar dados de política de consentimento](/help/connections/consent-reporting-filtering/consent-analyze.md).

### Filtragem de consentimento

>[!IMPORTANT]
>
>Os dados de consentimento filtrados (excluídos) não são armazenados no Customer Journey Analytics e não podem ser recuperados por datas anteriores atualizando sua configuração.

Ao ativar a filtragem de consentimento, o Customer Journey Analytics exclui visitantes que não consentiram no momento da assimilação. Como a filtragem acontece no momento da assimilação, os dados de visitantes excluídos nunca entram no Customer Journey Analytics e não estão disponíveis para relatórios.

Considere o seguinte ao usar a filtragem de consentimento:

* O Customer Journey Analytics determina as políticas de consentimento que se aplicam às ações de marketing configuradas.

  Uma ação de marketing representa uma categoria de uso de dados. O Customer Journey Analytics determina quais políticas de consentimento se aplicam a cada ação de marketing e você habilita a filtragem de cada ação de marketing independentemente ao [criar sua configuração](/help/connections/consent-reporting-filtering/consent-configure.md#create-a-configuration).

  | Ação de marketing | Descrição |
  |---------|----------|
  | **[!UICONTROL Analytics]** | Relatórios padrão do Customer Journey Analytics no Analysis Workspace. |
  | **[!UICONTROL Ciência de dados]** | Casos de uso de análise avançada, aprendizado de máquina e ciência de dados. |

* Os dados de um visitante são assimilados somente se o visitante corresponder a **todas** as políticas de consentimento aplicáveis. Se alguma política aplicável não for aplicada ao visitante, os dados dele serão excluídos.

## Configurar relatório e filtragem de consentimento

Ao configurar o relatório e a filtragem de consentimento, você seleciona a sandbox e o conjunto de dados de Perfil que contêm seus dados de associação de política de consentimento, escolhe a conexão ou as conexões a serem configuradas e escolhe se deseja filtrar dados para cada ação de marketing. Em seguida, o Customer Journey Analytics cria automaticamente o conjunto de dados de pesquisa de política de consentimento e os componentes da política de consentimento.

Para obter mais informações, consulte [Configurar relatório e filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-configure.md).

## Gerenciar configurações de filtragem e relatório de consentimento

Você pode gerenciar o relatório de consentimento e as configurações de filtragem após serem criados. É possível exibir, editar e excluir configurações.

Para obter informações sobre como gerenciar configurações existentes, consulte [Gerenciar configurações de filtragem e relatório de consentimento](/help/connections/consent-reporting-filtering/consent-manage.md).

## Analisar dados de política de consentimento

Com os dados da política de consentimento disponíveis no Customer Journey Analytics, você pode informar sobre quais visitantes correspondem a quais políticas de consentimento e usar essa insight para entender os públicos-alvo de consentimento em seus relatórios.

Para obter mais informações, consulte [Analisar dados de política de consentimento](/help/connections/consent-reporting-filtering/consent-analyze.md).

## Requisitos de permissão e função de filtragem e relatórios de consentimento

As seguintes funções do Customer Journey Analytics e permissões do Experience Platform são necessárias para o relatório e a filtragem de consentimento:

| Recurso | Requisitos de permissão ou função do Customer Journey Analytics | Exigências de permissão do Experience Platform |
|---------|----------|----------|
| [Criar configurações de filtragem e relatório de consentimento](/help/connections/consent-reporting-filtering/consent-configure.md) | Administrador do sistema | <ul><li>Conjuntos de dados: leitura, gravação</li><li>Esquemas: Read, Write</li></ul> <p>O acesso de leitura é necessário para o conjunto de dados do Perfil que contém os dados de associação da política de consentimento. O acesso de gravação é necessário porque um conjunto de dados de pesquisa de política de consentimento foi criado e mantido em sincronia.</p> |
| Exibir componentes da política de consentimento na visualização de dados | Administrador de perfil de produto do perfil de produto ao qual a visualização de dados está atribuída <p>Para obter mais informações, consulte [Controle de acesso](/help/technotes/access-control.md).</p> | N/A |
| Usar componentes de política de consentimento no Analysis Workspace | Acesso a uma visualização de dados em que os componentes da política de consentimento foram adicionados | N/D |

## Casos de uso de relatórios e filtragem de consentimento

Por exemplo, casos de uso que destacam o valor fornecido pelo relatório e filtragem de consentimento, consulte [Casos de uso de relatório e filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-use-cases.md).

## Limites de filtragem e relatório de consentimento

Considere os seguintes limites ao [configurar o relatório e a filtragem de consentimento](/help/connections/consent-reporting-filtering/consent-configure.md):

* Uma única sandbox pode ter apenas um conjunto de dados de pesquisa de política de consentimento. Várias configurações no mesmo compartilhamento de sandbox que o conjunto de dados de pesquisa.

* Uma conexão pode ser associada a apenas uma configuração de filtragem e relatório de consentimento.
