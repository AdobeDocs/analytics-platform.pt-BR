---
title: Criar ou editar uma visualização de dados
description: Todas as configurações que podem ser ajustadas para criar ou editar uma visualização de dados.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c106e178c5aecdaf061001247a1ee6ef183d043e
workflow-type: ht
source-wordcount: '1431'
ht-degree: 100%

---

# Criar ou editar uma visualização de dados

A criação de uma visualização de dados envolve criar métricas e dimensões com base em elementos de esquema ou utilizar componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica, dependendo das necessidades da sua empresa. Depois de arrastar um elemento do esquema para uma visualização de dados, algumas opções serão exibidas à direita, onde você poderá ajustar como a dimensão ou métrica opera no Customer Journey Analytics.

Veja um vídeo sobre este tópico:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

Criar ou editar uma visualização de dados:

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e acesse a guia **[!UICONTROL Visualizações de dados]**.
1. Para criar uma visualização de dados, selecione **[!UICONTROL Criar nova visualização de dados]**. Como alternativa, selecione uma visualização de dados existente na lista de visualizações de dados para editá-la.


## Configurar

Para configurar uma visualização de dados nova ou existente:

1. Selecione a guia **[!UICONTROL Configurar]** (se ainda não estiver ativa).

   ![Configurar visualização de dados](assets/dataview-configure.png)
1. Especifique os detalhes de [!UICONTROL configurações], [!UICONTROL container] e [!UICONTROL calendário] (veja abaixo).
1. Selecione **[!UICONTROL Salvar e continuar]** para continuar configurando sua visualização de dados nova ou existente. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.


### Configurações

Fornece configurações abrangentes para a visualização de dados.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Conexão] | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém um ou mais conjuntos de dados da Adobe Experience Platform. |
| [!UICONTROL Nome] | Obrigatório. O nome da visualização de dados. Esse valor aparece na lista suspensa no canto superior direito do Analysis Workspace. |
| [!UICONTROL Descrição] | Opcional. A Adobe recomenda uma descrição detalhada para que os usuários entendam por que a visualização de dados existe e para quem ela foi projetada. |

{style="table-layout:auto"}

### Contêineres

Determina o nome dos containers para a visualização de dados. Os nomes dos containers são usados com frequência em [filtros](/help/components/filters/filters-overview.md#Filter-containers).

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Nome do container de pessoas] | [!UICONTROL Pessoa] (padrão). O container [!UICONTROL Pessoa] inclui todas as sessões e eventos de pessoas dentro do intervalo de tempo especificado. Se sua organização usar um termo diferente (por exemplo, &quot;Visitante&quot; ou &quot;Usuário&quot;), você poderá renomear o container aqui. |
| [!UICONTROL Nome do container da sessão] | [!UICONTROL Sessão] (padrão). O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica. Você pode renomear o container como &quot;Visita&quot; ou com qualquer outro termo que desejar. |
| [!UICONTROL Nome do container do evento] | [!UICONTROL Evento] (padrão). O container [!UICONTROL Evento] define eventos individuais em um conjunto de dados. Se sua organização usar um termo diferente (por exemplo, &quot;Ocorrências&quot; ou &quot;Exibições de página&quot;), você poderá renomear o container aqui. |

{style="table-layout:auto"}

### Calendário

Indica o formato de calendário que a visualização de dados deve seguir. Você pode ter várias visualizações de dados com base na mesma [Conexão](/help/connections/create-connection.md) e fornecer tipos de calendário ou fusos horários diferentes. Essas visualizações de dados podem permitir que equipes que usam diferentes tipos de calendário acomodem suas respectivas necessidades com os mesmos dados subjacentes.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Fuso horário] | Escolha em qual fuso horário você deseja que seus dados sejam apresentados. Se você escolher um fuso horário que funcione no Horário de verão, os dados serão automaticamente ajustados para refletir isso. Na primavera, quando os relógios se ajustam uma hora à frente, há um intervalo de uma hora. No outono, quando os relógios são atrasados em uma hora, uma hora é repetida durante o horário de verão. |
| [!UICONTROL Tipo de calendário] | Determine como as semanas do mês são agrupadas.<br>**Gregoriano:** formato de calendário padrão. Os trimestres são agrupados por mês.<br>**4-5-4 Varejo:** um calendário de varejo padronizado em 4-5-4. O primeiro e o último mês do trimestre contêm 4 semanas, enquanto o segundo mês do trimestre possui 5 semanas.<br>**Personalizado (4-5-4):** semelhante ao calendário 4-5-4, exceto que é possível escolher o primeiro dia do ano e o ano em que a semana “extra” ocorre.<br>**Personalizado (4-4-5):** o primeiro e o segundo mês de cada trimestre contêm 4 semanas, enquanto o último mês de cada trimestre possui 5 semanas.<br>**Personalizado (5-4-4):** O primeiro mês de cada trimestre consiste em 5 semanas, enquanto o segundo e o terceiro meses de cada trimestre consistem em 4 semanas. |
| [!UICONTROL Primeiro mês do ano] e [!UICONTROL Primeiro dia da semana] | Visível para o tipo de calendário gregoriano. Especifique em qual mês deseja que o ano civil comece e o dia em que cada semana inicia. |
| [!UICONTROL Primeiro dia do ano atual] | Visível para tipos de calendário personalizado. Especifique o dia do ano em que deseja que o ano atual comece. O calendário formata automaticamente o primeiro dia de cada semana com base nesse valor. |
| [!UICONTROL Ano em que a semana “extra” ocorre] | Na maioria dos calendários de 364 dias (52 semanas de 7 dias cada), cada ano acumula alguns dias até que uma semana extra seja formada. Essa semana extra é então adicionada ao último mês desse ano. Especifique em qual ano você deseja adicionar a semana extra. |

