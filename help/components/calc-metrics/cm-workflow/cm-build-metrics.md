---
description: O Criador de métricas calculadas oferece uma tela para arrastar e soltar dimensões, métricas, filtros e funções a fim de criar métricas personalizadas com base em lógicas de hierarquia de container, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.
title: Criar métricas
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 1c5ea3f49d47ffd833404260e6c21bd1e64a2734
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 65%

---

# Criar métricas

O Customer Journey Analytics fornece uma tela para arrastar e soltar dimensões, métricas, filtros e funções a fim de criar métricas personalizadas com base na lógica, nas regras e nos operadores da hierarquia do container. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.

## Começar a criar uma métrica calculada

Você pode começar a criar uma métrica calculada de qualquer uma das seguintes maneiras:

* No Analysis Workspace, abra um projeto e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar métrica]**.
* No Analysis Workspace, abra um projeto e selecione a **Plus** ícone ao lado do [!UICONTROL **Métricas**] no painel esquerdo.
* Entrada [!DNL Customer Journey Analytics], vá para **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]** e selecione **[!UICONTROL + Adicionar]** na parte superior da página Métricas calculadas.

## Áreas do Construtor de métricas calculadas

A imagem a seguir e a tabela que a acompanha explicam algumas das principais áreas e recursos do Criador de métricas calculadas.

![](assets/cm_builder_ui.png)

| Campo | Descrição |
| --- | --- |
| Título | É obrigatório fornecer um nome para a métrica. Não é possível salvar a métrica sem um nome. |
| Descrição | Forneça uma descrição simples para mostrar sua utilização e diferenciá-la de métricas similares. <p>A descrição também será exibida em um relatório. É melhor NÃO colocar a fórmula na descrição; em vez disso, descreva quando ela deve ou não ser utilizada. (A fórmula é gerada conforme você cria a métrica, abaixo do cabeçalho Resumo. Como resultado, não é necessário adicionar a fórmula à descrição.) </p> |
| Formato | As opções incluem Decimal, Hora, Porcentagem e Moeda. |
| Casas decimais | Mostra quantas casas decimais serão exibidas no relatório. O número máximo de casas decimais que você pode especificar é 10. |
| Mostrar tendência para cima como... | A configuração de polaridade desta métrica mostra se o Analytics deve considerar uma tendência para cima na métrica como algo positivo (verde) ou negativo (vermelho). Como resultado, o gráfico do relatório será exibido em verde ou vermelho ao subir. |
| Moeda | A moeda base dessa visualização de dados. |
| Tags | Adicionar tags é uma boa maneira de organizar as métricas. Todos os usuários podem criar tags e aplicar uma ou mais tags a uma métrica. No entanto, você pode visualizar tags somente para seus filtros ou os compartilhados com você. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:<ul><li>**Nomes das equipes**, como Marketing social, Marketing móvel.</li><li>**Projetos** (tags de análise), como Análise de página de entrada.</li><li>**Categorias**, como Mulheres; Geografia.</li><li>**Fluxos de trabalho**, como Para ser aprovado; Preparado para (uma unidade de negócios específica)</li></ul> |
| Resumo | <p>A fórmula Resumo é atualizada sempre que a definição da métrica é alterada. Esta fórmula também é exibida no painel Métricas à esquerda, ao passar o mouse sobre uma métrica e clicar no botão <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> ícone. </p> |
| Definição | Aqui você pode arrastar métricas/métricas calculadas, filtros e/ou funções para criar a métrica calculada. <ul><li>Se você arrastar uma métrica calculada, ela expandirá automaticamente sua definição de métrica. </li> <li>Você pode aninhar definições em contêineres. No entanto, diferentemente dos contêineres de filtro, esses contêineres funcionam como uma expressão matemática e determinam a ordem das operações. </li> </ul> |
| Operador | Dividido por ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) é o operador padrão, além dos operadores +, - e x. |
| Visualização | Fornece uma leitura rápida sobre possíveis erros. A visualização abrange os últimos 90 dias. Esta é uma maneira de medir, ao menos de maneira inicial, se você selecionou os componentes certos para a sua métrica. Um resultado inesperado significa que você precisa analisar a definição da métrica novamente. |
| Compatibilidade do produto | Para qualquer métrica calculada criada no Customer Journey Analytics, esse valor é sempre listado como [!UICONTROL **Dados totalmente processados**]. As métricas calculadas só podem incluir dados de conjuntos de dados de eventos. |
| Adicionar | Para todos os tipos de métricas calculadas, é possível adicionar contêineres e números estáticos à definição. Para métricas calculadas avançadas, também é possível adicionar filtros e funções.<ul><li>Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Todo o conteúdo do contêiner será processado antes da próxima operação.</li><li>Arrastar um filtro para um container filtra tudo nesse container. (Somente métricas calculadas avançadas)</li><li>É possível empilhar vários filtros em um container.</li></ul> |
| Ícone de engrenagem (Tipo de métrica, Atribuição) | Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo de métrica e os modelos de atribuição. <!-- <p>**Note:** Consider the following when updating a component's attribution to a non-default attribution model:</p><ul><li>**When using the component in a report with *a single dimension*:** The component's attribution ignores the allocation model when a non-default attribution model is used.</li><li>**When using the component in a report with *multiple dimensions*:** The component's attribution retains the allocation model when a non-default attribution model is used.</li><li>Multiple dimensions are available only when [exporting data to the cloud](/help/analysis-workspace/export/export-cloud.md).</li></ul> --> <p>Para obter mais informações sobre alocação, consulte [Configurações do componente de Persistência](/help/data-views/component-settings/persistence.md).</p> |
| Ícone de adição (+) | Permite criar um novo componente, como um novo filtro (que leva você ao Construtor de filtros). |
| Pesquisar componentes | Essa barra de pesquisa permite procurar dimensões, métricas, filtros (somente métricas calculadas avançadas) e funções (somente métricas calculadas avançadas). |
| Lista de dimensões | Em vez de sair do Criador de métrica calculada para criar um filtro simples (no Criador de filtros), por exemplo &quot;Página = Página inicial&quot;, é possível arrastar para a Página e selecionar Página inicial diretamente do Criador de métrica calculada. Isso resulta em um fluxo de trabalho mais simplificado para a criação de métricas calculadas filtradas. |
| Lista de métricas | As métricas possuem 3 categorias:<ul><li>Métricas padrão</li><li>Métricas calculadas</li><li>Modelos de métricas - na parte inferior da lista.</li></ul>Ao passar o mouse sobre uma métrica, é possível ver o ícone Informações à direita. Clicar neste ícone fornece as seguintes informações:<ul><li>A fórmula de como é calculado.</li><li>Uma tendência prevista da métrica.</li><li>Um ícone de edição (lápis) na parte superior direita que direcionará você ao Criador de métricas calculadas, onde será possível editar essa métrica calculada.</li></ul> |
| Lista de filtros | (Somente métricas calculadas avançadas) Como administrador, esta lista mostra todos os filtros criados na sua empresa de logon. Caso seja um usuário não administrador, esta lista mostra os filtros que possui e os que são compartilhados com você. |
| Lista de funções | (Somente métricas calculadas avançadas) As funções estão divididas em duas listas: Básicas (usadas com mais frequência) e Avançadas. |
| Seletor de visualizações de dados | Esse seletor (na parte superior direita) permite alternar para uma visualização de dados diferente. |
