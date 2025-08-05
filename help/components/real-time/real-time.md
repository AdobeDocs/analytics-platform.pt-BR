---
description: Entenda os recursos de relatórios em tempo real no Customer Journey Analytics.
title: Visão geral do relatório em tempo real
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: 34dfbc98acecf1ca953434a7d1f0547ff45139a8
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 1%

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

* Casos de uso relevantes, mas menos valiosos, para relatórios em tempo real são os casos de uso de validação.
Você deseja validar, por exemplo:

   * A jornada de campanha que você iniciou recentemente está realmente funcionando?
   * Quando a nova página do produto entrou em funcionamento, você está coletando dados do cliente da página?
   * Seu evento de mídia ao vivo está indo bem?

Não considere a geração de relatórios em tempo real para casos de uso de monitoramento de operações. Por exemplo, para responder à pergunta: um site está realmente funcionando?


## Definição

O aspecto em tempo real dos relatórios em tempo real para o Customer Journey Analytics é definido como dados e visualizações atualizados em aproximadamente 5 minutos a partir do momento em que os dados subjacentes são assimilados por meio da conexão associada.

## Limitações

Você deve estar ciente da seguinte limitação para relatórios em tempo real:

* O relatório em tempo real só relata os dados disponíveis em um período contínuo de 24 horas. Os dados que cruzam esse período contínuo de 24 horas não estão disponíveis.
* A atribuição, a segmentação, as métricas calculadas e muito mais trabalharão apenas nos dados disponíveis no período acumulado de 24 horas.
* O relatório em tempo real funciona melhor em dados de evento e nível de sessão, e você deve ter cuidado ao usar o relatório em tempo real para dados de nível de pessoa. <!--Need to explain this a bit better --> Como apenas eventos do período contínuo de 24 horas estão disponíveis para relatórios em tempo real, o histórico de eventos de uma pessoa também está limitado a essa janela. Considere a preferência por dados de evento e nível de sessão ao selecionar métricas de dimensão (calculadas). E quando você usa funcionalidades como detalhamentos, anteriores ou seguintes e muito mais no painel habilitado para atualização em tempo real.
* Não é possível combinar a compilação com os relatórios em tempo real. <!-- Do we need to explain this in more detail, why? --> Os relatórios em tempo real abordam dados de eventos e de sessões e são menos relevantes para dados com base em pessoas.
* Nenhuma métrica de mídia coletada de heartbeat está disponível, com exceção das métricas de início de mídia e fechamento de mídia. Dessa forma, você ainda pode usar os relatórios em tempo real para ativar um caso de uso de mídia.
* Ao usar as [opções de download ou exportação](/help/analysis-workspace/export/download-send.md) para baixar um projeto ou exportar dados de uma tabela de forma livre, considere o seguinte:
   * Um projeto CSV baixado ou arquivo CSV exportado contém os dados em tempo real disponíveis no momento do download ou da exportação.
   * Um projeto do PDF baixado contém dados que não são em tempo real, semelhantes aos dados que são mostrados quando a atualização em tempo real está desativada.
