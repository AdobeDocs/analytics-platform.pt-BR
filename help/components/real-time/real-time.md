---
description: Entenda os recursos de relatórios em tempo real no Customer Journey Analytics.
title: Visão geral do relatório em tempo real
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 3%

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

   * A jornada de campanha lançada recentemente está funcionando?
   * Quando a nova página do produto entrou em funcionamento, você está coletando dados do cliente da página?
   * Seu evento de mídia ao vivo está indo bem?

Não considere a geração de relatórios em tempo real para casos de uso de monitoramento de operações. Por exemplo, para responder à pergunta se um site está funcionando corretamente. Como o [botão de atualização em tempo real](use-real-time.md) é desabilitado automaticamente depois de 30 minutos e o relatório em tempo real para de ser atualizado, você não deve usar um relatório em tempo real como uma fonte confiável para esses casos de uso.


## Definição

O aspecto em tempo real dos relatórios em tempo real para o Customer Journey Analytics é definido como dados e visualizações atualizados em aproximadamente 6,5 minutos a partir do momento em que os dados subjacentes são assimilados pela conexão associada.

Vários componentes na configuração da coleção de dados determinam a latência de relatórios em tempo real.

![Relatório em tempo real](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | Descrição | Latência |
|:---:|---|--:|
| 1 | Dados coletados pelo Edge Network SDK/APIs na Edge Network. | &lt; 500 milissegundos |
| 2 | Dados replicados do Edge Network para o serviço de coleta e validação de dados no Experience Platform Hub. | &lt; 5 minutos |
| 3 | Dados coletados por meio de conectores de transmissão no serviço de coleta e validação de dados no Experience Platform Hub. | &lt; 15 minutos |
| 4 | Dados coletados pelo Adobe Analytics e encaminhados pelo conector de origem do Analytics para o processador de conectores de origem no Experience Platform Hub. | &lt; 15 minutos |
| 5 | Dados coletados por outros conectores de origem no processador de conectores de origem no Experience Platform Hub. | &lt; 24 horas |
| 6 | Dados processados pelo processador em tempo real para um conjunto de dados consolidado para relatórios em tempo real. | &lt; 90 segundos |

## Limitações

Esteja ciente da seguinte limitação para relatórios em tempo real:

* O relatório em tempo real só relata os dados disponíveis em um período contínuo de 24 horas. Os dados que passam por esse período contínuo de 24 horas são ocultados para relatórios em tempo real. Assim que a [atualização em tempo real](use-real-time.md) de um relatório for desabilitada ou desabilitada automaticamente, todos os dados relevantes de um relatório ficarão disponíveis mais uma vez.
* A atribuição, a segmentação, as métricas calculadas e muito mais trabalharão apenas nos dados disponíveis no período acumulado de 24 horas.
* O relatório em tempo real funciona melhor em dados de evento e nível de sessão, e você deve ter cuidado ao usar o relatório em tempo real para dados de nível de pessoa. <!--Need to explain this a bit better --> Como apenas eventos do período contínuo de 24 horas estão disponíveis para relatórios em tempo real, o histórico de eventos de uma pessoa também está limitado a essa janela. Considere a preferência por dados de evento e nível de sessão ao selecionar uma dimensão e métricas (calculadas). E quando você usa funcionalidades como detalhamentos, anteriores ou seguintes e muito mais no painel habilitado para atualização em tempo real.
* Não é possível combinar a compilação com os relatórios em tempo real. <!-- Do we need to explain this in more detail, why? --> Os relatórios em tempo real abordam dados de eventos e de sessões e são menos relevantes para dados com base em pessoas.
* Nenhuma métrica de mídia coletada de heartbeat está disponível, exceto as métricas de início e fechamento de mídia. Dessa forma, você ainda pode usar os relatórios em tempo real para ativar um caso de uso de mídia.
* Ao usar as [opções de download ou exportação](/help/analysis-workspace/export/download-send.md) para baixar um projeto ou exportar dados de uma tabela de forma livre, considere o seguinte:
   * Um projeto CSV baixado ou arquivo CSV exportado contém os dados em tempo real disponíveis no momento do download ou da exportação.
   * Um projeto do PDF baixado contém dados que não são em tempo real, semelhantes aos dados que são mostrados quando a atualização em tempo real está desativada.
