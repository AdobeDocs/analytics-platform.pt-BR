---
title: Solicitar compilação
description: Como solicitar a compilação
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 9%

---

# Solicitar compilação

Assim que sua organização atender a todos os [pré-requisitos](overview.md#prerequisites) e entender as limitações comuns de [limitações](overview.md#limitations) e do método de compilação específico ([baseado em campo](fbs.md#limitations) e [baseado em gráfico](gbs.md#limitations)), você poderá seguir essas etapas para solicitar e começar a usar a compilação no Customer Journey Analytics.

## Selecionar opções

O pacote do Customer Journey Analytics ao qual você está habilitado determina os métodos de compilação disponíveis, as opções para a duração do preenchimento retroativo inicial, a janela de pesquisa, a frequência de repetição e o número máximo de conjuntos de dados permitidos para compilação. Consulte a [descrição do produto Customer Journey Analytics](https://helpx.adobe.com/br/legal/product-descriptions/customer-journey-analytics.html) para obter mais detalhes. Decida sobre as opções disponíveis antes de solicitar suporte.

| | Customer Journey Analytics<br/>Selecionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de compilação disponíveis | <li>Compilação em campo</li> | <li>Compilação em campo</li><li>Compilação baseada em gráfico</li> | <li>Compilação em campo</li><li>Compilação baseada em gráfico</li> |
| Duração do preenchimento retroativo de compilação única | 13 meses | 13 meses | 25 meses |
| Janela de pesquisa e frequência de repetição | <li>1 dia, todos os dias</li><li>até 7 dias, semanalmente</li> | <li>1 dia, todos os dias</li><li>até 14 dias, semanalmente</li> | <li>1 dia, todos os dias</li><li>até 30 dias, semanalmente</li> |
| Número máximo de conjuntos de dados permitidos para compilação | 5 | 15 | 50 |

## Solicitar suporte

1. Entre em contato com o Suporte ao cliente da Adobe com as seguintes informações:

   - Uma solicitação para ativar a compilação.
   - A ID do conjunto de dados que você deseja rechavear.
   - O nome da coluna (caminho de identidade e namespace) da ID persistente para o conjunto de dados desejado (o identificador que aparece em cada linha).
   - Se o conjunto de dados suportar `identityMap`:
      - Para a compilação em campo, especifique o namespace para as IDs persistente e de pessoa.
      - Para a compilação baseada em gráfico, especifique o namespace da ID persistente e o namespace de identidade a ser usado para consultar o gráfico de identidade.
   - Se o conjunto de dados não suportar `identityMap`:
      - Para a compilação em campo, o nome da coluna da ID de pessoa para o conjunto de dados desejado (o identificador de pessoa, que também atua como um link entre conjuntos de dados no contexto de uma conexão).
      - Para compilação baseada em gráfico, o namespace de identidade a ser usado para consultar o gráfico de identidade.
   - Sua preferência por janela de retrospectiva e frequência de repetição. Consulte seu pacote do Customer Journey Analytics para obter as [opções](#options) disponíveis.
   - Nome da sandbox.


2. O Suporte ao cliente da Adobe trabalha com a engenharia da Adobe para permitir a compilação ao receber sua solicitação. Depois de habilitado, um conjunto de dados rechaveado que contém uma coluna de ID compilada é exibido no Adobe Experience Platform. O Suporte ao cliente da Adobe pode fornecer a ID do novo conjunto de dados.
3. Quando ativado pela primeira vez, o Adobe fornece um preenchimento retroativo de dados compilados. Consulte seu pacote do Customer Journey Analytics para a [opção](#options) disponível.

4. Se você quiser usar o conjunto de dados compilado em uma análise entre canais, é necessário adicionar o conjunto de dados compilado a uma [conexão](../connections/overview.md) no Customer Journey Analytics. Em seguida, adicione outros conjuntos de dados necessários para a análise entre canais e selecione a ID de pessoa correta para cada conjunto de dados.

5. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados for configurada, você poderá executar sua análise de relatórios do Customer Journey Analytics em canais e dispositivos.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->
