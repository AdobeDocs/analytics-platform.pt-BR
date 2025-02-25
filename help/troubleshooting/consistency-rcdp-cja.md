---
description: Explica quais fatores influenciam a consistência das métricas e as contagens de associação de público-alvo na Real-time Customer Data Platform (Real-time CDP) e no Customer Journey Analytics.
title: Consistência das métricas e associação do público-alvo
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 7c906e30d54362713f5013c8661ee523938d4b0f
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%

---


# Consistência das métricas e associação do público-alvo

Em cenários reais, a consistência de métricas e as contagens de associação de público-alvo na Real-time Customer Data Platform (Real-time CDP) e no Customer Journey Analytics (CJA) não podem ser garantidas. Este documento explica o porquê.

Ao comparar as contagens de associação de público-alvo na Real-time CDP e no Customer Journey Analytics, é importante ter em mente as diferentes finalidades dessas duas ferramentas. A Real-time CDP usa dados de perfis de clientes para direcionar experiências digitais a consumidores individuais, enquanto o Customer Journey Analytics ajuda os usuários a entender padrões em métricas e segmentos comerciais importantes. Embora a publicação de públicos-alvo do Customer Journey Analytics na Real-time CDP permita que um usuário dessas ferramentas “ative” um insight nativamente e de maneira fácil, aproveitando os aprendizados obtidos no Customer Journey Analytics, as finalidades dessas ferramentas são fundamentalmente diferentes.

## Diferenças nas configurações de identidade

Atualmente, a Real-time CDP e o Customer Journey Analytics não compartilham a mesma definição de pessoa. A Real-time CDP depende totalmente das informações contidas no [Gráfico de identidade](https://experienceleague.adobe.com/pt-br/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs) para criar um perfil mesclado.

O Customer Journey Analytics pode ser configurado para usar [Costura](../stitching/overview.md). Se você usar a [Compilação em campo](/help/stitching/fbs.md) como o mecanismo de compilação, especifique um identificador de um conjunto de dados no data lake para compilar os dados nesse conjunto de dados com a finalidade de elevar o conjunto de dados com perfis mesclados aprimorados. Se você usar a [Compilação com base em gráfico](/help/stitching/gbs.md) como o mecanismo de compilação, um processo semelhante estará usando o gráfico de identidade, com base em um namespace de identidade especificado.


## Diferenças na configuração do conjunto de dados

Você pode optar por inserir alguns dados na Real-time CDP e outros no Customer Journey Analytics. Geralmente, os clientes optam por inserir mais dados históricos no Customer Journey Analytics, que não são relevantes para a Real-time CDP. Outros conjuntos de dados podem ser mais relevantes para a Real-time CDP do que para o Customer Journey Analytics.

## Diferenças na configuração de processamento

O Customer Journey Analytics permite uma modificação extensa dos dados no momento da consulta, como a combinação e divisão de campos e outras manipulações, como inclusões/exclusões, substrings, desduplicação de valor, criação de sessões e filtragem em nível de linha.

A Real-time CDP oferece um conjunto diferente de ferramentas de manipulação de dados. Ela aplica [políticas de mesclagem](https://experienceleague.adobe.com/pt-br/docs/experience-platform/profile/merge-policies/overview) para determinar quais dados serão priorizados e quais dados serão combinados para criar uma visualização unificada de uma pessoa.

## Diferenças no TTL (Tempo de vida útil) e na assimilação de dados

Mesmo que os conjuntos de dados da Real-time CDP e do Customer Journey Analytics sejam os mesmos, a Real-time CDP pode manter apenas uma janela de histórico muito limitada. Por outro lado, o Customer Journey Analytics provavelmente tem dados de vários anos. Além disso:

* Os clientes do Customer Journey Analytics e da Real-time CDP podem definir janelas de retenção personalizadas para dados independentes umas das outras.

* A Real-time CDP e o Customer Journey Analytics utilizam lógicas diferentes para assimilar dados. O Customer Journey Analytics ignora registros sem uma ID de pessoa ou carimbo de data e hora e tem limites rigorosos para o número de registros que um único perfil/pessoa pode ter.

* Os clientes da Real-time CDP recebem 7 dias de acesso aos dados do data lake, principalmente para facilitar a integração de dados no perfil e para consultas ad-hoc.

* Não há TTLs para os dados no data lake para clientes do Customer Journey Analytics. No entanto, os usuários do Customer Journey Analytics podem definir uma janela de retenção personalizada no Customer Journey Analytics ao criar uma conexão.

* A loja de perfis na Real-time CDP permite TTLs configuráveis pelo cliente. Os clientes podem alterar esse TTL para o valor que precisarem para manter seus direitos de licença.

## Diferenças na latência de assimilação de dados

O Customer Journey Analytics ainda não tem os recursos em tempo real da Real-time CDP e, como resultado, pode apresentar um pouco de latência antes de disponibilizar os dados para criação de relatórios ou de público-alvo. A Real-time CDP processa dados por meio de diferentes sistemas com diferentes níveis de latência.