{style="table-layout:auto"}

## Componentes

Em seguida, você pode definir os componentes de uma visualização de dados, o que significa que é possível criar métricas e dimensões com base em elementos do esquema. Você também pode usar os componentes padrão.

>[!IMPORTANT]
>
>Até 5 mil métricas e 5 mil dimensões podem ser adicionadas a uma mesma visualização de dados.

1. Selecione a guia **[!UICONTROL Componentes]**.

   ![Guia Componentes](assets/dataview-components.png)

   Você pode ver a [!UICONTROL Conexão] no canto superior esquerdo, que contém os conjuntos de dados, e seus [!UICONTROL Campos de esquema] abaixo.  Os componentes já incluídos são componentes padrão (gerados pelo sistema) necessários para todas as visualizações de dados (como métricas de eventos, pessoas e sessões e dimensões de minuto, trimestre e semana). A Adobe também aplica o filtro **[!UICONTROL Contém dados]** e **[!UICONTROL não foi descontinuado]** por padrão, para que sejam exibidos apenas campos de esquema que contêm dados e não foram descontinuados.

1. Procure um campo de esquema usando a opção ![Ícone de pesquisa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Pesquisar campos de esquema]** ou localize um campo acessando qualquer uma das coleções de conjunto de dados, como ![Ícone de pasta](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Conjuntos de dados de evento]**.<br/>Como alternativa, é possível criar um campo derivado usando a opção ![Ícone de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Criar campo derivado** . Consulte [Campos derivados](./derived-fields/derived-fields.md) para obter mais informações.

1. Quando você encontrar o campo de esquema específico ou definir o campo derivado, arraste esse campo, como o ![Ícone de alça](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Nome da página]**, do painel esquerdo para a seção Métricas ou Dimensões.
Você pode arrastar o mesmo campo de esquema nas seções de dimensões ou métricas várias vezes e configurar a mesma dimensão ou métrica de maneiras diferentes. Por exemplo, no campo pageName, é possível criar uma dimensão chamada “Páginas de produto” e outra chamada “Páginas de erro”, usando diferentes [Configurações de componente](component-settings/overview.md) à direita.
Se você arrastar uma pasta de campo de esquema do painel esquerdo, elas serão classificadas automaticamente em seções típicas. Os campos de sequência de caracteres terminam na seção [!UICONTROL Dimensão] e os esquemas do tipo numérico terminam na seção [!UICONTROL Métricas]. Você também pode clicar em **[!UICONTROL Adicionar tudo]** e todos os campos de esquema serão adicionados aos seus respectivos locais.

1. Ao selecionar um componente, as configurações são exibidas no lado direito.

   ![Componente de visualização de dados selecionado](assets/dataview-component-pagename.png)

   Configure o componente usando [Configurações de componente](component-settings/overview.md). As configurações de componente disponíveis variam, dependendo se o componente é uma dimensão/métrica e do tipo de dados do esquema. As configurações incluem:

   * [[!UICONTROL Atribuição]](component-settings/attribution.md)
   * [[!UICONTROL Comportamento]](component-settings/behavior.md)
   * [[!UICONTROL Formato]](component-settings/format.md)
   * [[!UICONTROL Incluir/excluir valores]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Desduplicação de métrica]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Sem opções de valor]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistência]](component-settings/persistence.md)
   * [[!UICONTROL Classificação de valor]](component-settings/value-bucketing.md)

1. Selecione **[!UICONTROL Salvar e continuar]** para continuar configurando sua visualização de dados nova ou existente. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.

**Métricas ou dimensões duplicadas**

Duplicar métricas ou dimensões e depois modificar configurações específicas é uma maneira fácil de criar várias métricas ou dimensões a partir de um único campo de esquema. Selecione a configuração [!UICONTROL Duplicar] abaixo do nome da métrica ou das dimensões no canto superior direito. Modifique a nova métrica ou dimensão e salve-a com um nome mais descritivo.

**Filtrar campos ou conjuntos de dados de esquema**

Você pode filtrar ![Ícone de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) campos de esquema no painel esquerdo por [!UICONTROL tipo de dados], [!UICONTROL conjuntos de dados], [!UICONTROL governança de dados] e [!UICONTROL outros] critérios ([!UICONTROL contém dados], [!UICONTROL é uma identidade] e [!UICONTROL não foi descontinuado]):

![Filtrar campos](assets/dataview-components-filter.png)

>[!TIP]
>
>Se os componentes não forem carregados corretamente na visualização de dados e uma mensagem de erro aparecer, consulte [Falta de permissões](../troubleshooting/lack-of-permissions.md) para obter uma resolução.



## Configurações 

1. Selecione a guia **[!UICONTROL Configurações]**.
1. Configure filtros para aplicar a toda a visualização de dados. Consulte [Configurações (filtros)](#settings-filters) abaixo.
1. Configurar o tempo limite e as métricas da sessão. Consulte [Configurações da sessão](#session-settings) abaixo.
1. Selecione **[!UICONTROL Salvar e continuar]** para continuar configurando sua visualização de dados nova ou existente. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.

### Configurações (filtros)

É possível adicionar filtros que se aplicam a toda a visualização de dados. Esse filtro é aplicado a qualquer relatório executado no Espaço de trabalho. Arraste um filtro da lista no painel à esquerda para o campo [!UICONTROL Adicionar filtros].

### Configurações da sessão

Determine o período de inatividade entre eventos antes de uma sessão expirar e um novo ser iniciado. É necessário um período. Ou também é possível forçar o início de uma nova sessão quando um evento contém uma determinada métrica. Consulte [Configurações de sessão](session-settings.md) para obter mais detalhes.

Depois que todas as configurações desejadas forem especificadas, clique em **[!UICONTROL Salvar e concluir]**.
