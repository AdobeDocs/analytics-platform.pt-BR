---
title: Configuração de solicitação
description: Saiba como solicitar compilação.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: a94f3fe6821d96c76b759efa3e7eedc212252c5f
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 20%

---

# Solicitar compilação


>[!IMPORTANT]
>
>A solicitação de compilação por meio do Adobe não é mais necessária e esse método está obsoleto. [Habilitar a compilação na interface do usuário de Conexões](use-stitching-ui.md).
>

Assim que sua organização atender aos [pré-requisitos](overview.md#prerequisites) genéricos, entender as [limitações](overview.md#limitations) comuns e também os pré-requisitos e limitações específicos do método de compilação ([baseado em campo](fbs.md) e [baseado em gráfico](gbs.md)), você poderá seguir essas etapas para solicitar e começar a usar a compilação no Customer Journey Analytics.

## Selecionar opções

O pacote do Customer Journey Analytics ao qual você está habilitado determina os métodos de compilação disponíveis, as opções para a duração do preenchimento retroativo inicial, a janela de pesquisa, a frequência de repetição e o número máximo de conjuntos de dados permitidos para compilação. Consulte a [descrição do produto Customer Journey Analytics](https://helpx.adobe.com/br/legal/product-descriptions/customer-journey-analytics.html) para obter mais detalhes. Decida sobre as opções disponíveis antes de solicitar suporte.

| | Customer Journey Analytics<br/>Selecionar | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Métodos de compilação disponíveis | Compilação em campo | Compilação em campo<br/>Compilação em gráfico | Compilação em campo<br>Compilação em gráfico</li> |
| Duração do preenchimento retroativo de compilação única | 13 meses | 13 meses | 25 meses |
| Janela de pesquisa e frequência de repetição | 1 dia, todos os dias<br/>até 7 dias, semanalmente | 1 dia, todos os dias<br/>até 14 dias, semanalmente | 1 dia, todos os dias<br/>até 30 dias, semanalmente |
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
      - Para a compilação baseada em gráfico, o namespace de identidade que você deseja usar para consultar o gráfico de identidade.
   - Sua preferência por janela de retrospectiva e frequência de repetição. Consulte seu pacote do Customer Journey Analytics para obter as [opções](#options) disponíveis.
   - Nome da sandbox.


2. O Suporte ao cliente da Adobe trabalha com a engenharia da Adobe para permitir a compilação ao receber sua solicitação. Depois de habilitado, um conjunto de dados rechaveado que contém uma coluna de ID compilada é exibido no Adobe Experience Platform. O Suporte ao cliente da Adobe pode fornecer a ID do novo conjunto de dados.
3. Quando ativado pela primeira vez, o Adobe fornece um preenchimento retroativo de dados compilados. Consulte seu pacote do Customer Journey Analytics para a [opção](#options) disponível.

4. Se você quiser usar o conjunto de dados compilado em uma análise entre canais, é necessário adicionar o conjunto de dados compilado a uma [conexão](../connections/overview.md) no Customer Journey Analytics. Em seguida, adicione outros conjuntos de dados necessários para a análise entre canais e selecione a ID de pessoa correta para cada conjunto de dados.

5. [Crie uma visualização de dados](/help/data-views/create-dataview.md) com base na conexão.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Depois que a visualização de dados for configurada, você poderá executar sua análise de relatórios do Customer Journey Analytics em canais e dispositivos.

## Limitações

- Aplique também qualquer alteração feita ao esquema de conjunto de dados do evento de origem ao novo esquema de conjunto de dados compilados.

- Se você remover o conjunto de dados de origem, o processamento do conjunto de dados compilado será interrompido e ele será removido pelo sistema.

- Os rótulos de uso de dados não são propagados automaticamente para o esquema do conjunto de dados compilado. Se você tiver rótulos de uso de dados aplicados ao esquema do conjunto de dados de origem, será necessário aplicá-los manualmente ao esquema do conjunto de dados compilado. Consulte [Gerenciamento de rótulos de uso de dados na Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview) para obter mais informações.
