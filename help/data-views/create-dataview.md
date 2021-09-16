---
title: Criar ou editar uma visualização de dados
description: Todas as configurações que você pode ajustar para criar ou editar uma visualização de dados.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 384679788d140a01a12e1c830b47099398a920b1
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 18%

---

# Criar ou editar uma visualização de dados

A criação de uma visualização de dados envolve a criação de métricas e dimensões com base em elementos de esquema ou a utilização de componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica dependendo das necessidades da sua empresa. Depois de arrastar um elemento de esquema para uma visualização de dados, as opções são exibidas à direita, onde você pode ajustar como a dimensão ou métrica opera no CJA.

## Configurar uma visualização de dados

1. Faça logon em [Customer Journey Analytics](https://analytics.adobe.com) e vá para a guia **[!UICONTROL Visualizações de dados]**.
2. Clique em **[!UICONTROL Adicionar]** para criar uma visualização de dados ou clique em uma visualização de dados existente para editá-la.

![Nova visualização de dados](assets/new-data-view.png)

### Configurações

Fornece configurações abrangentes para a visualização de dados.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Conexão] | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém um ou mais conjuntos de dados do Adobe Experience Platform. |
| [!UICONTROL Nome] | Obrigatório. O nome da visualização de dados. Esse valor aparece na lista suspensa superior direita do Analysis Workspace. |
| [!UICONTROL Descrição] | Opcional. O Adobe recomenda uma descrição detalhada para que os usuários entendam por que a visualização de dados existe e para quem ela foi projetada. |

### Contêineres

Designa o nome dos contêineres para a exibição de dados. Os nomes dos contêineres são frequentemente usados em [Filters](/help/components/filters/filters-overview.md#Filter-containers).

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Nome do container de pessoas] | [!UICONTROL Pessoa] (padrão). O contêiner [!UICONTROL Pessoa] inclui cada sessão e evento para visitantes dentro do período especificado. Se sua organização usar um termo diferente (por exemplo, &quot;Visitante&quot; ou &quot;Usuário&quot;), você poderá renomear o contêiner aqui. |
| [!UICONTROL Nome do container da sessão] | [!UICONTROL Sessão] (padrão). O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica. É possível renomear esse contêiner como &quot;Visita&quot; ou qualquer outro termo preferido pela organização. |
| [!UICONTROL Nome do container do evento] | [!UICONTROL Evento] (padrão). O contêiner [!UICONTROL Event] define eventos individuais em um conjunto de dados. Se sua organização usar um termo diferente (por exemplo, &quot;Ocorrências&quot; ou &quot;Exibições de página&quot;), você poderá renomear o contêiner aqui. |

### Calendário

Indica o formato de calendário que a visualização de dados deve seguir. Você pode ter várias visualizações de dados com base na mesma [Conexão](/help/connections/create-connection.md) e fornecer tipos de calendário ou fusos horários diferentes. Essas visualizações de dados podem permitir que equipes que usam diferentes tipos de calendário acomodem suas respectivas necessidades com os mesmos dados subjacentes.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL Fuso horário] | Escolha em qual fuso horário você deseja que seus dados sejam apresentados. Se você escolher um fuso horário que funcione no Horário de verão, os dados serão automaticamente ajustados para refletir isso. Na primavera, quando os relógios se ajustam uma hora à frente, há um intervalo de uma hora. Na queda em que os relógios se ajustam uma hora atrás, uma hora é repetida durante o deslocamento do horário de verão. |
| [!UICONTROL Tipo de calendário] | Determine como as semanas do mês são agrupadas.<br>**Gregoriano:** formato de calendário padrão. Os trimestres são agrupados por mês.<br>**4-5-4 Varejo:** um calendário de varejo padronizado 4-5-4. O primeiro e o último meses do trimestre contêm 4 semanas, enquanto o segundo mês do trimestre é constituído por 5 semanas.<br>**Personalizado (4-5-4):** Semelhante ao calendário 4-5-4, exceto que é possível escolher o primeiro dia do ano e o ano em que a semana &quot;extra&quot; ocorre.<br>**Personalizado (4-4-5):** o primeiro e o segundo meses de cada trimestre contêm 4 semanas, enquanto a última semana de cada trimestre consiste em 5 semanas.<br>**Personalizado (5-4-4):** O primeiro mês de cada trimestre consiste em 5 semanas, enquanto o segundo e o terceiro meses de cada trimestre consistem em 4 semanas. |
| [!UICONTROL Primeiro mês do ] ano e  [!UICONTROL Primeiro dia da semana] | Visível para o tipo de calendário gregoriano. Especifique em qual mês você deseja que o ano do calendário comece e em que dia você deseja que cada semana comece. |
| [!UICONTROL Primeiro dia do ano atual] | Visível para tipos de calendário personalizado. Especifique o dia do ano em que deseja que o ano atual comece. O calendário formata automaticamente o primeiro dia de cada semana com base nesse valor. |
| [!UICONTROL Ano em que a semana “extra” ocorre] | Com a maioria dos calendários de 364 dias (52 semanas de 7 dias cada), cada ano acumula dias restantes até formar uma semana extra. Essa semana extra é então adicionada ao último mês desse ano. Especifique em qual ano você deseja adicionar a semana extra. |

