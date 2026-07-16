---
title: Criar Ou Editar Uma Visualização De Dados
description: Saiba mais sobre todas as configurações que você pode definir ao criar ou editar uma visualização de dados.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
TQID: https://experienceleague.adobe.com/EXiKrWVfmMRgZ4GF0OR410Mr2-P5IEjPy3Hf0FmRDJ8
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044fid: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 28959f1ea858dee686e6d13025621c4a6164c319
workflow-type: tm+mt
source-wordcount: 3152
ht-degree: 74%

---

# Criar ou editar uma visualização de dados

A criação de uma visualização de dados envolve criar métricas e dimensões com base em elementos de esquema ou utilizar componentes padrão. A maioria dos elementos do esquema pode ser uma dimensão ou uma métrica, dependendo das necessidades da sua empresa. Depois de arrastar um elemento do esquema para uma visualização de dados, algumas opções serão exibidas à direita, onde você poderá ajustar como a dimensão ou métrica opera no Customer Journey Analytics.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Criar ou editar uma visualização de dados](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/data-views/overview-of-configuring-data-views-for-cja){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


Criar ou editar uma visualização de dados:

1. Faça logon no [Customer Journey Analytics](https://analytics.adobe.com) e selecione **[!UICONTROL Visualizações de dados]**, ou use a seção **[!UICONTROL Gerenciamento de dados]** no menu superior.
1. Para criar uma visualização de dados, selecione **[!UICONTROL Criar nova visualização de dados]**. Como alternativa, selecione uma visualização de dados existente na lista de visualizações de dados para editá-la.


## Configurar {#configure}

Para configurar uma visualização de dados nova ou existente:

![Configurar exibição de dados com a guia de contêineres separada](assets/data-view-configure-containers.png)



1. Selecione a guia **[!UICONTROL Configurar]** (se ainda não estiver ativa).
1. Especifique os detalhes de **[!UICONTROL Configurações]**, **[!UICONTROL Compatibilidade]**, **[!UICONTROL Configurações de IA]** e **[!UICONTROL Calendário]** (veja abaixo).
1. Selecione **[!UICONTROL Salvar e continuar]** para continuar configurando sua visualização de dados nova ou existente. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.


### Configurações {#configure-settings}

>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="ID externa"
>abstract="Alterar a ID externa afeta como o nome da visualização de dados aparece em fontes externas, como ferramentas de business intelligence."


Fornece configurações abrangentes para a visualização de dados.

| Configuração | Descrição |
| --- | --- |
| **[!UICONTROL Conexão]** | Esse campo vincula a visualização de dados à conexão estabelecida anteriormente, que contém um ou mais conjuntos de dados da Adobe Experience Platform. |
| **[!UICONTROL Nome]** | Obrigatório. O nome da visualização de dados. Este valor aparece no menu suspenso localizado no canto superior direito do Analysis Workspace. |
| **[!UICONTROL ID externa]** | Obrigatório. O nome da visualização de dados que você pode usar em fontes externas, como ferramentas de business intelligence. O padrão é `unspecified`. Se você não especificar uma ID externa, o nome será gerado a partir do Nome da visualização de dados, substituindo espaços por sublinhados. |
| **[!UICONTROL Descrição]** | Opcional. A Adobe recomenda uma descrição detalhada para que os usuários entendam por que a visualização de dados existe e para quem ela foi projetada. |

{style="table-layout:auto"}

### Compatibilidade {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Visualizações de dados no Journey Optimizer"
>abstract="O Customer Journey Analytics requer uma conexão e uma visualização de dados compatíveis com o Adobe Journey Optimizer. O sistema cria uma conexão e uma visualização de dados por padrão. Como alternativa, ative essa opção para definir essa como a visualização de dados padrão para relatórios do Adobe Journey Optimizer, que adiciona os componentes necessários à visualização de dados e aos conjuntos de dados à conexão."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/integrations/ajo#connection" text="Quais componentes e conjuntos de dados são adicionados."


Fornece as configurações aplicáveis ao usar o Adobe Journey Optimizer junto com o Customer Journey Analytics.

Esta seção é visível somente para admins provisionados com o Journey Optimizer.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL **Definir como visualização de dados padrão no Adobe Journey Optimizer**] | Essa opção de configuração padroniza os relatórios no Journey Optimizer e no Customer Journey Analytics. Também permite executar análises avançadas dos dados do Adobe Journey Optimizer no Customer Journey Analytics (selecionando as opções ![Abrir](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) e [!UICONTROL **Analisar no CJA**] no Journey Optimizer).<p>Para executar esse tipo de análise, o Journey Optimizer precisa acessar uma visualização de dados do Customer Journey Analytics.<p>Habilite esta opção para torná-la a visualização de dados padrão usada nos relatórios do Journey Optimizer da sandbox.</p><p>Essa opção de configuração automaticamente:</p><ul><li>Configura todos os conjuntos de dados do Journey Optimizer necessários na conexão associada no Customer Journey Analytics para uso com o Journey Optimizer.</li><li>Cria um conjunto de métricas e dimensões do Journey Optimizer na visualização de dados (incluindo campos derivados e métricas calculadas). Os rótulos de contexto são definidos automaticamente em todas essas métricas e dimensões.</li><li>Habilita automaticamente a opção de **[!UICONTROL Usar no CJA]** na conexão associada a esta visualização de dados. (Para saber mais sobre esta opção, consulte [Usar uma conexão com o Journey Optimizer no Customer Journey Analytics](/help/connections/manage-connections.md)).<p>Se essa configuração for desabilitada manualmente após ser habilitada, a conexão e quaisquer visualizações de dados associadas serão redefinidas para o estado padrão. Isso pode resultar em alterações nos dados dos seus relatórios.</p></li></ul><p><p>Considere o seguinte ao habilitar essa opção: <ul><li>É possível alterar a visualização de dados padrão posteriormente, mas isso pode alterar os dados dos relatórios do Journey Optimizer. Se optar por desabilitar essa opção posteriormente, será necessário selecionar uma nova visualização de dados padrão.</li><li>Se você já fez personalizações manuais nos conjuntos de dados, dimensões ou métricas na visualização de dados do Customer Journey Analytics, elas permanecerão intactas ao habilitar essa opção de configuração. Essa opção faz personalizações adicionais que padronizam ainda mais os relatórios no Journey Optimizer e no Customer Journey Analytics. Você também pode fazer personalizações manuais depois de habilitar essa opção.</li><li>Quando essa opção está selecionada, a conexão associada à visualização de dados não pode ser excluída.</li></ul>Consulte [Integrar o Adobe Journey Optimizer ao Adobe Customer Journey Analytics](/help/integrations/ajo.md) para obter mais informações. |

{style="table-layout:auto"}


### Configurações de IA

Selecione **[!UICONTROL Habilitar para o Data Insights Agent]** para habilitar a exibição de dados para o [Data Insights Agent](/help/data-analysis-ai.md). O Data Insights Agent é um agente de conversação de IA generativa acessível pelo Assistente de IA na Customer Journey Analytics. Ele ajuda a analisar os seus dados rapidamente com prompts de texto. O agente cria visualizações relevantes no Analysis Workspace usando componentes da visualização de dados e usando os dados reais.


### Calendário

Indica o formato de calendário que a visualização de dados deve seguir. Você pode ter várias visualizações de dados com base na mesma [Conexão](/help/connections/create-connection.md) e fornecer tipos de calendário ou fusos horários diferentes. Essas visualizações de dados podem permitir que equipes que usam diferentes tipos de calendário acomodem suas respectivas necessidades com os mesmos dados subjacentes.

| Configuração | Descrição |
| --- | --- |
| [!UICONTROL **Fuso horário**] | Escolha em qual fuso horário você deseja que seus dados sejam apresentados. Se você escolher um fuso horário que funcione no Horário de verão, os dados serão automaticamente ajustados para refletir isso. Na primavera, quando os relógios se ajustam uma hora à frente, há um intervalo de uma hora. No outono, quando os relógios são atrasados em uma hora, uma hora é repetida durante o horário de verão. |
| [!UICONTROL **Tipo de calendário**] | Determine como as semanas do mês são agrupadas.<br>**Gregoriano:** Formato de calendário padrão. Os trimestres são agrupados por mês.<br>**4-5-4 Varejo:** Um calendário de varejo padronizado em 4-5-4. O primeiro e o último mês do trimestre contêm 4 semanas, enquanto o segundo mês do trimestre possui 5 semanas.<br>**Personalizado (4-5-4):** semelhante ao calendário 4-5-4, exceto que é possível escolher o primeiro dia do ano e o ano em que a semana “extra” ocorre.<br>**Personalizado (4-4-5):** o primeiro e o segundo mês de cada trimestre contêm 4 semanas, enquanto o último mês de cada trimestre possui 5 semanas.<br>**Personalizado (5-4-4):** O primeiro mês de cada trimestre consiste em 5 semanas, enquanto o segundo e o terceiro meses de cada trimestre consistem em 4 semanas. |
| [!UICONTROL **Primeiro mês do ano**] e [!UICONTROL **Primeiro dia da semana**] | Visível para o tipo de calendário gregoriano. Especifique em qual mês deseja que o ano civil comece e o dia em que cada semana inicia. |
| [!UICONTROL **Primeiro dia do ano atual**] | Visível para tipos de calendário personalizado. Especifique o dia do ano em que deseja que o ano atual comece. O calendário formata automaticamente o primeiro dia de cada semana com base nesse valor. |
| [!UICONTROL **Ano em que a semana “extra” ocorre**] | Na maioria dos calendários de 364 dias (52 semanas de 7 dias cada), cada ano acumula alguns dias até que uma semana extra seja formada. Essa semana extra é então adicionada ao último mês desse ano. Especifique em qual ano você deseja adicionar a semana extra.<br><br/>**Semanas extras e anos bissextos**<br/> Quando você seleciona um **[!UICONTROL Tipo de calendário]** personalizado **[!UICONTROL Personalizado (4-5-4)]**, **[!UICONTROL Personalizado (4-4-5)]** ou **[!UICONTROL Personalizado (5-4-4)]**), os dias que sobram são acumulados a cada ano até totalizar uma semana extra completa (sete dias). Essa semana extra é adicionada ao ano selecionado em **[!UICONTROL Ano em que a semana “extra” ocorre]**.<br/><br/>Os anos bissextos não são mostrados intencionalmente no **[!UICONTROL Ano em que a semana “extra” ocorre]**. No entanto, um ano bissexto ainda pode conter 53 semanas. Para forçar um ano bissexto a conter 53 semanas, selecione um ano não bissexto em **[!UICONTROL Ano em que a semana “extra” ocorre]** para garantir que o desvio da data cumulativa adicione até sete dias ao ano bissexto alvejado. Por exemplo: para ter 53 semanas em 2024, selecione **[!UICONTROL 2019]**. De 2019 a 2024, o desvio total de datas é de 7 dias (2020 (+2), 2021 (+1), 2022 (+1), 2023 (+1) e 2024 (+2)), o que resulta em uma 53ª semana em 2024.<br/><br/>A seleção para **[!UICONTROL Primeiro dia do ano atual]** afeta onde a semana extra chega. Para confirmar a sua configuração, use a prévia do calendário. |

