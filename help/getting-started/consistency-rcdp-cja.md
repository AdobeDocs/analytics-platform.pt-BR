---
description: Explica quais fatores influenciam a consistência das métricas e as contagens de associação de público-alvo entre o Real-time Customer Data Platform (CDP em tempo real) e o CJA.
title: Consistência de métricas e contagens de associação de público-alvo entre a CDP em tempo real e a CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 21d51ababeda7fe188fbd42b57ef3baf76d21774
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---


# Consistência de métricas e contagens de associação de público-alvo entre a CDP em tempo real e a CJA

Em cenários do mundo real, a consistência de métricas e contagens de associação de público-alvo no Real-time Customer Data Platform (CDP em tempo real) e no Customer Journey Analytics (CJA) não pode ser garantida. Este documento explica o porquê.

## O CJA ainda não usa o Gráfico de identidade

A CDP e o CJA não compartilham hoje a mesma definição de pessoa. O CJA ainda não usa [Gráfico de identidade](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=pt-BR) Informar a definição de pessoa. A CDP em tempo real depende totalmente das informações no Gráfico de identidade para criar um perfil mesclado.

O CJA usa um método chamado [Compilação em campo](/help/connections/cca/overview.md) que extrai identificadores de conjuntos de dados no lago de dados e aplica a lógica personalizada para vinculá-los. No futuro intermediário, espera-se que o CJA comece a utilizar [Serviço de identidade da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) Exportações para o lago de dados, permitindo uma noção compartilhada de identidade entre a CDP em tempo real e o CJA.

>[!IMPORTANT]
>
>Tornar o serviço de identidade da Adobe Experience Platform a fonte de identidade da verdade para todos os aplicativos Adobe Experience Platform não torna as métricas consistentes automaticamente entre os aplicativos. Leia para saber por quê.

## Flexibilidade dos dados do aplicativo

O Experience Platform não aplica imposição estrita para manter os dados entre o Perfil do cliente em tempo real e o Data Lake iguais. Alguns casos de uso resultam em dados em [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (ativação), enquanto outras trabalham com a função [lago de dados](https://business.adobe.com/blog/basics/data-lake) (serviço de relatórios e consultas).

Os clientes da CDP em tempo real geralmente não têm 100% dos dados no lago de dados da Adobe Experience Platform entrando no Perfil. Isso ocorre por design - os clientes devem ativar especificamente os dados no lago para Perfil. O CJA permite que analistas de dados selecionem livremente quais dados desejam trazer para análise a partir do lago de dados, independentemente do que está ativado para a CDP em tempo real.

## Modificadores específicos do aplicativo

O CJA permite modificações de dados abrangentes no momento da consulta, como a combinação de campos, divisão de campos e outras manipulações, como conversões de moeda, eliminação de duplicação de valor, sessão e filtragem em nível de linha. Esses recursos não estão disponíveis para a CDP.

Da mesma forma, a CDP em tempo real se aplica [políticas de mesclagem](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) para determinar quais dados serão priorizados e quais dados serão combinados para criar uma exibição unificada de uma pessoa. Essas configurações se encaixam firmemente na lógica de cada aplicativo e não são compartilhadas.

## Comportamento de tempo de leitura vs tempo de gravação

A CDP em tempo real requer a compilação point-in-time de perfis usando o gráfico de ID mais recente.

* A CDP em tempo real foi projetada para reunir informações de perfil em tempo real para ativação.

* Ele pode acomodar em tempo real todas as alterações nos identificadores definidos para um determinado usuário.

* A janela de lookback é controlada pela definição do segmento.

O CJA requer que os dados sejam compilados no tempo de gravação usando exportações do Gráfico de ID.

* O CJA aplica etapas complexas de pré-processamento, como indexação, compartilhamento e agrupamento, antes que os dados sejam feitos prontos para análise.

* O identificador de pessoa para um determinado usuário é um elemento essencial para as fases de pré-processamento; alterar o identificador de pessoa depois tem um custo significativo de reprocessamento.

* A janela de retrospectiva é controlada no nível do aplicativo.

## Diferenças no TTL (Tempo de vida útil) e na assimilação de dados

Mesmo que os conjuntos de dados na CDP em tempo real e no CJA sejam os mesmos, a CDP em tempo real pode manter apenas uma janela de histórico muito limitada. Por outro lado, o CJA provavelmente tem dados que valem anos. Além disso:

* Clientes CJA e CDP em tempo real podem definir janelas de retenção personalizadas para dados, independentemente uns dos outros.

* A CDP e o CJA em tempo real têm uma lógica diferente para assimilar dados. O CJA ignora registros sem uma ID de pessoa ou carimbo de data e hora e tem limites estritos para o número de registros que um único perfil/pessoa pode ter.

* Os clientes da CDP em tempo real obtêm 7 dias de acesso aos dados no lago, principalmente para facilitar a integração de dados no perfil e para consultas ad-hoc.

* Não há TTLs para os dados no lago para clientes do CJA. No entanto, os usuários do CJA podem definir uma janela de retenção personalizada no CJA ao criar uma conexão.

* A Loja de perfis na CDP em tempo real permite TTLs configuráveis pelo cliente. Os clientes podem alterar esse TTL para o que precisarem para permanecer dentro dos direitos de licença.

## Diferenças no processamento do GDPR (Regulamento Geral sobre a Proteção de Dados)

A lógica de processamento de dados para o GDPR e a higiene de dados na CDP em tempo real e no lago de dados é bem diferente. Estamos a trabalhar para uma abordagem única.

## Diferenças na latência de assimilação de dados

Os relatórios do CJA incluem alguma latência antes de os dados estarem disponíveis para criação de relatórios ou público-alvo. A CDP em tempo real processa dados por meio de diferentes sistemas com latência diferente.
