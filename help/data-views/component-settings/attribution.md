---
title: Configurações de componente de atribuição
description: Permite definir a atribuição padrão de uma métrica.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: ht
source-wordcount: '847'
ht-degree: 100%

---

# Configurações de componente de atribuição {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Atribuição"
>abstract="Configure o modelo de atribuição padrão aplicado a uma métrica nos relatórios."

<!-- markdownlint-enable MD034 -->


A atribuição permite personalizar como os itens de dimensão obtêm crédito por eventos bem-sucedidos.

![Janela de visualizações de dados, destacando a opção de definir atribuição](../assets/attribution-settings.png)

Por exemplo:

1. Um visitante do site clica em um link de pesquisa paga para uma das suas páginas de produto. Ele adiciona o produto ao carrinho, mas não o compra.
2. No dia seguinte, ele vê uma publicação nas redes sociais de um amigo. Ele clica no link e conclui a compra.

Em alguns relatórios, você pode desejar que a ordem seja atribuída à pesquisa paga. Em outros relatórios, você pode desejar que a ordem seja atribuída ao Social. A atribuição permite controlar esse aspecto dos relatórios.

## Definir o modelo de atribuição padrão de um componente

É possível definir um modelo de atribuição padrão para uma determinada métrica, atualizando-se a configuração da métrica na visualização de dados. Isso substitui o modelo de atribuição da métrica sempre que ela é usada no Analysis Workspace.

>[!NOTE]
>
>Considere o seguinte ao habilitar a atribuição em uma métrica:
>
>* **Ao usar o componente em um relatório com *uma dimensão*:** a atribuição do componente ignora o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>* **Ao usar o componente em um relatório com *várias dimensões*:** a atribuição do componente retém o modelo de alocação quando um modelo de atribuição não padrão é usado.
>
>   Várias dimensões estão disponíveis somente ao [exportar dados para a nuvem](/help/analysis-workspace/export/export-cloud.md).
>
> Para mais informações sobre alocação, consulte [Configurações do componente de persistência](/help/data-views/component-settings/persistence.md).

Para atualizar o modelo de atribuição padrão de um componente:

1. Abra a visualização de dados que contém o componente cujo modelo de atribuição padrão você deseja atualizar.

1. Selecione o componente e expanda a seção de atribuição no lado direito da tela.

   ![Janela de visualizações de dados, destacando a opção de definir atribuição](../assets/attribution-settings.png)

1. Selecione [!UICONTROL **Definir atribuição**] e clique no modelo de atribuição, no menu suspenso [!UICONTROL **Modelo de atribuição**].

   Consulte [Modelos de atribuição](#attribution-models) para saber mais sobre cada modelo de atribuição.

1. Selecione [!UICONTROL **Salvar e continuar**].

>[!TIP]
>
>Se a sua organização exigir que uma métrica tenha várias configurações de atribuição, você poderá executar um dos seguintes procedimentos:
>
> * Copie a métrica na visualização de dados com cada configuração de atribuição desejada. É possível incluir a mesma métrica várias vezes em uma visualização de dados, dando a cada métrica uma configuração diferente. Certifique-se de rotular cada métrica apropriadamente, para que os analistas entendam a diferença entre essas métricas ao gerar relatórios.
>
> * Substitua a métrica no Analysis Workspace. Nas [Configurações de coluna](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) de uma métrica, selecione **[!UICONTROL Usar modelo de atribuição não padrão]** para alterar o modelo de atribuição da métrica e a janela de retrospectiva desse relatório específico.

## Modelos de atribuição {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modelo"
>abstract="Selecione um modelo de atribuição para a métrica."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Janela de pesquisa

{{attribution-lookback-window}}



## Exemplo de atribuição {#attribution-example}

Considere o exemplo a seguir:

1. Em 15 de setembro, um visitante chega ao seu site através de um anúncio de pesquisa pago e depois sai.
1. Em 18 de setembro, a pessoa acessa seu site novamente por meio de um link de redes sociais que recebeu de um amigo. Eles adicionam vários itens ao carrinho, mas não compram nada.
1. Em 24 de setembro, sua equipe de marketing envia um email com um cupom para alguns dos itens em seu carrinho. Eles aplicam o cupom, mas visitam vários outros sites para ver se existem outros cupons disponíveis. Eles encontram outro cupom por meio de um anúncio de exibição e, em seguida, fazem uma compra de US$ 50.

Dependendo da janela de retrospectiva e do modelo de atribuição, os canais recebem crédito diferente. Veja a seguir alguns exemplos:

* Ao usar o modelo **primeiro contato** e uma **janela de retrospectiva de sessão**, a atribuição considera somente a terceira visita. Entre email e exibição, o email foi o primeiro, portanto, o email recebe 100% de crédito pela compra de US$ 50.

* Ao usar o modelo **primeiro contato** e uma **janela de retrospectiva de pessoa**, a atribuição considera todas as três visitas. A pesquisa paga foi a primeira, portanto recebe 100% de crédito pela compra de US$ 50.

* Ao usar o modelo **linear** e uma **janela de retrospectiva de sessão**, o crédito é dividido entre email e exibição. Ambos os canais recebem um crédito de US$ 25.
Ao usar o modelo **linear** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição. Cada canal recebe um crédito de US$ 12,50 por esta compra.

* Ao usar o modelo **Forma de J** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição.

   * O crédito será de 60% para a exibição (US$ 30).
   * De 20% para a pesquisa paga (US$ 10).
   * Os 20% restantes são divididos entre redes sociais e email (US$ 5 para cada).

* Ao usar o modelo **Decaimento de tempo** e uma **janela de retrospectiva de pessoa**, o crédito é dividido entre pesquisa paga, redes sociais, email e exibição. Usando a meia-vida padrão de 7 dias:

   * Intervalo de 0 dias entre o ponto de contato de exibição e a conversão. `2^(-0/7) = 1`
   * Intervalo de 0 dias entre o ponto de contato de email e a conversão. `2^(-0/7) = 1`
   * Intervalo de seis dias entre o ponto de contato de rede social e a conversão. `2^(-6/7) = 0.552`
   * Intervalo de nove dias entre o ponto de contato de pesquisa paga e a conversão. `2^(-9/7) = 0.41`
   * A normalização desses valores resulta no seguinte:

      * Exibição: 33,8%, crédito de US$ 16,88
      * Email: 33,8%, crédito de US$ 16,88
      * Redes sociais: 18,6%, crédito de US$ 9,32
      * Pesquisa paga: 13,8%, crédito de US$ 6,92

Os eventos de conversão que normalmente têm números inteiros são divididos se o crédito pertencer a mais de um canal. Por exemplo, se dois canais contribuem para um pedido usando um modelo de atribuição linear, ambos os canais recebem 0,5 desse pedido. Essas métricas parciais são somadas para todas as pessoas e depois arredondadas para o número inteiro mais próximo para fins de geração de relatórios.


