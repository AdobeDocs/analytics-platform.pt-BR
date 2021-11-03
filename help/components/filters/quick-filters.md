---
description: Usar filtros rápidos no Analysis Workspace para o Customer Journey Analytics
title: Filtros rápidos
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 1334e1edb36583ba978936fecbff2657e63a94bf
workflow-type: ht
source-wordcount: '950'
ht-degree: 100%

---

# Filtros rápidos

Você pode criar filtros rápidos dentro de um projeto para evitar a complexidade do [Construtor de filtros](/help/components/filters/create-filters.md) completo. Filtros rápidos

* Aplica-se somente aos projetos em que foram criados (é possível alterar isso).
* Permitem até três regras
* Não acomodam containers aninhados ou regras sequenciais.

Para uma comparação do que os filtros rápidos podem fazer com relação aos filtros completos da lista de componentes, acesse [aqui](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Os filtros rápidos estão atualmente em período de testes e ainda não estão disponíveis para o público geral.

## Pré-requisitos

Qualquer pessoa pode criar um Segmento rápido. No entanto, é necessário ter a permissão Criação de segmentos no [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR#analytics-tools) para salvar segmentos rápidos ou abri-los no Construtor de segmentos.

## Criar filtros rápidos

Em uma tabela de Forma livre, clique no ícone do filtro+ no cabeçalho do painel:

![Filtro de segmentos](assets/quick-seg1.png)

| Configuração | Descrição |
| --- | --- |
| Nome | O nome padrão de um filtro é uma combinação dos nomes das regras no filtro. É possível renomear o filtro para um nome mais amigável. |
| Incluir/excluir | Você pode incluir ou excluir componentes na definição do filtro, mas não ambos. |
| Container de ocorrência/visita/visitante | Filtros rápidos incluem somente um [container de filtro](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=pt-BR#filter-containers) que permite incluir uma dimensão/métrica/intervalo de datas no (ou excluí-lo do) filtro. O [!UICONTROL Visitante] contém dados abrangentes específicos para o visitante entre visitas e visualizações de página. Um container de [!UICONTROL Visita] permite definir regras para detalhar os dados do visitante com base em visitas, e um container de [!UICONTROL Ocorrência] permite detalhar as informações do visitante com base em visualizações de página individuais. O container padrão é o de [!UICONTROL Ocorrência]. |
| Componentes (dimensão/métrica/intervalo de datas) | Defina até 3 regras adicionando componentes (dimensões, métricas, intervalos de datas ou valores de dimensão). Há três maneiras de encontrar o componente correto:<ul><li>Comece a digitar e o construtor de [!UICONTROL Filtros rápidos] encontrará automaticamente o componente apropriado.</li><li>Use a lista suspensa para localizar o componente.</li><li>Arraste os componentes do painel esquerdo e solte-os.</li></ul> |
| Operador | Use o menu suspenso para encontrar operadores padrão e operadores de [!UICONTROL Contagem distinta]. Consulte [Operadores de filtro](operators.md). |
| Sinal de mais (+) | Adicionar outra regra |
| Qualificadores E/OU | É possível adicionar qualificadores “E” ou ”OU” às regras, mas não é possível misturar &quot;E&quot; e &quot;OU&quot; em uma única definição de filtro. |
| Aplicar | Aplicar esse filtro ao painel. Se o filtro não contiver dados, você será questionado se deseja continuar. |
| Abrir builder | Abre o Construtor de filtros. Depois de salvar ou aplicar o filtro no Construtor de filtros, ele não é mais considerado um “Filtro rápido”. Ele se torna parte da biblioteca de filtros da lista de componentes. |
| Cancelar | Cancele esse filtro rápido - não o aplique. |
| Intervalo de datas | O validador usa o intervalo de datas do painel para a pesquisa de dados. Mas qualquer intervalo de datas aplicado em um filtro rápido substitui o intervalo de datas na parte superior do painel. |
| Pré-visualizar (canto superior direito) | Permite ver se você tem um filtro válido e a amplitude deste. Representa o detalhamento do conjunto de dados que se pode esperar ao aplicar esse filtro. Você pode receber um aviso indicando que esse filtro não tem dados. Nesse caso, você pode continuar ou alterar a definição do filtro. |

Aqui está um exemplo de um filtro que combina dimensões e métricas:

![Exemplo de definição de filtro](assets/quick-seg2.png)

O filtro é exibido na parte superior. Observe a barra lateral com listras azuis, diferente da barra lateral azul para filtros baseados em componente na biblioteca de filtros à esquerda.

![Filtrar locais do componente](assets/quick-seg3.png)

## Editar filtros rápidos

1. Passe o mouse sobre o filtro rápido e selecione o ícone do lápis.
1. Edite a definição ou o nome do filtro.

## Salvar filtros rápidos

Você pode optar por salvar filtros rápidos no [!UICONTROL Construtor de filtros rápidos] ou no [!UICONTROL Construtor de filtros].

>[!IMPORTANT]
>Depois de salvar ou aplicar o filtro, não é mais possível editá-lo no Construtor de filtros rápidos, somente no Construtor de filtros comum.

### Salvar no Construtor de filtros rápidos

1. Depois de aplicar o filtro rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).
1. Clique em **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. Renomeie o filtro (opcional).
1. Clique em **[!UICONTROL Salvar]**.

Observe como a barra lateral do filtro muda de azul listrado para azul-claro. Agora ele aparece na lista de componentes no painel esquerdo.

### Salvar no Construtor de filtros

1. Passe o mouse sobre o filtro rápido e selecione o ícone de informações (&quot;i&quot;).
1. Selecione **[!UICONTROL Salvar filtro]**
1. Deixe o nome como está ou renomeie o filtro.

   Volte para o espaço de trabalho e observe como o filtro agora tem uma barra lateral azul-clara. Isso indica que ele não pode mais ser editado/aberto no Construtor de filtros rápidos. E ao salvá-lo, ele se torna parte da lista de componentes.

   ![Filtrar lista de componentes](assets/quick-seg4.png)

Depois de aplicar o filtro, você pode optar por adicioná-lo à lista de componentes de filtro e disponibilizá-lo para todos os projetos.

1. Passe o mouse sobre o filtro salvo e selecione o ícone do lápis.

1. Na parte superior do Construtor de filtros, observe esta caixa de diálogo:

   ![Filtrar caixa de diálogo](assets/project-only.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes.]**
1. Clique em **[!UICONTROL Salvar]**.
1. O filtro agora aparece na lista de componentes de filtro para todos os seus projetos.
1. Você também pode [compartilhar o filtro](/help/components/filters/manage-filters.md) com outras pessoas em sua empresa.

## O que são filtros exclusivos de projeto?

Filtros exclusivos de projeto são filtros rápidos ou filtros de projeto ad hoc do Espaço de trabalho. Ao editá-los/abri-los no [!UICONTROL Construtor de filtros], a caixa exclusiva do projeto será exibida.

Se você APLICAR um filtro rápido no construtor sem marcar a caixa para &quot;disponibilizá-lo&quot;, ele ainda será um filtro exclusivo do projeto, mas não poderá mais ser aberto no [!UICONTROL Construtor de filtros rápidos]. Se marcar a caixa e clicar em **[!UICONTROL Salvar]**, ele se torna um filtro da lista de componentes.