{style="table-layout:auto"}

## Containers

{{release-limited-testing-section}}


>[!BEGINTABS]

>[!TAB Padrão]

![Configurar visualização de dados](assets/data-view-containers-b2c.png)

>[!TAB B2B Edition]

![Configurar visualização de dados B2B](assets/data-view-containers-b2b.png)

>[!ENDTABS]

Na guia **[!UICONTROL Contêineres]**, é possível renomear contêineres do sistema e adicionar contêineres personalizados.

### Containers do sistema

Determina o nome dos containers para a visualização de dados. Os nomes dos containers são usados com frequência em [segmentos](/help/components/segments/seg-overview.md#containers).

| Nome do container | Nome de exibição (padrão) | Descrição |
| --- | --- | --- |
| globalAccount | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Conta Global ]** | O container [!UICONTROL Conta global] inclui todas as sessões e eventos para contas globais no intervalo de tempo especificado. Se sua organização usa um termo diferente, é possível renomear o container aqui. |
| pessoa | **[!UICONTROL Pessoa]** | O container [!UICONTROL Pessoa] inclui todas as sessões e eventos de pessoas dentro do intervalo de tempo especificado. Se sua organização usar um termo diferente (por exemplo, &quot;Visitante&quot; ou &quot;Usuário&quot;), você poderá renomear o container aqui. |
| session | **[!UICONTROL Sessão]** | O container [!UICONTROL Sessão] permite identificar as interações de página, campanhas ou conversões de uma sessão específica. Você pode renomear o container como &quot;Visita&quot; ou com qualquer outro termo que desejar. |
| oportunidade | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Oportunidade ]** | O container [!UICONTROL Oportunidade] inclui todas as sessões e eventos para oportunidades no intervalo de tempo especificado. Se sua organização usa um termo diferente, é possível renomear o container aqui. |
| purchaseGroup | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Grupo de compras ]** | O container [!UICONTROL Grupo de compra] inclui todas as sessões e eventos para grupos de compra no intervalo de tempo especificado. Se sua organização usa um termo diferente, é possível renomear o container aqui. |
| evento | **[!UICONTROL Evento]** | O container [!UICONTROL Evento] define eventos individuais em um conjunto de dados. Se sua organização usar um termo diferente (por exemplo, &quot;Ocorrências&quot; ou &quot;Exibições de página&quot;), você poderá renomear o container aqui. |
| account | [!BADGE Conta ]**]{type=Informative url="https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL B2B edition | O container [!UICONTROL Conta] inclui todas as sessões e eventos para contas no intervalo de tempo especificado. Se sua organização usa um termo diferente, é possível renomear o container aqui. |

Para renomear contêineres do sistema:

1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar o **[!UICONTROL Nome de exibição]** do contêiner.
1. Defina um novo nome para o container.
1. Selecione **[!UICONTROL Salvar]**.


### Containers personalizados

Você adiciona contêineres personalizados à sua visualização de dados para que possa usar esses contêineres para [análise de subevento](/help/components/segments/sub-event.md). Os contêineres personalizados podem ser definidos em:

* objetos ou matrizes disponíveis nos conjuntos de dados que fazem parte da conexão. Por exemplo, **[!UICONTROL productListItems]**, **[!UICONTROL content_assets]** ou **[!UICONTROL placeContext.ativePOIs]**.
* campos derivados que retornam uma matriz com o uso da função [Split](/help/data-views/derived-fields/derived-fields.md#split).
* componentes de exibição de dados configurados para retornar uma matriz usando as configurações de componente [Substring](/help/data-views/component-settings/substring.md) com a opção [Delimitador](/help/data-views/component-settings/substring.md#delimiter).

Para adicionar um contêiner personalizado:

1. Selecione **[!UICONTROL Adicionar contêiner personalizado]**.
1. No diálogo **[!UICONTROL Adicionar contêiner]**:
   1. Selecione um contêiner no menu suspenso **[!UICONTROL Contêiner]**. Por exemplo: **[!UICONTROL productListItems.productCategories]**. Após a seleção, você verá valores atualizados para **[!UICONTROL Caminho do esquema]** e **[!UICONTROL Tipo de esquema]**.

   1. Digite um **[!UICONTROL Nome de exibição]** para o contêiner. Por exemplo: `Product Categories`.
   1. Selecione **[!UICONTROL Salvar]**.

Para editar um contêiner personalizado:

1. Selecione ![Mais](/help/assets/icons/More.svg) para o contêiner personalizado na coluna **[!UICONTROL Nome de exibição]**.
1. Selecione ![Editar](/help/assets/icons/Edit.svg) **[!UICONTROL Editar]** no menu de contexto.
1. Na caixa de diálogo **[!UICONTROL Editar container]**:
   1. Modifique o **[!UICONTROL Contêiner]**, o **[!UICONTROL Nome de exibição]** ou ambos.
   1. Selecione **[!UICONTROL Salvar]**.

Para excluir um contêiner personalizado:

1. Selecione ![Mais](/help/assets/icons/More.svg) para o contêiner personalizado na coluna Nome para exibição.
1. Selecione ![Excluir](/help/assets/icons/Delete.svg) **[!UICONTROL Excluir]** no menu de contexto.

   >[!NOTE]
   >
   >O container personalizado é excluído sem confirmação.
   >

Para alterar a lista de contêineres personalizados:

1. Selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg).
1. Em **[!UICONTROL Personalizar tabela]**:
   1. Selecione as colunas a serem exibidas.
   1. Selecione **[!UICONTROL Salvar]**.


## Componentes

Em seguida, você pode definir os componentes de uma visualização de dados, o que significa que é possível criar métricas e dimensões com base em elementos do esquema. Você também pode usar os componentes padrão.

>[!IMPORTANT]
>
>Até 5 mil métricas e 5 mil dimensões podem ser adicionadas a uma mesma visualização de dados.

1. Selecione a guia **[!UICONTROL Componentes]**.

   ![Guia Componentes](assets/dataview-components.png)

   Você pode ver a [!UICONTROL Conexão] no canto superior esquerdo, que contém os conjuntos de dados, e seus [!UICONTROL Campos de esquema] abaixo.  Todas as visualizações de dados incluem componentes padrão como Eventos, Pessoas, Métricas de sessão e dimensões de tempo.<ul><li>Ao definir [contêineres personalizados](#containers-1), as métricas são adicionadas automaticamente como ![ShowAllLayer](/help/assets/icons/ShowAllLayer.svg) **[!UICONTROL _nome do contêiner personalizado _Ocorrências]**.</li><li>O sistema aplica o filtro **[!UICONTROL não está obsoleto]** por padrão, de modo que apenas os campos de Esquema não obsoletos são exibidos.</li></ul>

1. Procure um campo de esquema por meio do ![Ícone de pesquisa](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Procurar campos de esquema]** ou localize um campo por meio de qualquer uma das coleções de conjunto de dados, como ![Pasta](/help/assets/icons/Folder.svg) **[!UICONTROL Conjuntos de dados de evento]** ou ![Pasta](/help/assets/icons/Folder.svg) **[!UICONTROL Conjuntos de dados de pesquisa]**. Para conjuntos de dados de eventos, coleções separadas para ![Pasta](/help/assets/icons/Folder.svg) **[!UICONTROL campos XDM]** e ![Pasta](/help/assets/icons/Folder.svg) **[!UICONTROL campos relacionais e adhoc]** estão disponíveis.<br/>Como alternativa, você pode criar um campo derivado usando o ![ícone de Dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Criar campo derivado**. Consulte [Campos derivados](./derived-fields/derived-fields.md) para obter mais informações.

1. Quando tiver encontrado o campo de esquema específico ou definido o campo derivado, arraste esse campo, como ![Ícone de Identificador](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Nome da Página]**, do painel esquerdo para a seção **[!UICONTROL Métricas]** ou **[!UICONTROL Dimensões]** abaixo de **[!UICONTROL Componentes incluídos]**.
Você pode arrastar o mesmo campo de esquema nas seções de dimensões ou métricas várias vezes e configurar a mesma dimensão ou métrica de maneiras diferentes. Por exemplo, no campo pageName, crie `Product Pages` e `Error pages` dimensões usando diferentes [Configurações de componente](component-settings/overview.md) à direita.
Se você arrastar uma pasta de campos de esquema a partir do painel esquerdo, os campos contidos na pasta serão ordenados automaticamente nas seções correspondentes. Os campos de string terminam na seção [!UICONTROL Dimensão] e os esquemas do tipo numérico terminam na seção [!UICONTROL Métricas]. Você também pode clicar em **[!UICONTROL Adicionar tudo]**, e todos os campos de esquema são adicionados a seus respectivos locais.

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

### Métricas ou dimensões duplicadas

Duplicar métricas ou dimensões e depois modificar configurações específicas é uma maneira eficiente de criar várias métricas ou dimensões a partir de um único campo de esquema. Selecione a configuração [!UICONTROL Duplicar] abaixo do nome da métrica ou da dimensão no canto superior direito. Modifique a nova métrica ou dimensão e salve-a com um nome mais descritivo.

### Filtrar campos ou conjuntos de dados do esquema

Você pode filtrar ![Ícone de filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) campos de esquema no painel esquerdo por [!UICONTROL tipo de dados], [!UICONTROL conjuntos de dados], [!UICONTROL governança de dados] e [!UICONTROL outros] critérios ([!UICONTROL contém dados], [!UICONTROL é uma identidade] e [!UICONTROL não foi descontinuado]):

![Filtrar campos](assets/dataview-components-filter.png)

>[!TIP]
>
>Se os componentes não forem carregados corretamente na visualização de dados e você vir uma mensagem de erro, consulte [Falta de permissões](../troubleshooting/lack-of-permissions.md) para obter uma resolução.


### Componentes incluídos {#included-components}

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_custom"
>title="Rótulos personalizados"
>abstract="Além dos rótulos fornecidos pela Adobe, também é possível definir seus próprios rótulos personalizados para sua organização."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_contract"
>title="Rótulos de contrato"
>abstract="Os rótulos de contrato (C) são usados para categorizar dados que contêm obrigações contratuais ou estão relacionados às políticas de governança de dados da sua organização."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_identity"
>title="Rótulos de identidade"
>abstract="Os rótulos de identidade (I) são usados para categorizar dados que podem identificar ou permitir o contato com uma pessoa específica."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_sensitive"
>title="Rótulos sigilosos"
>abstract="Os rótulos sigilosos (S) são usados para categorizar dados que você e sua organização consideram sigilosos."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_partnerecosystem"
>title="Ecossistema de parceiros"
>abstract="Os rótulos do ecossistema de parceiros (P) são usados para categorizar dados compartilhados com terceiros parceiros."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_policies"
>title="Políticas"
>abstract="Para oferecer suporte à conformidade de dados, implemente as políticas de uso de dados. Essas políticas descrevem ações de marketing permitidas ou restritas em dados no Experience Platform. Os filtros de políticas aplicam a política habilitada à Visualização de dados."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_responsibleengagement"
>title="Rótulos de engajamento responsável"
>abstract="Os rótulos de engajamento responsável são usados para oferecer suporte ao engajamento responsável."
>additional-url="https://experienceleague.adobe.com/pt-br/docs/experience-platform/data-governance/labels/overview" text="Visão geral dos rótulos de uso de dados"


A seção **[!UICONTROL Componentes incluídos]** contém a lista de **[!UICONTROL Métricas]** e **[!UICONTROL Dimensões]** que você configura para a visualização de dados.

* Para pesquisar componentes, use ![Pesquisar](/help/assets/icons/Search.svg) **[!UICONTROL _Pesquisar componentes_]**.
* Para filtrar os componentes inclusos listados, selecione ![Filtro](/help/assets/icons/Filter.svg).

  ![Caixa de diálogo de filtro de componentes inclusos](assets/dataview_includedcomponents_filter.png)

  Na caixa de diálogo **[!UICONTROL Filtrar campo por]**, você pode filtrar as seguintes categorias:

   * **[!UICONTROL Tipo de dados]**: você pode selecionar um ou mais dos seguintes tipos de dados: [!UICONTROL String], [!UICONTROL Número inteiro], [!UICONTROL Curto], [!UICONTROL Booleano], [!UICONTROL Duplo], [!UICONTROL Byte], [!UICONTROL Longo], [!UICONTROL Data] ou [!UICONTROL Data/hora].
   * **[!UICONTROL Conjuntos de dados]**: selecione um ou mais conjuntos de dados.
   * **[!UICONTROL Governança de dados]**: selecione um ou mais rótulos das subcategorias [!UICONTROL Rótulos personalizados], [!UICONTROL Rótulos de contrato], [!UICONTROL Rótulos de identidade], [!UICONTROL Rótulos de sensibilidade], [!UICONTROL ecossistema de parceiros] ou [!UICONTROL Políticas].
   * **[!UICONTROL Outros]**: selecione uma ou mais das opções [!UICONTROL Contém dados], [!UICONTROL É identidade] ou [!UICONTROL Não foi descontinuado].

  Selecione **[!UICONTROL Aplicar]** para aplicar os filtros.



## Configurações {#dataview-settings}

1. Selecione a guia **[!UICONTROL Configurações]**.

   ![Configurações de visualização de dados](assets/dataview-settings.png)

1. Configure segmentos a serem aplicados a toda a visualização de dados. Consulte [Configurações (segmentos)](#settings-filters) abaixo.
1. Configurar o tempo-limite e as métricas da sessão. Consulte [Configurações da sessão](#session-settings) abaixo.

1. Selecione **[!UICONTROL Salvar e continuar]** para continuar configurando sua visualização de dados nova ou existente. Selecione **[!UICONTROL Salvar]** para salvar a configuração da visualização de dados existente.

### Configurações (segmentos) {#segment-settings}

Você pode adicionar segmentos a serem aplicados a toda a visualização de dados. Esse segmento é aplicado a qualquer relatório executado no Workspace. Arraste um filtro dos componentes no painel esquerdo até o campo **[!UICONTROL Adicionar segmentos]**.

### Configurações da sessão

Determine o período de inatividade entre eventos antes de uma sessão expirar e um novo ser iniciado. É necessário um período. Opcionalmente, é possível forçar o início de uma nova sessão quando um evento contém uma determinada métrica. Consulte [Configurações de sessão](session-settings.md) para obter mais detalhes.

### Pré-visualização de dados

A pré-visualização de dados compara (nos vários containers) os dados dessa visualização de dados com os dados da conexão. A porcentagem de pré-visualização é baseada no número total de conexões nos últimos 90 dias.

Se a visualização não estiver carregando, a conexão ainda estará sendo preenchida.

Depois que todas as configurações desejadas forem especificadas, clique em **[!UICONTROL Salvar e concluir]**.
