---
title: Visão geral da análise de público-alvo
description: Saiba mais sobre como analisar públicos-alvo do RTCDP no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 2b91c0592ac4ec0e0b5ffa3db91758466563abaf
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 4%

---

# Visão geral da análise de público-alvo

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>A análise de público-alvo é diferente da publicação de público-alvo, o que permite criar e publicar públicos-alvo descobertos no Customer Journey Analytics no Adobe Experience Platform para direcionamento e personalização de clientes. Para obter informações sobre a publicação de público, consulte [Visão geral da publicação de público-alvo](/help/components/audiences/audiences-overview.md).

A análise de público-alvo permite assimilar dados de associação de público-alvo de conjuntos de dados de perfil da Experience Platform em uma conexão do Customer Journey Analytics. Os públicos-alvo são disponibilizados como novas dimensões para uso no Analysis Workspace.

O diagrama a seguir e a tabela associada mostram uma representação de alto nível de como uma configuração de análise de público-alvo no Customer Journey Analytics disponibiliza os dados de público-alvo do Experience Platform no Analysis Workspace:

![Visão geral da análise de público-alvo](assets/audience-analysis-overview.png)

| Número | Recurso | Função |
|---------|----------|---------|
| 1 | Configuração da análise de público-alvo | Interface de configuração no Customer Journey Analytics usada para configurar a análise de público-alvo. |
| 2 | Sandbox | Deve conter o conjunto de dados de perfil que você deseja adicionar à conexão. |
| 3 | Conjunto de dados Perfil | Deve incluir os dados de público-alvo do Experience Platform que você deseja analisar. Esse conjunto de dados de perfil é adicionado à conexão selecionada. |
| 4 | Política de mesclagem | A política de mesclagem associada aos públicos-alvo da Experience Platform que você deseja analisar. |
| 5 | Dados do perfil | Os dados do perfil associados à política de mesclagem selecionada. Esses dados estão disponíveis em conjuntos de dados da Experience Platform. |
| 6 | Novo conjunto de dados de pesquisa | Fornece nomes amigáveis para as novas dimensões de público-alvo criadas. O conjunto de dados de pesquisa é criado e adicionado automaticamente à conexão, juntamente com o conjunto de dados do perfil selecionado. |
| 7 | Conexão | A conexão à qual você deseja adicionar o conjunto de dados do perfil selecionado. |
| 8 | Novas dimensões de público | Novas dimensões de público-alvo <!--and metrics?--> que representam os públicos-alvo da Experience Platform incluídos no conjunto de dados de perfil selecionado e estão disponíveis para relatórios no Analysis Workspace. Essas dimensões são criadas automaticamente. |
| 9 | Visualizações de dados | As visualizações de dados selecionadas associadas à sua conexão. Essas são as visualizações de dados que você deseja usar ao analisar dados de público-alvo do Experience Platform no Analysis Workspace. Essas visualizações de dados são configuradas automaticamente com os dados de público-alvo do Experience Platform para relatórios. |
| 10 | Analysis Workspace | A área dentro do Customer Journey Analytics em que você cria relatórios que inclui os públicos-alvo da Experience Platform que são assimilados. |

## Configurar análise de público

Ao configurar a análise de público-alvo, você seleciona a sandbox e a política de mesclagem associadas aos públicos-alvo da Experience Platform que deseja analisar. O Customer Journey Analytics cria um novo conjunto de dados de pesquisa e, em seguida, adiciona automaticamente o conjunto de dados de pesquisa e o conjunto de dados do perfil à conexão escolhida.

Para obter mais informações, consulte [Configurar análise de audiência](/help/connections/audience-analysis/audience-analysis-configure.md).

## Analisar dados de público-alvo no Customer Journey Analytics

Com os dados do público-alvo disponíveis no Customer Journey Analytics, você pode obter insights acionáveis sobre como os membros do público-alvo se comportam em vários canais.

Por exemplo, você pode rastrear o comportamento de clientes individuais que foram incluídos na mesma promoção de email. Com o público-alvo disponível no Customer Journey Analytics, você pode ver os seguintes tipos de informações sobre cada membro do público-alvo:

* Click-throughs do email para o site que eventualmente resultaram em uma compra

* Membros do público-alvo que eventualmente fizeram uma compra na loja

Para obter mais informações, consulte [Analisar públicos-alvo da Experience Platform na Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).










