---
description: Usar filtros rápidos no Analysis Workspace para o Customer Journey Analytics
title: Filtros rápidos
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: a69f9eef39c0eceee1964a3b8741b7538b218ece
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 45%

---

# Filtros rápidos

Os filtros rápidos permitem explorar facilmente os dados em um determinado projeto, sem a necessidade de criar um filtro de lista de componentes mais complexo no [Construtor de filtros](/help/components/filters/create-filters.md).

Considere o seguinte ao criar filtros rápidos:

* Os filtros rápidos se aplicam somente ao projeto em que foram criados. Eles não estão disponíveis em outros projetos e não podem ser compartilhados com outros usuários.
* São permitidas no máximo 3 regras.
* Não há suporte para contêineres aninhados ou regras sequenciais.

O vídeo a seguir demonstra como usar filtros rápidos. (Observação: este vídeo usa o termo &quot;segmentos rápidos&quot; em vez de &quot;filtros rápidos&quot;. No entanto, a funcionalidade é a mesma.)

>[!VIDEO](https://video.tv.adobe.com/v/341466/?quality=12&learn=on)

## Criar um filtro rápido {#create}

Qualquer usuário do Analysis Workspace pode criar um filtro rápido.

Para criar um filtro rápido:

1. Escolha um dos seguintes métodos para começar a criar o filtro rápido:

   * **Ad hoc (arrastar e soltar):** No painel à esquerda, arraste um componente para a área de soltar ao lado do **Filtro** no cabeçalho do painel, selecione o **Editar** ícone para ajustar o filtro.

      ![Editar filtro ad hoc](assets/filter-adhoc-edit.png)

      >[!NOTE]
      >
      > Considere o seguinte ao criar um filtro rápido ad hoc (arrastar e soltar):
      > * Os seguintes tipos de componentes não são suportados: métricas e dimensões calculadas, bem como métricas a partir das quais não é possível criar filtros.
      > * Para dimensões e eventos completos, o Analysis Workspace cria filtros de ocorrência “existe”. Exemplos: `Hit where eVar1 exists` ou `Hit where event1 exists`.
      > * Se “não especificado” ou “nenhum” forem soltos na área de destino do filtro, eles serão automaticamente convertidos em um filtro “não existe” para que sejam tratados corretamente durante a filtragem.



   * **Usando o ícone de filtro:** Em uma tabela de Forma livre, selecione o **Filtro** no cabeçalho do painel.

      ![Filtro de segmentos](assets/quick-seg1.png)

1. Ajuste qualquer uma das seguintes configurações:

   | Configuração | Descrição |
   | --- | --- |
   | [!UICONTROL Nome] | O nome padrão de um filtro é uma combinação dos nomes das regras no filtro. É possível renomear o filtro para um nome mais amigável. |
   | [!UICONTROL Incluir/excluir] | Você pode incluir ou excluir componentes na definição do filtro, mas não ambos. |
   | [!UICONTROL Container de ocorrência/visita/visitante] | Filtros rápidos incluem somente um [container de filtro](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=pt-BR#filter-containers) que permite incluir uma dimensão/métrica/intervalo de datas no (ou excluí-lo do) filtro. O [!UICONTROL Visitante] contém dados abrangentes específicos para o visitante entre visitas e visualizações de página. Um container de [!UICONTROL Visita] permite definir regras para detalhar os dados do visitante com base em visitas, e um container de [!UICONTROL Ocorrência] permite detalhar as informações do visitante com base em visualizações de página individuais. O container padrão é o de [!UICONTROL Ocorrência]. |
   | [!UICONTROL Componentes] (Dimensão/métrica/intervalo de datas) | Defina até 3 regras adicionando componentes (dimensões, métricas, intervalos de datas ou valores de dimensão). Há três maneiras de encontrar o componente correto:<ul><li>Comece a digitar e o construtor de filtro rápido encontra automaticamente o componente apropriado.</li><li>Use a lista suspensa para localizar o componente.</li><li>Arraste os componentes do painel esquerdo e solte-os.</li></ul> |
   | [!UICONTROL Operador] | Use o menu suspenso para encontrar operadores padrão e operadores de [!UICONTROL Contagem distinta]. Consulte [Operadores de filtro](operators.md). |
   | Sinal de mais (+) | Adicionar outra regra |
   | Qualificadores AND/OR | É possível adicionar qualificadores “AND” ou ”OR” às regras, mas não é possível misturar &quot;AND&quot; e &quot;OR&quot; em uma única definição de filtro. |
   | [!UICONTROL Aplicar] | Aplicar esse filtro ao painel. Se o filtro não contiver dados, você será perguntado se deseja continuar. |
   | [!UICONTROL Abrir builder] | Abre o Construtor de filtros. Depois de salvar ou aplicar o filtro no Construtor de filtros, ele não é mais considerado um &quot;Filtro rápido&quot;. Ele se torna parte da biblioteca de filtros da lista de componentes. <p>Para disponibilizar o componente em todos os projetos e no painel à esquerda, selecione a opção . [!UICONTROL **Disponibilize esse filtro para todos os projetos e adicione-o à lista de componentes**].</p><p>Para obter mais informações, consulte a seção [Salvar um filtro rápido como um filtro de lista de componentes](#save-a-quick-filter-as-a-component-list-filter) neste artigo.</p><p>**Observação:** Somente usuários com a permissão de Criação de filtro na [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR#analytics-tools) pode abrir o Construtor de filtros.</p> |
   | [!UICONTROL Cancelar] | Cancele esse filtro rápido (não o aplique). |
   | [!UICONTROL Intervalo de datas] | O validador usa o intervalo de datas do painel para a pesquisa de dados. Mas qualquer intervalo de datas aplicado em um filtro rápido substitui o intervalo de datas na parte superior do painel. |
   | Pré-visualizar (canto superior direito) | Permite ver se você tem um filtro válido e a amplitude deste. Representa o detalhamento do conjunto de dados que se pode esperar ao aplicar esse filtro. Você pode receber um aviso indicando que esse filtro não tem dados. Nesse caso, você pode continuar ou alterar a definição do filtro. |

1. Selecionar [!UICONTROL **Aplicar**] para salvar as alterações.

## Editar um filtro rápido {#edit}

1. Passe o mouse sobre o filtro rápido que deseja editar, em seguida, selecione o **Editar** ícone .

   ![Editar filtro ad hoc](assets/filter-adhoc-edit.png)

1. Edite a definição ou o nome do filtro.
1. Selecionar [!UICONTROL **Aplicar**] para salvar as alterações.

## Salvar um filtro rápido como um filtro de lista de componentes {#save}

>[!IMPORTANT]
>
> Considere o seguinte ao salvar um filtro rápido:
> 
> * Para salvar um filtro rápido, você precisa da permissão Criação de filtro na [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=pt-BR#analytics-tools).
> 
> * Depois de salvar ou aplicar o filtro, ele não poderá mais ser editado no construtor de filtro rápido. Em vez disso, você deve usar o Construtor de filtros normal.


Você pode optar por salvar filtros rápidos como filtros da lista de componentes. As vantagens dos filtros da lista de componentes incluem:

* Disponibilidade em todos os projetos do Workspace
* Oferecem suporte a filtros mais complexos, bem como filtros sequenciais

Você pode salvar filtros do Construtor de filtros rápidos ou do [!UICONTROL Construtor de filtros].

### Salvar no construtor de filtro rápido {#save2}

1. Depois de aplicar o filtro rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).
1. Selecionar **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes]**.
1. Renomeie o filtro (opcional).
1. Selecione **[!UICONTROL Salvar]**.

   O filtro agora aparece na lista de componentes no painel esquerdo. Além disso, observe que a barra lateral do filtro muda de azul claro para um azul mais escuro, indicando que não pode mais ser editada ou aberta no construtor de filtro rápido.

### Salvar no Construtor de filtros {#save3}

1. Depois de aplicar o filtro rápido, passe o mouse sobre ele e selecione o ícone de informações (&quot;i&quot;).
1. Selecione **[!UICONTROL Salvar filtro]**
1. (Opcional) Renomeie o filtro e selecione [!UICONTROL **Aplicar**].

   Retorne ao Workspace e observe que a barra lateral do filtro muda de azul claro para azul mais escuro, indicando que não pode mais ser editada ou aberta no construtor de filtro rápido. E ao salvá-lo, ele se torna parte da lista de componentes.

   ![Filtrar lista de componentes](assets/quick-seg4.png)

Depois de aplicar o filtro, você pode optar por adicioná-lo à lista de componentes de filtro e disponibilizá-lo para todos os projetos.

1. Passe o mouse sobre o filtro salvo e selecione o ícone do lápis.

1. Na parte superior do Construtor de filtros, observe esta caixa de diálogo:

   ![Filtrar caixa de diálogo](assets/project-only.png)

1. Marque a caixa de seleção ao lado de **[!UICONTROL Disponibilizar para todos os projetos e adicionar à lista de componentes.]**
1. Selecione **[!UICONTROL Salvar]**.
O filtro agora aparece na lista de componentes de filtro para todos os seus projetos.
Você também pode [compartilhar o filtro](/help/components/filters/manage-filters.md) com outras pessoas em sua empresa.

## Exemplo de filtro rápido

O exemplo a seguir de um filtro combina dimensões e métricas:

![Exemplo de definição de filtro](assets/quick-seg2.png)

