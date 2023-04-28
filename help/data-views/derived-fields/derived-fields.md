---
title: Campos derivados
description: Um campo derivado especifica a manipulação em tempo de relatório de campos de esquema e/ou componentes padrão por meio de um conjunto de funções e modelos de função disponíveis.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
source-git-commit: 35a1a93a43869abab6e53ffb1d02edb5fad9a0c1
workflow-type: tm+mt
source-wordcount: '3062'
ht-degree: 9%

---


# Campos derivados

{{release-limited-testing}}

Os campos derivados são um aspecto importante da funcionalidade de relatório em tempo real no Customer Journey Analytics (CJA). Um campo derivado (personalizado) permite definir (geralmente complexo) manipulações de dados dinamicamente, por meio de um construtor de regras personalizável. Em seguida, você pode usar esse campo derivado como um componente (métrica ou dimensão) no [Workspace](../../analysis-workspace/home.md) ou ainda defina mais como um componente em [Exibição de dados](../data-views.md).

Campos derivados podem economizar uma quantidade significativa de tempo e esforço, em comparação com a transformação ou manipulação de seus dados em outros locais fora do CJA. Tal como [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=pt-BR), [Distiller de dados](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)ou em seus próprios processos de Extrair carga de transformação (ETL)/Extrair transformação de carga (ELT).

Os campos derivados são definidos como campos personalizados dentro de [Visualizações de dados](../data-views.md), são baseadas em um conjunto de funções definidas como regras e aplicadas aos campos padrão e/ou de esquema disponíveis.

Os casos de uso de exemplo são:

- Defina um campo de Nome de página personalizado que corrija valores de nome de página coletados inadequados para corrigir valores de nome de página.

- Defina um campo de Canal de marketing personalizado que determine o canal de marketing apropriado com base em uma ou mais condições (por exemplo, parâmetro de URL, URL da página, nome da página).

## Interface de campo personalizada

Ao criar ou editar um campo personalizado, use a interface de campo personalizado.

![Caixa de diálogo Campo personalizado](assets/custom-field-dialog.png)


