---
title: Perguntas frequentes sobre a compilação
description: Saiba mais sobre as perguntas frequentes sobre compilação.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 332c9240399e429d971855ab1aa685bd4d07b86e
workflow-type: tm+mt
source-wordcount: '2149'
ht-degree: 84%

---

# Perguntas frequentes

Confira abaixo algumas perguntas frequentes sobre a compilação:

## Mover entre canais

+++ Como posso usar a compilação para ver como as pessoas mudam de um tipo de canal para outro?

Você pode usar uma visualização de fluxo com a dimensão ID do conjunto de dados.

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e crie um projeto em branco do Workspace.
2. Clique na guia **[!UICONTROL ** Visualizações **]** à esquerda e arraste uma visualização de **[!UICONTROL **&#x200B; Fluxo &#x200B;**]** até a tela à direita.
3. Clique na guia **[!UICONTROL ** Componentes **]** à esquerda e arraste a dimensão **[!UICONTROL ** ID de conjunto de dados **]** até o local central rotulado como **[!UICONTROL **&#x200B; Dimensão ou item &#x200B;**]**.
4. Este relatório de fluxo é interativo. Para expandir os fluxos para páginas seguintes ou anteriores, selecione qualquer um dos valores. Use o menu de clique com o botão direito do mouse para expandir ou recolher colunas. Dimensões diferentes também podem ser usadas no mesmo relatório de fluxo.

Se você quiser renomear itens de dimensão da ID de conjunto de dados, poderá usar um conjunto de dados de pesquisa.

+++

## Reproduzir novamente

+++ Até que ponto no passado a compilação reproduz perfis novamente?

A janela de pesquisa para rechaveamento depende da frequência com a qual você deseja reproduzir dados novamente. Por exemplo, se você configurar a compilação para reproduzir os dados novamente uma vez por semana, a janela de pesquisa para rechaveamento será de sete dias. Se você configurar a compilação para reproduzir os dados novamente todos os dias, a janela de pesquisa para rechaveamento será de um dia.

+++

## Dispositivos compartilhados

+++ Como os dispositivos compartilhados são manipulados?

Em algumas situações, é possível que várias pessoas façam logon no mesmo dispositivo. Os exemplos incluem um dispositivo compartilhado em casa, PCs compartilhados em uma biblioteca ou um quiosque em uma loja de varejo.

A ID de pessoa substitui a ID persistente; portanto, os dispositivos compartilhados são considerados pessoas separadas (mesmo que sejam oriundos do mesmo dispositivo).

Consulte o caso de uso [Dispositivos compartilhados](/help/use-cases/stitching/shared-devices.md) para obter mais detalhes.

+++

## Várias IDs persistentes

+++ Como a a compilação lida com situações em que uma mesma pessoa tem várias IDs persistentes?

Em algumas situações, um usuário individual pode ser associado a muitas IDs persistentes. Um exemplo é um indivíduo que limpa os cookies do navegador com frequência ou que usa o modo privado/anônimo do navegador.

No caso da compilação baseada em campos, o número de IDs persistentes é irrelevante em favor da ID de pessoa. Um mesmo usuário pode pertencer a qualquer número de dispositivos sem afetar a capacidade do Customer Journey Analytics de compilar entre dispositivos.

Para a compilação baseada em gráficos, uma única pessoa pode ter muitas IDs persistentes no gráfico de identidade. A compilação baseada em gráficos usa a ID persistente com base no namespace especificado. Caso haja mais IDs persistentes para o mesmo namespace, a primeira ID persistente lexicográfica será usada.

+++

## Processo de compilação

+++ Após entrar em contato com minha equipe de contas da Adobe e fornecer as informações desejadas, quanto tempo levará para o conjunto de dados rechaveado ser disponibilizado?

A compilação em tempo real está disponível aproximadamente uma semana depois de a Adobe habilitar a compilação. A disponibilidade do preenchimento retroativo depende da quantidade de dados existentes. Os pequenos conjuntos de dados (menos de um milhão de eventos por dia) normalmente levam alguns dias, enquanto grandes conjuntos de dados (um bilhão de eventos por dia) podem levar uma semana ou mais.

+++

## Análise entre dispositivos versus análise entre canais

+++ Qual é a diferença entre a análise entre dispositivos (um recurso do Analytics tradicional) e a análise entre canais?

A [análise entre dispositivos](https://experienceleague.adobe.com/en/docs/analytics/components/cda/overview) é um recurso específico do Adobe Analytics tradicional que permite compreender como as pessoas operam em diversos dispositivos. Ela oferece dois fluxos de trabalho para vincular dados do dispositivo: compilação em campo e gráfico do dispositivo.

A análise entre canais é um recurso específico do Customer Journey Analytics que permite entender como as pessoas operam em diversos dispositivos e canais. Ela compila a ID de pessoa de um conjunto de dados, permitindo que ele seja combinado perfeitamente com outros conjuntos de dados. Esse recurso funciona de forma semelhante à compilação baseada em campos da análise entre dispositivos, mas a implementação difere devido às distintas arquiteturas de dados entre o Analytics tradicional e o Customer Journey Analytics. Consulte [Compilação](overview.md) e o caso de uso da [análise entre canais](../use-cases/cross-channel/cross-channel.md) para obter mais informações.

+++

## Privacidade

+++ Como a compilação trata as solicitações de privacidade?

A Adobe trata as solicitações de privacidade de acordo com as leis locais e internacionais. A Adobe oferece o [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/pt-br/docs/experience-platform/privacy/home) para enviar solicitações de acesso e exclusão de dados. As solicitações se aplicam aos conjuntos de dados originais e rechaveados.

>[!IMPORTANT]
>
>O processo de descompilação, como parte das solicitações de privacidade, mudou no início de 2025. O processo de descompilação atual compila novamente os eventos usando a versão mais recente de identidades conhecidas. Essa reatribuição de eventos para outra identidade pode ter consequências legais indesejáveis. Para solucionar essas preocupações, a partir de 2025, o novo processo de descompilação atualiza os eventos que são objeto da solicitação de privacidade com a ID persistente.
> 

Para ilustrar, imagine os seguintes dados de identidades e eventos antes e depois da compilação.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilado | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa | ID resultante | namespace compilado |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Processo atual para solicitações de privacidade**

Quando uma solicitação de privacidade é recebida em referência ao cliente com CustID Bob, as linhas com entradas tachadas são excluídas. Outros eventos são corrigidos com base no mapa de identidade. Por exemplo, a primeira ID compilada no conjunto de dados compilado é atualizada para **Alex**.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilado | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa | ID resultante | namespace compilado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Novo processo de solicitação de privacidade**

Quando uma solicitação de privacidade é recebida em referência ao cliente com CustID Bob, as linhas com entradas tachadas são excluídas. Outros eventos são corrigidos com a ID persistente. Por exemplo, a primeira ID compilada no conjunto de dados compilado é atualizada para **123**.

| Mapa de identidade | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados de eventos | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Conjunto de dados compilado | ID | carimbo de data e hora | ID persistente | namespace persistente | ID da pessoa | namespace de pessoa | ID resultante | namespace compilado |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Valores de IDs persistentes em branco

+++ O que acontece se o campo de ID persistente de um ou mais eventos estiver em branco?

Se o campo ID persistente estiver em branco em um evento em um conjunto de dados que está sendo compilado , a ID resultante desse evento será determinada de uma das duas formas a seguir:

* Se o campo ID de pessoa não estiver em branco, o Customer Journey Analytics usará o valor na ID de pessoa como a ID resultante.
* Se o campo ID de pessoa estiver em branco, o Customer Journey Analytics também deixará a ID resultante em branco. Nesse caso, a ID persistente, a ID de pessoa e a ID resultante estarão em branco no evento. Esses tipos de eventos são descartados de qualquer conexão do Customer Journey Analytics usando o conjunto de dados que está sendo compilado em que a ID resultante foi escolhida como a ID de pessoa.

+++


## Valores de IDs de pessoas indefinidos

+++ O que acontece se o campo de ID de pessoa de um ou mais eventos contiver valores de espaço reservado, como `Undefined`?

Tenha cuidado com o “recolhimento de pessoas”, que ocorre quando a compilação é aplicada a dados que usam valores de espaço reservado para IDs transitórias. Na tabela de exemplo abaixo, IDs de pessoas indefinidas oriundas de um conjunto de dados proveniente de um sistema de CRM são preenchidas com o valor “Indefinido”, resultando na representação incorreta de pessoas.

| Evento | Carimbo de data e hora | ID persistente (ID do cookie) | ID transitória | ID resultante (após a repetição) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | Cory | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | Indefinido | **Indefinido** |
| 4 | 2023-05-12 12:04 | 456 | - | **Indefinido** |
| 5 | 2023-05-12 12:05 | 789 | Indefinido | **Indefinido** |
| 6 | 2023-05-12 12:06 | 012 | Indefinido | **Indefinido** |
| 7 | 2023-05-12 12:07 | 012 | - | **Indefinido** |
| 8 | 2023-05-12 12:03 | 789 | Indefinido | **Indefinido** |
| 9 | 2023-05-12 12:09 | 456 | - | **Indefinido** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **4 dispositivos** | **2 pessoas**:<br/>Eventos 1, 4, 7, 9, 10 descartados | **2 pessoas**:<br/>Cory, não autenticado (recolhido para uma pessoa) |

+++

## Comparação de métricas

+++ Qual é a comparação entre as métricas nos conjuntos de dados compilados do Customer Journey Analytics e métricas semelhantes em conjuntos de dados não compilados do Customer Journey Analytics e o Adobe Analytics?

Certas métricas do Customer Journey Analytics são semelhantes às métricas do Analytics tradicional, mas outras são diferentes, dependendo do que você está comparando. A tabela abaixo compara várias métricas comuns:

| **Dados compilados do Customer Journey Analytics** | **Dados não compilados do Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate com CDA** |
| ----- | ----- | ----- | ----- |
| **Pessoas** = Contagem de IDs de pessoa distintas, em que a ID resultante é escolhida como ID de pessoa. **Pessoas** pode ser superior ou inferior a **Visitantes únicos** no Adobe Analytics tradicional, dependendo da saída do processo de compilação. | **Pessoas** = contagem de IDs de pessoas diferentes com base na coluna selecionada como ID de pessoa. As **Pessoas** nos conjuntos de dados do conector de origem do Analytics são semelhantes a **Visitantes únicos** no Adobe Analytics tradicional, se `endUserIDs._experience.aaid.id` for escolhida como ID de pessoa no Customer Journey Analytics. | **Visitantes únicos** = Contagem de IDs de visitante distintas. **Visitantes únicos** pode não ser o mesmo que a contagem de **ECID** s. | Consulte [de pessoas](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/people). |
| **Sessões**: definidas com base nas configurações de sessão na visualização de dados do Customer Journey Analytics. O processo de compilação pode combinar sessões individuais de vários dispositivos em uma única sessão. | **Sessões**: definidas com base nas configurações de sessão especificadas na visualização de dados do Customer Journey Analytics. | **Visitas**: consulte [Visitas](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/visits). | **Visitas**: definido com base nas configurações de sessão especificadas no [conjunto de relatórios virtuais do CDA](https://experienceleague.adobe.com/en/docs/analytics/components/cda/setup). |
| **Eventos** = contagem de linhas nos dados compilados no Customer Journey Analytics. Essa métrica é bem semelhante às **Ocorrências** do Adobe Analytics tradicional. No entanto, observe as perguntas frequentes acima relacionadas a linhas com uma ID persistente em branco. | **Eventos** = contagem de linhas nos dados não compilados no Customer Journey Analytics. Essa métrica é bem semelhante às **Ocorrências** do Adobe Analytics tradicional. No entanto, observe que, se algum evento tiver uma ID de pessoa em branco nos dados não compilados no data lake da Experience Platform, esses eventos não são incluídos no Customer Journey Analytics. | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). | **Ocorrências**: consulte [Ocorrências](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/occurrences). |

Outras métricas pode ser semelhantes no Customer Journey Analytics e no Adobe Analytics. Por exemplo, a contagem total de 1 a 100 [eventos personalizados](https://experienceleague.adobe.com/en/docs/analytics/components/metrics/custom-events) do Adobe Analytics é comparável entre o Adobe Analytics tradicional e o Customer Journey Analytics (sejam compilados ou não). [Diferenças de recursos](/help/getting-started/aa-vs-cja/cja-aa.md)), como a desduplicação de eventos entre o Customer Journey Analytics e o Adobe Analytics, podem causar uma discrepância entre os dois produtos.

+++

## Mapa de identidade

+++ O Customer Journey Analytics pode usar campos do mapa de identidade?

Sim, o Customer Journey Analytics pode usar campos do mapa de identidade para compilação [baseada em campos](/help/stitching/fbs.md#identitymap) e [baseada em gráficos](/help/stitching/gbs.md#identitymap).

+++

## Alternar para a compilação baseada em gráficos

+++ Os dados precisam ser assimilados novamente para alternar da compilação em campos para a compilação em gráficos?

Os dados não precisam ser assimilados novamente na Experience Platform. No entanto, os dados precisam ser reconfigurados no Customer Journey Analytics. Siga estas etapas:

1. Configure o novo conjunto de dados compilado com base em gráficos, usando a compilação baseada em gráficos.
1. Crie uma nova conexão temporária com uma janela de dados muito pequena.
1. Configure o novo conjunto de dados baseado em gráficos como parte dessa conexão temporária.
1. Verifique se a compilação baseada em gráficos funciona corretamente com essa nova conexão temporária.
1. Se a compilação baseada em gráficos funcionar conforme esperado, solicite qualquer preenchimento retroativo adicional para o conjunto de dados baseado em gráficos e troque o conjunto de dados baseado em campos na conexão original pelo novo conjunto de dados baseado em gráficos.
1. Remova a conexão temporária.

+++

## Problemas na geração de relatórios

+++ Ocorreria algum problema nos relatórios existentes?

Se você seguir as etapas descritas acima, não. Caso contrário, solicite suporte adicional à Adobe Consulting.

+++

## Habilitar um conjunto de dados para o serviço de identidade

+++ Como faço para habilitar um conjunto de dados somente para o serviço de identidade? 

Certifique-se de que um conjunto de dados esteja ativado para que o Serviço de identidade use o conjunto de dados na compilação baseada em gráfico.

Não é necessário ter uma licença para que a Real-Time Customer Data Platform use a compilação baseada em gráficos. A compilação baseada em gráficos baseia-se em um gráfico de identidade disponível, não em perfis de clientes em tempo real.

Para verificar um conjunto de dados existente e habilitá-lo apenas para o Serviço de Identidade, use uma solicitação `PATCH` para o ponto de extremidade `/datasets` que usa apenas a marca `unifiedIdentity`. Por exemplo:

```shell
curl -X PATCH \
  https://platform.adobe.io/data/foundation/catalog/dataSets/{DATASET_ID} \
  -H 'Content-Type:application/json-patch+json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '[
        { "op": "add", "path": "/tags/unifiedIdentity", "value": ["enabled:true"] }
      ]'
```

Qualquer uso da tag `unifiedProfile` na solicitação, enquanto você não tiver licença para usar o perfil de dados do cliente em tempo real, retornará um erro.

Consulte [Criar um conjunto de dados habilitado para perfil e identidade](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#enable-the-dataset) para obter mais informações.

+++ 


## Valores de namespace compilados

+++ Por que os valores de namespace compilados nem sempre correspondem ao valor de namespace de identidade que você pode usar em outro conjunto de dados na conexão do CJA?

Por padrão, os valores de namespace compilados estão em minúsculas. Então, `custEmail` torna-se `custemail`. Se você tiver outro conjunto de dados com um valor de namespace de identidade de `custEmail`, os dois valores não corresponderão. Para contornar esse comportamento nos relatórios, você pode usar a função de campo derivada [lowercase()](/help/data-views/derived-fields/derived-fields.md#lowercase) para corresponder aos valores do namespace de identidade.

+++
