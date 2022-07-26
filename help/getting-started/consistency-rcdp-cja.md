---
description: Explica quais fatores influenciam a consistência das métricas e as contagens de associação de público-alvo entre o Real-time Customer Data Platform (CDP em tempo real) e o CJA.
title: Consistência de métricas e contagens de associação de público-alvo entre a CDP em tempo real e a CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Consistência de métricas e contagens de associação de público-alvo entre a CDP em tempo real e a CJA

Em cenários do mundo real, a consistência de métricas e contagens de associação de público-alvo no Real-time Customer Data Platform (CDP em tempo real) e no Customer Journey Analytics (CJA) não pode ser garantida. Este documento explica o porquê.

Ao comparar as contagens de associação de público-alvo entre a CDP em tempo real e o CJA, é importante ter em mente os diferentes propósitos dessas duas ferramentas. A CDP em tempo real usa dados de perfil do cliente para direcionar experiências digitais a consumidores individuais, enquanto a CJA é projetada para ajudar os usuários a entender padrões em métricas e segmentos-chave de negócios. Embora a publicação de público-alvo do CJA para a CDP em tempo real permita que um usuário dessas ferramentas &quot;ative&quot; um insight de maneira fácil e nativa, aproveitando os aprendizados obtidos no CJA, essas ferramentas, no entanto, servem objetivos fundamentalmente diferentes.

## Diferenças nas configurações de identidade

A CDP e o CJA em tempo real não compartilham a mesma definição de pessoa hoje. A CDP em tempo real depende totalmente das informações na [Gráfico de identidade](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) para criar um perfil mesclado.

O CJA pode ser configurado para usar [Análise entre canais](/help/connections/cca/overview.md) que extrai identificadores de conjuntos de dados no lago de dados e aplica a lógica personalizada para vinculá-los.

No futuro, o CJA poderá usar o Gráfico de identidade.

## Diferenças na configuração do conjunto de dados

Você pode optar por colocar alguns dados na CDP em tempo real e alguns no CJA; Geralmente, os clientes optam por colocar mais dados históricos no CJA do que é relevante para a CDP em tempo real. Outros conjuntos de dados podem ser mais relevantes para a CDP em tempo real do que para o CJA.

## Diferenças na configuração de processamento

O CJA permite uma modificação extensa de dados no momento da consulta, como a combinação de campos, divisão de campos e outras manipulações, como inclui/exclui, subsequências, eliminação de duplicação de valor, sessão e filtragem em nível de linha.

A CDP em tempo real oferece um conjunto diferente de ferramentas de manipulação de dados. Aplica-se [políticas de mesclagem](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) para determinar quais dados serão priorizados e quais dados serão combinados para criar uma exibição unificada de uma pessoa.

## Diferenças no TTL (Tempo de vida útil) e na assimilação de dados

Mesmo que os conjuntos de dados na CDP em tempo real e no CJA sejam os mesmos, a CDP em tempo real pode manter apenas uma janela de histórico muito limitada. Por outro lado, o CJA provavelmente tem dados que valem anos. Além disso:

* Clientes CJA e CDP em tempo real podem definir janelas de retenção personalizadas para dados, independentemente uns dos outros.

* A CDP e o CJA em tempo real têm uma lógica diferente para assimilar dados. O CJA ignora registros sem uma ID de pessoa ou carimbo de data e hora e tem limites estritos para o número de registros que um único perfil/pessoa pode ter.

* Os clientes da CDP em tempo real obtêm 7 dias de acesso aos dados no lago, principalmente para facilitar a integração de dados no perfil e para consultas ad-hoc.

* Não há TTLs para os dados no lago para clientes do CJA. No entanto, os usuários do CJA podem definir uma janela de retenção personalizada no CJA ao criar uma conexão.

* A Loja de perfis na CDP em tempo real permite TTLs configuráveis pelo cliente. Os clientes podem alterar esse TTL para o que precisarem para permanecer dentro dos direitos de licença.

## Diferenças na latência de assimilação de dados

O CJa ainda não tem os recursos em tempo real da CDP em tempo real e, como resultado, o relatório do CJA inclui alguma latência antes que os dados estejam disponíveis para relatórios ou criação de público-alvo. A CDP em tempo real processa dados por meio de diferentes sistemas com latência diferente.
