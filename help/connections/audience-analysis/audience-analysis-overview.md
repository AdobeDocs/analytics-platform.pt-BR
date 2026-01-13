---
title: Visão geral da análise de público-alvo
description: Saiba mais sobre como analisar públicos-alvo do RTCDP no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 9d9c4dbba13f61af4a47bbb0f87533fb950976bc
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 3%

---

# Visão geral da análise de público-alvo

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>Entenda a diferença entre a análise de público-alvo e a publicação de público-alvo:
>
>* **Análise de público-alvo**: permite assimilar dados de associação de público-alvo de conjuntos de dados do Perfil do Experience Platform em uma conexão do Customer Journey Analytics.
>* **Publicação de público-alvo**: permite criar e publicar públicos-alvo descobertos no Customer Journey Analytics na Adobe Experience Platform para direcionamento e personalização de clientes. Para obter informações sobre a publicação de público, consulte [Visão geral da publicação de público-alvo](/help/components/audiences/audiences-overview.md).

A análise de público-alvo permite assimilar dados de associação de público-alvo de conjuntos de dados de perfil da Experience Platform em uma conexão do Customer Journey Analytics. Os públicos-alvo são disponibilizados como novas dimensões para uso no Analysis Workspace.

O diagrama a seguir e a tabela associada mostram uma representação de alto nível de como uma configuração de análise de público-alvo no Customer Journey Analytics disponibiliza os dados de público-alvo do Experience Platform no Analysis Workspace:

![Visão geral da análise de público-alvo](assets/audience-analysis-overview.png)

| Número | Recurso | Função |
|---------|----------|---------|
| 1 | Configuração da análise de público-alvo | A interface de configuração no Customer Journey Analytics usada para configurar a análise de público-alvo. |
| 2 | Sandbox | Deve conter o conjunto de dados de perfil que você deseja adicionar à conexão. |
| 3 | Conjunto de dados Perfil | Deve incluir os dados de público-alvo do Experience Platform que você deseja analisar. Esse conjunto de dados de perfil é adicionado à conexão selecionada. |
| 4 | Política de mesclagem | A política de mesclagem associada aos públicos-alvo da Experience Platform que você deseja analisar. |
| 5 | Dados do perfil | Os dados do perfil associados à política de mesclagem selecionada. Esses dados estão disponíveis em conjuntos de dados da Experience Platform. |
| 6 | Novo conjunto de dados de pesquisa | Fornece nomes amigáveis para as novas dimensões de público-alvo criadas. <p>O conjunto de dados de pesquisa é criado e adicionado automaticamente à conexão, juntamente com o conjunto de dados do perfil selecionado.</p> |
| 7 | Conexão | A conexão à qual você deseja adicionar o conjunto de dados do perfil selecionado. |
| 8 | Novas dimensões de público | Novas dimensões de público-alvo <!--and metrics?--> que representam os públicos-alvo da Experience Platform incluídos no conjunto de dados de perfil selecionado e estão disponíveis para relatórios no Analysis Workspace. Essas dimensões são criadas automaticamente. |
| 9 | Visualizações de dados | As visualizações de dados selecionadas associadas à sua conexão. Essas são as visualizações de dados que você deseja usar ao analisar dados de público-alvo do Experience Platform no Analysis Workspace. Essas visualizações de dados são configuradas automaticamente com os dados de público-alvo do Experience Platform para relatórios. |

## Configurar análise de público

Ao configurar a análise de público-alvo, você seleciona a sandbox e a política de mesclagem associadas aos públicos-alvo da Experience Platform que deseja analisar. O Customer Journey Analytics cria um novo conjunto de dados de pesquisa e, em seguida, adiciona automaticamente o conjunto de dados de pesquisa e o conjunto de dados do perfil à conexão escolhida.

>[!NOTE]
>
>Os públicos-alvo estão disponíveis nas visualizações de dados do Customer Journey Analytics no dia seguinte à criação da configuração de análise de público-alvo.

Para obter mais informações, consulte [Configurar análise de audiência](/help/connections/audience-analysis/audience-analysis-configure.md).

## Gerenciar configurações de análise de público

Você pode gerenciar as configurações de análise de público-alvo após sua criação. É possível exibir, editar e excluir configurações.

Para obter informações sobre como gerenciar as configurações de análise de público-alvo existentes, consulte [Gerenciar configurações de análise de público-alvo](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analisar dados de público-alvo no Customer Journey Analytics

Com os dados do público-alvo disponíveis no Customer Journey Analytics, você pode obter insights acionáveis sobre como os membros do público-alvo se comportam em vários canais.

Por exemplo, você pode rastrear o comportamento de clientes individuais que foram incluídos na mesma promoção de email. Com o público-alvo disponível no Customer Journey Analytics, você pode ver os seguintes tipos de informações sobre cada membro do público-alvo:

* Click-throughs do email para o site que eventualmente resultaram em uma compra

* Membros do público-alvo que eventualmente fizeram uma compra na loja

Para obter mais informações, consulte [Analisar públicos-alvo da Experience Platform na Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Requisitos de permissão e função da análise de público-alvo

As seguintes funções e permissões do Customer Journey Analytics Experience Platform são necessárias para a análise de público-alvo:

| Recurso | Requisitos de permissão ou função do Customer Journey Analytics | Exigências de permissão do Experience Platform |
|---------|----------|----------|
| [Criar configurações de análise de público-alvo](/help/connections/audience-analysis/audience-analysis-configure.md) | Administrador do sistema | <ul><li>Conjuntos de dados: permissões de leitura</li><li>Esquemas: Read, Write</li><li>Namespaces de identidade: Lidos</li></ul> |
| [Exibir dimensões de análise de público-alvo na exibição de dados](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Administrador de perfil de produto do perfil de produto ao qual a visualização de dados está atribuída <p>Para obter mais informações, consulte [Controle de acesso](/help/technotes/access-control.md).</p> | N/A |
| Usar dimensões de análise de público-alvo no Analysis Workspace | Acesso a uma visualização de dados em que as dimensões de análise de público-alvo foram adicionadas | N/A |

## Limites de análise de público-alvo

Considere os seguintes limites ao [configurar a análise de público-alvo](/help/connections/audience-analysis/audience-analysis-configure.md):

* Uma única sandbox pode oferecer suporte a até 100 configurações de análise de público-alvo.

* Uma conexão só pode ser associada a uma configuração de análise de público-alvo.