|  | Nome | Descrição |
|---------|----------|--------|
| 1 | **Seletor** | Use a área do seletor para selecionar, arrastar e soltar ![Função](assets/Smock_Function_18_N.svg) ,![Ícone do modelo de função](assets/Smock_FileTemplate_18_N.svg) template de função,![Ícone do campo Esquema](assets/Smock_Folder_18_N.svg) campo de esquema ou![Ícone de campo padrão](assets/Smock_DragHandle_18_N.svg)campo padrão no construtor de regras. <br/>Use o menu suspenso para selecionar entre [!UICONTROL Funções], [!UICONTROL Modelos de funções], [!UICONTROL Campos de esquema]e [!UICONTROL Campos padrão].<br/>Você pode pesquisar por função, templates de função, schema e campos padrão usando a variável ![Ícone de Pesquisa](assets/Smock_Search_18_N.svg) Caixa de pesquisa. <br/>Você pode filtrar a lista de objetos selecionados ao selecionar ![Ícone Filtro](assets/Smock_Filter_18_N.svg) Filtre e especifique filtros na [!UICONTROL Filtrar campos por] caixa de diálogo. Você pode remover filtros facilmente usando ![Ícone Fechar](assets/CrossSize75.svg) para cada filtro. |
| 2 | **Construtor de regras** | Você cria seu campo personalizado sequencialmente usando uma ou mais regras. Uma regra é uma implementação específica de uma função e, portanto, sempre está associada a apenas uma função. Você cria uma regra arrastando e soltando uma função no Construtor de regras. O tipo de função determina a interface da regra.<br/>Consulte a [Interface de regras](#rule-interface) para obter mais informações. <br/>É possível inserir uma função no início, no fim ou entre as regras já disponíveis no Construtor de regras. A última regra no Construtor de regras determina a saída final do campo personalizado. |
| 3 | **[!UICONTROL ** Configurações de campo **]** | É possível nomear e descrever o campo personalizado e inspecionar o tipo de campo. |
| 4 | **[!UICONTROL ** Saída final **]** | Essa área mostra uma pré-visualização atualizada dos valores de saída, com base nos dados dos últimos 30 dias e nas alterações feitas no campo personalizado no construtor de regras. |

{style="table-layout:auto"}

Ao acessar a interface do campo Personalizado pela primeira vez, a variável [!UICONTROL Começar com um modelo de campo] assistente é exibido.

![Caixa de diálogo do assistente do modelo de campo personalizado](assets/field-template-dialog.png)

1. Selecione o template que melhor descreve o tipo de campo que você está tentando criar.
2. Selecione o **[!UICONTROL ** Selecionar **]** para continuar.

A caixa de diálogo Campo personalizado é preenchida com regras (e funções) necessárias ou úteis para o tipo de campo selecionado. Consulte [Modelos de funções](#function-templates) para obter mais informações sobre os modelos disponíveis.

## Interface de regras

Ao definir uma regra no construtor de regras, use a interface de regras.

![Interface da regra](assets/rule-interface.png)

|  | Nome | Descrição |
|---------|----------|--------|
| A | **Nome da regra** | Por padrão, o nome da regra é **Regra X** (X referindo-se a um número de sequência). Para editar o nome de uma regra, selecione seu nome e digite o novo nome, por exemplo `Query Parameter`. |
| B | **Nome da função** | O nome da função selecionada para a regra, por exemplo [!DNL URL PARSE]. Quando a função é a última na sequência de funções e determina os valores finais de saída, o nome da função é seguido por [!DNL FINAL OUTPUT], por exemplo [!DNL URL PARSE - FINAL OUTPUT]. <br/>Para mostrar um pop-up com mais informações sobre a função , selecione ![Ícone da Ajuda](assets/Smock_HelpOutline_18_N.svg). |
| C | **Descrição da regra** | Opcionalmente, é possível adicionar uma descrição a uma regra.<br/>Selecionar ![Ícone Mais](assets/More.svg), em seguida selecione **[!UICONTROL ** Adicionar descrição **]** para adicionar uma descrição ou **[!UICONTROL ** Editar descrição **]** para editar uma descrição existente.<br/>Use o editor para inserir uma descrição. Use a barra de ferramentas para formatar o texto (usando o seletor de estilos, negrito, itálico, sublinhado, direita, esquerda, centralizado, cor, lista de números, lista de marcadores) e adicionar links às informações externas. <br/>Para concluir a edição da descrição, clique fora do editor. |
| D | **Área de função** | Define a lógica da função. A interface depende do tipo de função. Consulte [Referência de função](#function-reference) em informações detalhadas para cada uma das funções suportadas. |

{style="table-layout:auto"}

## Criar um campo personalizado

1. Selecione uma Exibição de dados existente ou crie uma Exibição de dados. Consulte [Visualizações de dados](../data-views.md) para obter mais informações.

2. Selecione o **[!UICONTROL ** Componentes **]** da exibição de Dados.

3. Selecionar **[!UICONTROL ** Criar campo personalizado **]** no painel esquerdo.

4. Para definir seu campo personalizado, use a variável [!UICONTROL Criar campo personalizado] interface. Consulte [Interface de campo personalizada](#custom-field-interface).

   Para salvar o novo campo personalizado, selecione **[!UICONTROL ** Salvar **]**.

5. O novo campo personalizado é adicionado ao **[!UICONTROL ** Campos personalizados >**]** contêiner, como parte de **[!UICONTROL ** Campos de esquema **]** no painel à esquerda da visualização de dados.


## Editar um campo personalizado

1. Selecione uma visualização de Dados existente. Consulte [Visualizações de dados](../data-views.md) para obter mais informações.

2. Selecione o **[!UICONTROL ** Componentes **]** da exibição de Dados.

3. Selecionar **[!UICONTROL ** Campos de esquema **]** na guia no [!UICONTROL Conexão] painel à esquerda.

4. Selecionar **[!UICONTROL ** Campos personalizados >**]** contêiner.

5. Passe o mouse sobre o campo personalizado que deseja editar e selecione ![Ícone Editar](assets/Smock_Edit_18_N.svg).

6. Para editar seu campo personalizado, use o [!UICONTROL Editar campo personalizado] interface. Consulte [Interface de campo personalizada](#custom-field-interface).

   - Selecionar **[!UICONTROL ** Salvar **]** para salvar o campo personalizado atualizado.

   - Selecionar **[!UICONTROL ** Cancelar **]** para cancelar qualquer alteração feita no campo personalizado.

   - Selecionar **[!UICONTROL ** Salvar como **]** para salvar o campo personalizado como um novo campo personalizado. O novo campo personalizado tem o mesmo nome do campo personalizado editado original com `(copy)` adicionado a ele.

## Excluir um campo personalizado

1. Selecione uma visualização de Dados existente. Consulte [Visualizações de dados](../data-views.md) para obter mais informações.

2. Selecione o **[!UICONTROL ** Componentes **]** da exibição de Dados.

3. Selecionar **[!UICONTROL ** Campos de esquema **]** em [!UICONTROL Conexão] painel.

4. Selecionar **[!UICONTROL ** Campos personalizados >**]** contêiner.

5. Passe o mouse sobre o campo personalizado que deseja excluir e selecione ![Ícone Editar](assets/Smock_Edit_18_N.svg).

6. Em Uso **[!UICONTROL ** Editar campo personalizado **]** selecione Excluir.

   A [!UICONTROL Excluir componente] solicita que você confirme a exclusão. Considere qualquer referência externa que possa existir ao campo personalizado fora da exibição Dados.

   - Selecionar **[!UICONTROL ** Continuar **]** para excluir o campo personalizado.


## Modelos de função

Para criar rapidamente um campo personalizado para casos de uso específicos, os modelos de função estão disponíveis. Esses templates de função podem ser acessados na área Seletor na interface do campo Personalizado ou são apresentados após o primeiro uso na [!UICONTROL Começar com um modelo de campo] assistente.


### Canais de marketing

Este modelo está configurado para usar a variável [Análise De Url](#dnl-url-parse) e [Caso Quando](#dnl-case-when) O funciona várias vezes para obter valores apropriados de um URL. A lógica é aplicada nesses valores para associar o URL a um canal de marketing específico.

+++ Detalhes

Para usar o modelo, é necessário especificar os parâmetros corretos para cada função listada como parte das regras no modelo. Consulte [Referência de função](#function-reference) para obter mais informações.

![Construtor de regras de modelo de canal de marketing](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Referência de função

Para cada função suportada, localize os detalhes abaixo:

- entradas, operadores e saídas

- casos de utilização, incluindo:
   - dados antes de definir o campo personalizado
   - como definir o campo personalizado
   - dados após definir o campo personalizado


<!-- Concatenate -->

### [!DNL Concatenate]

Combina dois ou mais campos, campos personalizados ou valores inseridos pelo usuário em um único campo com delimitadores definidos.

+++ Detalhes

## Entradas/operadores/saídas {#concatenate-io}

| Tipo de dados de entrada | Entrada | Operadores incluídos | Saída |
|---|---|---|---|
| <p>Sequência de caracteres</p> | <ul><li>Dois ou mais valores para combinar<ul><li>Campos</li><li>Valor derivado de uma regra anterior</li><li>Valor inserido pelo usuário</li></ul></li><li>Delimitadores<ul><li>Entrada ou seleção de um delimitador para cada valor</li></ul></li> </ul> | <p>N/D</p> | <p>Novo campo personalizado</p> |

{style="table-layout:auto"}


## Caso de uso {#concatenate-uc}

Atualmente, você coleta códigos de origem e de destino do aeroporto como campos separados. Você gostaria de pegar os dois campos e combiná-los em uma única dimensão separada por um hífen (-). Assim, você pode analisar a combinação de origem e destino para identificar as principais rotas reservadas.

Pressupostos:

- Os valores de origem e destino são coletados em campos separados na mesma tabela.
- O usuário determina o uso do delimitador &#39;-&#39; entre os valores.

Imagine que as seguintes reservas ocorram:

- Cliente ABC123 registra voo entre Salt Lake City (SLC) e Orlando (MCO)
- Cliente ABC456 registra um voo entre Salt Lake City (SLC) e Los Angeles (LAX)
- O Cliente ABC789 registra um voo entre Salt Lake City (SLC) e Seattle (SEA)
- Cliente ABC987 registra voo entre Salt Lake City (SLC) e San Jose (SJO)
- Cliente ABC654 registra voo entre Salt Lake City (SLC) e Orlando (MCO)

O relatório desejado deve ter a seguinte aparência:

| Origem/Destino | Reservas |
|---|---|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Dados anteriores {#concatenate-uc-databefore}

| Origem | Destino |
|----|----|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Campo personalizado {#concatenate-customfield}

Você define um novo **[!UICONTROL ** Origem - Destino **]** campo personalizado. Você usa a variável **[!UICONTROL CONCATENADO]** para definir uma regra para concatenar a variável [!UICONTROL Original] e [!UICONTROL Destino] campos que usam `-` [!UICONTROL Delimitador].

![[!DNL Concatenate] regra](assets/concatenate.png)

### Dados após {#concatenate-dataafter}

| Origem - Destino<br/>(campo personalizado) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

Aplica condições, com base em critérios definidos de um ou mais campos. Esses critérios são usados para definir os valores em um novo campo personalizado, com base na sequência das condições.

+++ Detalhes

## Entradas/operadores/saídas {#casewhen-io}

| Tipo de dados de entrada | Entrada | Operadores incluídos | Saída |
|---|---|---|---|
| <ul><li>Sequência de caracteres</li><li>Numérico</li><li>Data/Hora</li></ul> | <ul><li>Campos de entrada</li><li>Critérios</li></ul> | <p><u>Strings</u></p><ul><li>Igual a</li><li>Igual a qualquer termo</li><li>Contém a frase</li><li>Contém qualquer termo</li><li>Contém todos os termos</li><li>Começa com</li><li>Começa com qualquer termo</li><li>Termina com</li><li>Termina com qualquer termo</li><li>Não é igual</li><li>Não é igual a nenhum termo</li><li>Não contém a frase</li><li>Não contém nenhum termo</li><li>Não contém todos os termos</li><li>Não começa com</li><li>Não inicia com nenhum termo</li><li>Não termina com</li><li>Não termina com nenhum termo</li><li>Está definido</li><li>Não está definido</li></ul><p><u>Numérico</u></p><ul><li>Igual a</li><li>Não é igual</li><li>É maior que</li><li>É maior que ou igual a</li><li>É menor que</li><li>É menor que ou igual a</li><li>Está definido</li><li>Não está definido</li></ul><p><u>Datas</u></p><ul><li>Igual a</li><li>Não é igual</li><li>É posterior a</li><li>É posterior ou igual a</li><li>É antes</li><li>É anterior ou igual a</li><li>Está definido</li><li>Não está definido</li></ul> | <p>Novo campo personalizado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#casewhen-uc1}

Você deseja definir regras para identificar vários canais de marketing, aplicando lógica em cascata para definir um campo de canal de marketing para o valor correto:

- Se o referenciador for de um mecanismo de pesquisa e a página tiver um valor de string de consulta, onde `cid` contém `ps_`, o canal de marketing deve ser identificado como um **Pesquisa paga**.
- Se o referenciador for de um mecanismo de pesquisa e a página não tiver a string de consulta `cid`, o canal de marketing deve ser identificado como um **Pesquisa natural**.
- Se uma página tiver um valor de sequência de consulta em que `cid` contém `em_`, o canal de marketing deve ser identificado como um **Email**.
- Se uma página tiver um valor de sequência de consulta em que `cid` contém `ds_`, o canal de marketing deve ser identificado como um **Exibir anúncio**.
- Se uma página tiver um valor de sequência de consulta em que `cid` contém `so_`, o canal de marketing deve ser identificado como um **Social pago**.
- Se o referenciador for de um domínio de referência de twitter.com, facebook.com, linkedin.com ou tiktok.com, o canal de marketing deve ser identificado como um **Social natural**.
- Se nenhuma das regras acima for correspondida, o canal de marketing deverá ser identificado como **Outro referenciador**.

Caso seu site receba os seguintes eventos de exemplo, contendo Referenciador e URL da página, esses eventos devem ser identificados da seguinte maneira:

| Evento  | Referenciador | URL da página | Canal de marketing |
|:----:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | Social natural |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | Exibir |
| 3 |  | `https://site.com/?cid=em_12345678` | Email |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | Pesquisa paga |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | Email |
| 6 | `https://google.com` |  | Pesquisa natural |

{style="table-layout:auto"}

### Dados anteriores {#casewhen-uc1-databefore}

| Referenciador | URL da página |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### Campo personalizado {#casewhen-uc1-customfield}

Você define um novo `Marketing Channel` campo personalizado. Você usa a variável **[!UICONTROL CASO QUANDO]** para definir regras que criem valores para a com base em valores existentes para a variável `Page URL` e `Referring URL` campo.

Observe o uso da função **[!UICONTROL ** ANÁLISE DE URL **]** para definir regras para buscar os valores de `Page Url` e `Referring Url` antes da **[!UICONTROL ** CASO QUANDO **]** são aplicadas.

![[!DNL Case when] regra 1](assets/case-when-1.png)

### Dados após {#casewhen-uc1-dataafter}

| Canal de marketing |
|----|
| Social natural |
| Exibir |
| Email |
| Pesquisa paga |
| Email |
| Pesquisa natural |

{style="table-layout:auto"}


## Caso de uso 2 {#casewhen-uc2}

Você coletou várias variações diferentes da pesquisa na dimensão Métodos de descoberta de produto . Para entender o desempenho geral da pesquisa e navegação, você deve passar muito tempo combinando os resultados manualmente.

Seu site coleta os seguintes valores para sua dimensão Métodos de descoberta de produto . No final, todos esses valores indicam uma pesquisa.

| Valor coletado | Valor real |
|---|---|
| pesquisar p13n_no | pesquisa |
| search p13n_yes | pesquisa |
| search refine p13n_no | pesquisa |
| search refine p13n_yes | pesquisa |
| search redirect p13n_yes | pesquisa |
| redirecionamento de pesquisa | pesquisa |

{style="table-layout:auto"}


### Dados anteriores {#casewhen-uc2-databefore}

| Métodos para encontrar produtos |
|----|
| search p13_no |
| search p13_yes |
| navegar |
| search refine p13_no |
| search refine p13_yes |
| navegar |
| search redirect p13_yes |
| redirecionamento de pesquisa |
| navegar |

{style="table-layout:auto"}

### Campo personalizado {#casewhen-uc2-customfield}

Você define uma `Product Finding Methods (new)` campo personalizado. Você cria o seguinte **[!UICONTROL ** CASO QUANDO **]** no Construtor de regras. Essas regras aplicam a lógica a todas as possíveis variações do antigo **[!UICONTROL ** Métodos para encontrar produtos **]** valores de campo para `search` e `browse` usando o **[!UICONTROL Contém a frase]** critério.

![[!DNL Case When] regra 2](assets/case-when-2.png)

### Dados após {#casewhen-uc2-dataafter}

| Métodos para encontrar produtos (novo) |
|----|
| pesquisa |
| pesquisa |
| navegar |
| pesquisa |
| pesquisa |
| navegar |
| pesquisa |
| pesquisa |
| navegar |

{style="table-layout:auto"}


## Caso de uso 3 {#casewhen-uc3}

Como companhia de viagens, você gostaria de agrupar a duração da viagem para viagens reservadas, de modo que possa relatar os períodos de viagem.

Pressupostos:

- A organização está coletando a duração do percurso em um campo numérico.
- Eles gostariam de agrupar durações de 1 a 3 dias em um balde chamado &quot;curta viagem&quot;
- Eles gostariam de agrupar durações de 4 a 7 dias em um balde chamado &quot;percurso médio&quot;
- Eles gostariam de agrupar durações de mais de 8 dias em um balde chamado &quot;longa viagem&quot;
- 132 viagens foram reservadas por um período de 1 dia
- 110 viagens foram reservadas por um período de 2 dias
- 105 viagens foram reservadas por um período de três dias
- 99 viagens foram reservadas por um período de 4 dias
- 92 viagens foram reservadas por um período de cinco dias
- 85 viagens foram reservadas por um período de 6 dias
- 82 viagens foram reservadas por um período de 7 dias
- 78 viagens foram reservadas por um período de 8 dias
- 50 viagens foram reservadas por um período de 9 dias
- 44 viagens foram reservadas por um período de 10 dias
- 38 viagens foram reservadas por um período de 11 dias
- 31 viagens foram reservadas por um período de 12 dias

Seu relatório desejado deve ser semelhante a:

| Tipo de duração da viagem | Reservas |
|----|---:|
| trajeto médio | 358 |
| curta viagem | 347 |
| longa viagem | 241 |

{style="table-layout:auto"}

### Dados anteriores {#casewhen-uc3-databefore}

| Duração do Percurso |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

{style="table-layout:auto"}

### Campo personalizado {#casewhen-uc3-customfield}

Você define uma `Trip Duration (bucketed)` campo personalizado. Você cria o seguinte **[!UICONTROL ** CASO QUANDO **]** no Construtor de regras. Essa regra aplica a lógica para agrupar o antigo **[!UICONTROL ** Duração do Percurso **]** valores de campo em três valores: `short trip`, `medium  trip`e `long trip`.

![[!DNL Case When] artigo 3º](assets/case-when-3.png)


### Dados após {#casewhen-uc3-dataafter}

| Duração do Percurso (Classificada) |
|---|
| curta viagem |
| longa viagem |
| curta viagem |
| trajeto médio |
| trajeto médio |
| longa viagem |
| trajeto médio |
| curta viagem |
| curta viagem |
| curta viagem |
| longa viagem |
| longa viagem |

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

Encontra todos os valores em um campo selecionado e substitui esses valores por um valor diferente em um novo campo personalizado.

+++ Detalhes

## Entradas/operadores/saídas {#findreplace-io}

| Tipo de dados de entrada | Entrada | Operadores incluídos | Saída |
|---|---|---|---|
| <p>Sequência de caracteres</p> | <ul><li><span>Critérios do campo &quot;Quando substituir&quot;</span></li><li><span>Valor do campo &quot;Substituir por&quot;</span><ul><li><span>Digitado pelo usuário</span></li><li><span>Campo separado</span></li></ul></li></ul> | <p><u>Strings</u></p><ul><li>Localizar tudo e substituir tudo</li></ul> | <p>Novo campo personalizado</p> |

{style="table-layout:auto"}


## Caso de uso {#findreplace-uc}

Você recebeu alguns valores malformados para seu relatório de canais de marketing externos, por exemplo `email%20 marketing` em vez de `email marketing`. Esses valores malformados fracionam seu relatório e dificultam a visualização do desempenho do email. Você deseja substituir `email%20marketing` com `email marketing`.

**Relatório original**

| Canais de marketing externos | Sessões |
|---|---|
| marketing por email | 500 |
| email%20marketing | 24 |

{style="table-layout:auto"}

**Relatório preferencial**

| Canais de marketing externos | Sessões |
|---|---|
| marketing por email | 524 |


### Dados anteriores {#findreplace-uc-databefore}

| Marketing externo |
|----|
| marketing por email |
| email%20marketing |
| marketing por email |
| marketing por email |
| email%20marketing |

{style="table-layout:auto"}

### Campo personalizado {#findreplace-uc-customfield}

Você define uma `Email Marketing (updated)` campo personalizado. Você usa a variável **[!UICONTROL LOCALIZAR E SUBSTITUIR]** para definir uma regra para localizar e substituir todas as ocorrências de `email%20marketing` com `email marketing`.

![[!DNL Find and Replace] regra](assets/find-and-replace.png)

### Dados após {#findreplace-uc-dataafter}

| Marketing externo<br/>(campo personalizado) |
|----|
| marketing por email |
| marketing por email |
| marketing por email |
| marketing por email |
| marketing por email |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

Define um conjunto de valores de pesquisa que são substituídos pelos valores correspondentes.

+++ Detalhes


## Entradas/operadores/saídas {#lookup-io}

| Tipo de dados de entrada | Entrada | Operadores incluídos | Saída |
|---|---|---|---|
| <ul><li>Sequência de caracteres</li><li>Numérico</li><li>Data</li></ul> | <ul><li>Campo de sing</li><li>Arquivo de pesquisa<ul><li>Coluna-chave</li><li>Nova Coluna de Campo</li></ul></li></ul> | <p>N/D</p> | <p>Novo campo personalizado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#lookup-uc1}

Você tem um arquivo CSV que inclui uma coluna-chave para `hotelID` e uma ou mais colunas adicionais associadas à função `hotelID`: `city`, `rooms`, `hotel name`.
Você está coletando ID de hotel em uma dimensão, mas gostaria de criar uma dimensão de Nome de hotel derivada do `hotelID` no arquivo CSV.

**Estrutura e conteúdo do arquivo CSV**

| hotelID | city | salas | nome do hotel |
|---|---|---:|---|
| SLC123 | Salt Lake City | 40 | Centro SLC |
| LAX342 | Los Angels | 60 | Aeroporto de LA |
| SFO456 | São Francisco | 75 | Rua do mercado |

{style="table-layout:auto"}

**Relatório atual**

| ID do hotel | Visualizações de produto |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}


**Relatório desejado**

| Nome do hotel | Visualizações de produto |
|----|----:|
| Centro SLC | 200 |
| Aeroporto de LA | 198 |
| Rua do mercado | 190 |

{style="table-layout:auto"}

### Dados anteriores {#lookup-uc1-databefore}

| ID do hotel |
|----|
| SLC123 |
| LAX342 |
| SFO456 |

{style="table-layout:auto"}


### Campo personalizado {#lookup-uc1-customfield}

Você define uma `Hotel Name` campo personalizado. Você usa a variável **[!UICONTROL ** PESQUISA **]** para definir uma regra na qual você possa pesquisar valores da variável **[!UICONTROL ** ID do hotel **]** e substitua por novos valores.

![[!DNL Lookup] regra 1](assets/lookup-1.png)

### Dados após {#lookup-uc1-dataafter}

| Nome do hotel |
|----|
| Centro SLC |
| Aeroporto de LA |
| Rua do mercado |

{style="table-layout:auto"}


## Caso de uso 2 {#lookup-uc2}

Você coletou URLs em vez do nome amigável da página para várias páginas. Essa coleção mista de valores quebra o relatório.

### Dados anteriores {#lookup-uc2-databefore}

| Nome da página |
|---|
| Página inicial |
| Pesquisa de voo |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| Ofertas e contratos |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Campo personalizado {#lookup-uc2-customfield}

Você define uma `Page Name (updated)` campo personalizado. Você usa a variável **[!UICONTROL ** PESQUISA **]** para definir uma regra na qual você possa pesquisar valores de seus **[!UICONTROL ** Nome da página **]** e substitua por valores corretos atualizados.

![[!DNL Lookup] regra 2](assets/lookup-2.png)

### Dados após {#lookup-uc2-dataafter}

| Nome da página (atualizado) |
|---|
| Página inicial |
| Pesquisa de voo |
| Pesquisa de hotel |
| Pesquisa de pacotes |
| Ofertas e contratos |
| Resenhas |
| Gerar Cotação |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

Analisa diferentes partes de um URL, incluindo protocolo, host, caminho ou parâmetros de consulta.

+++ Detalhes

## Entradas/operadores/saídas {#urlparse-io}

| Tipo de dados de entrada | Entrada | Operadores incluídos | Saída |
|---|---|---|---|
| <ul><li>Sequência de caracteres</li></ul> | <ul><li>Campo de sing</li><li>Opção de análise<ul><li>Obter protocolo</li><li>Obter host</li><li>Obter caminho</li><li>Obter valor de consulta<ul><li>Parâmetro de consulta</li></ul></li><li>Obter valor de hash</li></ul></li></ul></li></ul> | <p>N/D</p> | <p>Novo campo personalizado</p> |

{style="table-layout:auto"}


## Caso de uso 1 {#urlparse-uc1}

Você deseja usar somente o domínio de referência do URL de referência como parte do conjunto de regras de um canal de marketing.

### Dados anteriores {#urlparse-uc1-databefore}

| URL de referência |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Campo personalizado {#urlparse-uc1-customfield}

Você define uma  `Referring Domain` campo personalizado. Você usa a variável **[!UICONTROL ** ANÁLISE DE URL **]** para definir uma regra para buscar o host do **URL de referência** e armazene no novo campo personalizado.

![[!DNL Url Parse] regra 1](assets/url-parse-1.png)

### Dados após {#urlparse-uc1-dataafter}

| Domínio de referência |
|----|
| www.google.com |
| duckduckgo.com |
| t.co |
| l.facebook.com |

{style="table-layout:auto"}


## Caso de uso 2 {#urlparse-uc2}

Você deseja usar o valor da variável `cid` de uma string de consulta em um URL de página como parte da saída de um relatório de código de rastreamento derivado.

### Dados anteriores {#urlparse-uc2-databefore}

| URL da página |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Campo personalizado {#urlparse-uc2-customfield}

Você define uma `Query String CID` campo personalizado. Você usa a variável **[!UICONTROL ** ANÁLISE DE URL **]** para definir uma regra para buscar o valor do parâmetro da string de consulta no URL da página, especificando `cid` como parâmetro de consulta. O valor de saída é armazenado no novo campo personalizado.

![[!DNL Url Parse] regra 2](assets/url-parse-2.png)

### Dados após {#urlparse-uc2-dataafter}

| CID da string de consulta |
|----|
| abc123 |
| def123 |
| xyz123 |

{style="table-layout:auto"}

+++
