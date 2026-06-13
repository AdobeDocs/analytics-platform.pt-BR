---
title: Transição do Google Analytics 4 para o Customer Journey Analytics
description: Saiba mais sobre os principais conceitos para obter relatórios no Customer Journey Analytics, direcionados para analistas familiarizados com o Google Analytics 4.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Transição do Google Analytics 4 para o Customer Journey Analytics

Este guia ajuda os analistas familiarizados com o Google Analytics 4 a aprender os conceitos e relatórios equivalentes no Adobe Customer Journey Analytics. Se você for responsável pela implementação técnica em vez dos relatórios, consulte [Atualizar de uma solução de análise de terceiros para o Customer Journey Analytics](../cja-upgrade/cja-upgrade-third-party-solution.md) para obter orientação sobre a configuração e a assimilação de dados do Web SDK. Se sua organização ainda precisar migrar dados existentes do Google Analytics para o Adobe Experience Platform, consulte [Migrar dados do Google Analytics](/help/use-cases/third-party/ga/overview.md).

## Principais diferenças entre o GA4 e o Customer Journey Analytics

O GA4 e o Customer Journey Analytics compartilham a mesma filosofia básica: cada interação do usuário é um evento e a análise é executada em uma ferramenta de tela em branco, onde você arrasta e solta dimensões e métricas para criar visualizações personalizadas. Se você estiver familiarizado com o GA4 Explore, o Analysis Workspace provavelmente será reconhecido imediatamente.

As diferenças mais significativas são quando o Customer Journey Analytics vai além do GA4:

* **Dados entre canais**: o Customer Journey Analytics pode combinar o Web Analytics com fontes de dados offline (como registros da central de atendimento, atividade de CRM, programas de fidelidade ou envolvimento de email) na mesma análise. O GA4 é limitado às interações digitais coletadas por meio de seu SDK.
* **Processamento de tempo do relatório**: a Customer Journey Analytics aplica lógica, como modelos de atribuição, definições de sessão e regras de segmento, no momento da consulta, não no momento da coleta. As alterações feitas nas definições de sessão ou nos modelos de atribuição se aplicam retroativamente a todos os dados históricos sem reprocessamento.
* **Definições de sessão flexíveis**: duração do tempo limite da sessão, eventos de início da sessão e eventos de término de sessão são configuráveis por visualização de dados no Customer Journey Analytics. O tempo limite de sessão do GA4 é ajustável (padrão de 30 minutos, até 7 horas e 55 minutos), mas se aplica a toda a propriedade e seu comportamento de início e término de sessão é fixo.
* **Compilação de identidade**: o recurso de compilação do Customer Journey Analytics pode vincular interações entre canais e dispositivos à mesma pessoa, produzindo contagens de pessoas mais precisas do que o modelo de identidade mista do GA4.

## Estrutura de dados e conta

O GA4 e o Customer Journey Analytics organizam os dados de forma diferente no nível da plataforma.

| GA4 | Customer Journey Analytics |
|---|---|
| Conta do Google | Organização IMS da Adobe |
| Propriedade | Conexão + visualização de dados |
| Fluxo de dados | [!UICONTROL Conjunto de dados de evento] na Plataforma |
| Filtros de dados | Filtros do componente de visualização de dados |
| Subpropriedade | Visualização de dados separada com filtros aplicados |
| Propriedade de acúmulo | Conexão combinando vários conjuntos de dados |

A diferença estrutural mais importante é que uma Propriedade GA4 trata a fiação de dados e os relatórios como um único objeto. O Customer Journey Analytics separa esses conceitos em duas camadas distintas:

* Uma **conexão** vincula um ou mais conjuntos de dados do Adobe Experience Platform à Customer Journey Analytics. Essa etapa assimila dados na Customer Journey Analytics em um formato otimizado para relatórios.
* Uma **visualização de dados** é criada sobre uma conexão e define quais dimensões, métricas e configurações estão disponíveis para relatórios. É a camada de configuração de relatórios.

Ambos devem existir antes que você possa analisar dados no Customer Journey Analytics. Não há conjuntos de relatórios no Customer Journey Analytics.

## Introdução ao Analysis Workspace

GA4 Explore e Analysis Workspace são ferramentas de análise de arrastar e soltar com tela em branco. O modelo de interação é o mesmo; a terminologia é ligeiramente diferente.

| GA4 Explorar | Analysis Workspace |
|---|---|
| Tela de exploração | Painel |
| Tipo de gráfico ou visualização | Visualização |
| Dimensão | Dimensão |
| Métrica | Métrica |
| Segmento ou filtro | Segmento |
| Contagem de eventos | [!UICONTROL Eventos] |
| Usuários | [!UICONTROL Pessoas] |
| Sessões | [!UICONTROL Sessões] |

>[!TIP]
>
>Os contêineres de segmento do GA4 são nomeados como Usuários, Sessões e Eventos. No Customer Journey Analytics, os contêineres equivalentes são **[!UICONTROL Pessoa]**, **[!UICONTROL Sessão]** e **[!UICONTROL Evento]**. A lógica de escopo é a mesma.

>[!MORELIKETHIS]
>
>* [Migrar dados do Google Analytics](/help/use-cases/third-party/ga/overview.md)
