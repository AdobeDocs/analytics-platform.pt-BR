---
description: Entenda os recursos de relatórios em tempo real no Customer Journey Analytics.
title: Visão geral do relatório em tempo real
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---


# Visão geral do relatório em tempo real

O relatório em tempo real no Customer Journey Analytics exibe e atualiza dados e visualizações em um ou mais painéis no Analysis Workspace em tempo real.

{{release-limited-testing}}

{{ultimate-package}}

## Casos de uso

Esta seção fornece uma visão geral dos casos de uso típicos valiosos e menos valiosos. E também informações quando não se deve considerar relatórios em tempo real.

* Os casos de uso mais valiosos para relatórios em tempo real estão relacionados às principais vendas, promoções ou lançamentos de produtos.
Como parte desse lançamento, você deseja saber:

   * Como as vendas se comparam com sua última venda?
   * Como esse lançamento de produto se compara ao último lançamento de produto?
   * Suas promoções para esse dia ou evento importante realmente funcionam?

* Os casos de uso relevantes, mas menos valiosos para relatórios reais, são os casos de uso de validação.
Você deseja validar, por exemplo:

   * A jornada da campanha que você lançou recentemente está realmente funcionando?
   * A nova página do produto foi ativada e você está coletando dados do cliente da página?
   * Seu evento de mídia ao vivo está indo bem?

Não considere a geração de relatórios em tempo real para casos de uso de monitoramento de operações. Por exemplo, para responder à pergunta se o site está realmente funcionando?


## Definição

O aspecto em tempo real dos relatórios em tempo real para o Customer Journey Analytics é definido como dados e visualizações atualizados em aproximadamente 5 minutos a partir do momento em que os dados subjacentes são assimilados por meio da conexão associada.

## Limitações

Você deve estar ciente da seguinte limitação para relatórios em tempo real:

* O relatório em tempo real só relata os dados disponíveis em um período contínuo de 24 horas. Os dados que cruzam esse período contínuo de 24 horas não estão disponíveis.
* A atribuição, a segmentação, as métricas calculadas e muito mais funcionarão apenas nos dados disponíveis no período contínuo de 24 horas.
* O relatório em tempo real funciona melhor em dados de evento e nível de sessão, e você deve ter cuidado para usar o relatório em tempo real para dados de nível de pessoa. <!--Need to explain this a bit better --> Considere a preferência por dados de evento e nível de sessão ao selecionar métricas de dimensão (calculadas). E quando você usa funcionalidades como detalhamentos, próximas ou anteriores e muito mais no painel habilitado para atualização em tempo real.
* Não é possível combinar a compilação com os relatórios em tempo real. <!-- Do we need to explain this in more detail, why? --> Como mencionado acima, os relatórios em tempo real abordam dados de nível de evento e sessão, e não tanto dados baseados em pessoas.
* Nenhuma métrica de mídia coletada de heartbeat está disponível, com exceção das métricas de início de mídia e fechamento de mídia. Dessa forma, você ainda pode usar os relatórios em tempo real para ativar um caso de uso de mídia.
