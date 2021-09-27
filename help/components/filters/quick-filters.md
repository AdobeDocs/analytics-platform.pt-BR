---
description: Use filtros rápidos no Analysis Workspace.
title: Filtros rápidos
feature: Workspace Basics
role: User, Admin
source-git-commit: a32b260fb4c4696ac460903f44b240cb71a62db9
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 1%

---


# Filtros rápidos

Você pode criar filtros rápidos em um projeto para ignorar a complexidade do [Construtor de filtros](/help/components/filters/create-filters.md) completo. Filtros rápidos

* Aplicar somente a projetos específicos (você pode alterar isso).
* Permitir até 3 regras
* Não acomode contêineres aninhados ou regras sequenciais.
* Trabalhar em painéis com vários conjuntos de relatórios

Para uma comparação do que os filtros rápidos podem fazer com relação aos filtros da lista de componentes completos, acesse [aqui](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Os filtros rápidos estão atualmente em testes limitados e ainda não estão disponíveis.

## Pré-requisitos

Os usuários precisam da permissão [!UICONTROL Filtrar criação] no [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools) para poderem criar filtros rápidos.

## Criar filtros rápidos

Em uma tabela de Forma livre, clique no ícone filter+ no cabeçalho do painel:

![](assets/quick-seg1.png)

| Configuração | Descrição |
| --- | --- |
| Nome | O nome padrão de um filtro é uma combinação dos nomes das regras no filtro. Você pode renomear o filtro. |
| Incluir/excluir | Você pode incluir ou excluir componentes na definição do filtro, mas não ambos. |
| Contêiner de Ocorrência/Visita/Visitante | Os filtros rápidos incluem um [contêiner de filtro](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-overview.html?lang=en#section_AF2A28BE92474DB386AE85743C71B2D6) somente que permite incluir uma dimensão/métrica/intervalo de datas no (ou excluí-lo do) filtro.  O Visitante contém dados abrangentes específicos para visitantes em visitas e visualizações de página. Um contêiner de [!UICONTROL Visita] permite definir regras para detalhar os dados do visitante com base em visitas e um contêiner de [!UICONTROL Ocorrência] permite detalhar as informações do visitante com base em visualizações de página individuais. O contêiner padrão é [!UICONTROL Hit]. |
| Componentes (Dimension/métrica/intervalo de datas) | Defina até 3 regras adicionando dimensões e/ou métricas de componentes e/ou intervalos de datas e seus valores. Há 3 maneiras de encontrar o componente correto:<ul><li>Comece a digitar e o construtor [!UICONTROL Quick Filter] encontra automaticamente o componente apropriado.</li><li>Use a lista suspensa para localizar o componente.</li><li>Arraste e solte componentes do painel esquerdo.</li></ul> |
| Operador | Use o menu suspenso para encontrar operadores padrão e operadores [!UICONTROL Distinct Count]. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Sinal de mais (+) | Adicionar outra regra |
| Qualificadores E/OU | Você pode adicionar qualificadores &quot;AND&quot; ou &quot;OR&quot; às regras, mas não pode misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de filtro. |
| Aplicar | Aplique esse filtro ao painel. Se o filtro não contiver dados, você será perguntado se deseja continuar. |
| Abrir builder | Abre o Construtor de filtros. Depois de salvar o filtro no Construtor de filtros, ele não é mais considerado um &quot;Filtro rápido&quot;. Ele se torna parte da biblioteca de filtros da lista de componentes. |
| Cancelar | Cancele esse filtro rápido - não o aplique. |
| Intervalo de datas | O validador usa o intervalo de datas do painel para sua pesquisa de dados. Mas qualquer intervalo de datas aplicado em um filtro rápido substitui o intervalo de datas do painel na parte superior do painel. |
| Visualização (canto superior direito) | Permite ver se você tem um filtro válido e a amplitude deste. Representa o detalhamento do conjunto de dados que você pode esperar ver ao aplicar esse filtro. você pode receber um aviso que indica que esse filtro não tem dados. Você pode continuar ou alterar a definição do filtro. |

Este é um exemplo de um filtro que combina dimensões e métricas:

![](assets/quick-seg2.png)

O filtro é exibido na parte superior. Observe a barra lateral com listras azuis, em vez da barra lateral azul para filtros no nível do componente na biblioteca de filtros à esquerda.

![](assets/quick-seg3.png)

## Editar filtros rápidos

1. Passe o mouse sobre o filtro rápido e selecione o ícone de lápis.
1. Edite a definição de filtro ou o nome do filtro.

## Salvar filtros rápidos

Você pode optar por salvar filtros rápidos no [!UICONTROL Quick Filter Builder] ou no [!UICONTROL Filter Builder].

>[!IMPORTANT]
>Depois de salvar ou aplicar o filtro, não é mais possível editá-lo no Construtor de filtro rápido, somente no Construtor de filtro comum.

### Salvar no construtor do Filtro rápido

1. Depois de aplicar o filtro rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).
1. Clique em **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. (Opcional) Renomeie o filtro.
1. Clique em **[!UICONTROL Salvar]**.

Observe como a barra lateral do filtro muda de azul listrado para azul. Agora ele aparece na lista de componentes no painel esquerdo.

### Salvar no Construtor de filtros

1. Passe o mouse sobre o filtro rápido e selecione o ícone de informações (&quot;i&quot;).
1. Selecione **[!UICONTROL Salvar filtro]**

   ![](assets/save-quick-seg.png)

1. Deixe o nome como está ou renomeie o filtro.

   Volte para o Workspace e observe como o filtro agora tem uma barra lateral azul. Isso indica que ele não pode mais ser editado/aberto no Construtor de filtro rápido. E ao salvá-lo, ele se torna parte da lista de componentes.

   ![](assets/quick-seg4.png)

Depois de aplicar o filtro, você pode optar por adicioná-lo à lista de componentes de filtro e disponibilizá-lo para todos os projetos.

1. Passe o mouse sobre o filtro salvo e selecione o ícone de lápis.

1. Na parte superior do Construtor de filtros, observe esta caixa de diálogo:

   ![](assets/project-only.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Disponibilize este filtro para todos os projetos e adicione-o à lista de componentes.]**
1. Clique em **[!UICONTROL Salvar]**.
1. O filtro agora aparece na lista de componentes de filtro para todos os seus projetos.
1. Você também pode [compartilhar o filtro](/help/components/filters/manage-filters.md) com outras pessoas em sua organização.

## O que são filtros somente de projeto?

Os filtros somente do projeto são filtros rápidos ou filtros de projeto ad-hoc do Workspace. Ao editá-los/abri-los no [!UICONTROL Construtor de filtros], a caixa somente do projeto será exibida. Se você APLICAR um filtro rápido no construtor, mas não marcar a caixa disponibilizar , ele ainda será um filtro somente do projeto, mas não poderá mais ser aberto no [!UICONTROL Quick Filter Builder]. Se marcar a caixa e clicar em **[!UICONTROL SAVE]**, agora é um filtro de lista de componentes.