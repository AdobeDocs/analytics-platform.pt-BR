---
description: Explica quais fatores influenciam a consistência das métricas e as contagens de associação de público na Real-time Customer Data Platform (Real-time CDP) e no CJA.
title: Consistência de métricas e contagens de associação de público na Real-time CDP e no CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---


# Consistência de métricas e contagens de associação de público na Real-time CDP e no CJA

Em cenários reais, a consistência de métricas e as contagens de associação de público na Real-time Customer Data Platform (Real-time CDP) e no Customer Journey Analytics (CJA) não podem ser garantidas. Este documento explica o porquê.

Ao comparar as contagens de associação de público entre a Real-time CDP e o CJA, é importante ter em mente as diferentes finalidades dessas duas ferramentas. A Real-time CDP usa dados de perfil do cliente para direcionar experiências digitais a consumidores individuais, enquanto que o CJA é projetado para ajudar os usuários a entender padrões em métricas e segmentos comerciais importantes. Embora a publicação de públicos do CJA na Real-time CDP permita que um usuário dessas ferramentas “ative” um insight nativamente e de maneira fácil, aproveitando os aprendizados obtidos no CJA, as finalidades dessas ferramentas são fundamentalmente diferentes.

## Diferenças nas configurações de identidade

Atualmente, a Real-time CDP e o CJA não compartilham a mesma definição de pessoa. A Real-time CDP depende totalmente das informações contidas no [Gráfico de identidade](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=pt-BR) para criar um perfil mesclado.

O CJA pode ser configurado para usar a [Cross-Channel Analytics](/help/cca/overview.md), que extrai identificadores de conjuntos de dados no data lake e aplica uma lógica personalizada para vinculá-los.

No futuro, o CJA poderá usar o Gráfico de identidade.

## Diferenças na configuração do conjunto de dados

Você pode optar por inserir alguns dados na Real-time CDP e outros no CJA. Geralmente, os clientes optam por inserir mais dados históricos no CJA, que não são relevantes para a Real-time CDP. Outros conjuntos de dados podem ser mais relevantes para a Real-time CDP do que para o CJA.

## Diferenças na configuração de processamento

O CJA permite uma modificação extensa dos dados no momento da consulta, como a combinação e divisão de campos e outras manipulações, como inclusões/exclusões, subsequências, eliminação de duplicações de valor, criação de sessões e filtragem em nível de linha.

A Real-time CDP oferece um conjunto diferente de ferramentas de manipulação de dados. Ela aplica [políticas de mesclagem](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=pt-BR) para determinar quais dados serão priorizados e quais dados serão combinados para criar uma visualização unificada de uma pessoa.

## Diferenças no TTL (Tempo de vida útil) e na assimilação de dados

Mesmo que os conjuntos de dados da Real-time CDP e do CJA sejam os mesmos, a Real-time CDP pode manter apenas uma janela de histórico muito limitada. Por outro lado, o CJA provavelmente tem dados de vários anos. Além disso:

* Os clientes do CJA e da Real-time CDP podem definir janelas de retenção personalizadas para dados, que sejam independentes umas das outras.

* A Real-time CDP e o CJA utilizam lógicas diferentes para assimilar dados. O CJA ignora registros sem uma ID de pessoa ou carimbo de data e hora e tem limites rigorosos para o número de registros que um único perfil/pessoa pode ter.

* Os clientes da Real-time CDP recebem 7 dias de acesso aos dados do data lake, principalmente para facilitar a integração de dados no perfil e para consultas ad-hoc.

* Não há TTLs para os dados no data lake para clientes do CJA. No entanto, os usuários do CJA podem definir uma janela de retenção personalizada no CJA ao criar uma conexão.

* A loja de perfis na Real-time CDP permite TTLs configuráveis pelo cliente. Os clientes podem alterar esse TTL para o valor que precisarem para manter seus direitos de licença.

## Diferenças na latência de assimilação de dados

O CJA ainda não tem os recursos em tempo real da Real-time CDP e, como resultado, ele pode apresentar um pouco de latência antes de disponibilizar os dados para relatórios ou criação de públicos. A Real-time CDP processa dados por meio de diferentes sistemas com diferentes níveis de latência.