## Definir os componentes de uma visualização de dados

Em seguida, você pode criar métricas e dimensões com base em elementos do esquema. Você também pode usar os componentes padrão.

1. Faça logon em [Customer Journey Analytics](https://analytics.adobe.com) e vá para a guia **[!UICONTROL Visualizações de dados]**.
1. Clique em **[!UICONTROL Adicionar]** para criar uma visualização de dados ou clique em uma visualização de dados existente para editá-la.
1. Clique na guia **[!UICONTROL Componentes]**.

![Guia Componentes](assets/components-tab.png)

Você pode ver a [!UICONTROL Conexão] no canto superior esquerdo, que contém os conjuntos de dados, e seus [!UICONTROL Campos de esquema] abaixo. Lembre-se:

    * Os componentes já incluídos são os componentes obrigatórios padrão (gerados pelo sistema).
    * O Adobe aplica o filtro **[!UICONTROL Contém dados]** por padrão, para que apenas os campos Esquema que contêm dados sejam exibidos. Se estiver procurando um campo que não contém dados, remova o filtro.

1. Arraste um campo de esquema, como `pageTitle`, do painel esquerdo para a seção Métricas ou Dimension.

   Você pode arrastar o mesmo campo de esquema nas seções de dimensões ou métricas várias vezes e configurar a mesma dimensão ou métrica de maneiras diferentes. Por exemplo, no campo `pageTitle`, é possível criar uma dimensão chamada &quot;Páginas de produto&quot; e outra &quot;Páginas de erro&quot;, usando [Configurações de componente](component-settings/overview.md) diferentes à direita.

   ![Tabulação 3](assets/components-tab-3.png)

   Se você arrastar uma pasta de campo de esquema do painel esquerdo, elas serão classificadas automaticamente em seções típicas. Os campos de cadeia de caracteres terminam na seção [!UICONTROL Dimension] e os tipos de esquema numérico terminam na seção [!UICONTROL Metrics]. Você também pode clicar em **[!UICONTROL Add all]** e todos os campos de esquema são adicionados às respectivas localizações.

1. Depois de selecionar o componente, várias configurações são exibidas à direita. Configure o componente usando [Configurações do componente](component-settings/overview.md). As configurações de componente disponíveis dependem se o componente for uma dimensão/métrica e o tipo de dados do esquema. As configurações incluem:

   * [[!UICONTROL Atribuição]](component-settings/attribution.md)
   * [[!UICONTROL Comportamento]](component-settings/behavior.md)
   * [[!UICONTROL Formato]](component-settings/format.md)
   * [[!UICONTROL Incluir/excluir valores]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Desduplicação de métrica]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Sem opções de valor]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistência]](component-settings/persistence.md)
   * [[!UICONTROL Classificação de valor]](component-settings/value-bucketing.md)

Se necessário, você pode usar os seguintes recursos:

* **[!UICONTROL Duplicar]**: Duplicar métricas ou dimensões e depois modificar configurações específicas é uma maneira fácil de criar várias métricas ou dimensões a partir de um único campo de esquema. Selecione a configuração [!UICONTROL Duplicar] abaixo do nome da métrica ou das dimensões na parte superior direita. Modifique a nova dimensão ou métrica e salve-a com um nome mais descritivo.

   ![Duplicar](assets/duplicate.png)

* **[!UICONTROL Filtro]**: Você pode filtrar campos de esquema no painel esquerdo pelos seguintes tipos de dados:

   ![Filtrar campos](assets/filter-fields.png)

   Também é possível filtrar por conjuntos de dados e se um campo de esquema contém dados ou se é uma identidade. Por padrão, o Adobe aplica inicialmente o filtro **[!UICONTROL Contém dados]** a todas as visualizações de dados.

   ![Filtrar outros](assets/filter-other.png)

## Configurações

1. Faça logon em [Customer Journey Analytics](https://analytics.adobe.com) e vá para a guia **[!UICONTROL Visualizações de dados]**.
1. Clique em **[!UICONTROL Adicionar]** para criar uma visualização de dados ou clique em uma visualização de dados existente para editá-la.
1. Clique na guia **[!UICONTROL Settings]**.

### Filtro global

É possível adicionar filtros que se aplicam a uma visualização de dados inteira. Esse filtro é aplicado a qualquer relatório executado no Workspace. Arraste um filtro da lista no painel à esquerda para o campo [!UICONTROL Adicionar filtros].

### Configurações da sessão

Determine o período de inatividade entre eventos antes de uma sessão expirar e um novo ser iniciado.

É necessário um período de tempo. Opcionalmente, também é possível forçar o início de uma nova sessão quando um evento contiver uma determinada métrica.

Depois que todas as configurações desejadas forem especificadas, clique em **[!UICONTROL Salvar e concluir]**.
