---
description: O Criador de métricas calculadas oferece uma tela para arrastar e soltar Dimension, Métricas, Filtros e Funções para criar métricas personalizadas com base em lógicas de hierarquia de contêiner, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.
title: Criar métricas
source-git-commit: 92d9c3bd7478af5fbd4aca20fd814e2c9f2d6ef4
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 73%

---

# Criar métricas

O Criador de métricas calculadas oferece uma tela para arrastar e soltar Dimension, Métricas, Filtros e Funções para criar métricas personalizadas com base em lógicas de hierarquia de contêiner, regras e operadores. Essa ferramenta de desenvolvimento integrado permite criar e salvar métricas calculadas simples ou métricas calculadas avançadas complexas.

Há várias maneiras de acessar o Criador de métricas calculadas:

* Na Analysis Workspace, abra um projeto e clique em **[!UICONTROL + Novo]** > **[!UICONTROL Criar métrica]** .
* No [!DNL Analytics], vá para **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**.

* Clique em **[!UICONTROL + Adicionar]** na parte superior do [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md) ou

* Vá para **[!UICONTROL Analytics]** > **[!UICONTROL Relatórios]**, abra um relatório e clique no ícone Métricas ![](assets/metrics_icon.png) para mostrar o painel Métricas e clique em **[!UICONTROL Adicionar]**.

![](assets/cm_builder_ui.png)

## Componentes da interface do usuário {#ui-components}

| Campo | Descrição |
| --- | --- |
| Título | É obrigatório fornecer um nome para a métrica. Não é possível salvar a métrica sem um nome. |
| Descrição | Forneça uma descrição simples para mostrar sua utilização e diferenciá-la de métricas similares. A descrição também será exibida em um relatório. É melhor NÃO colocar a fórmula na descrição; em vez disso, descreva quando ela deve ou não ser utilizada. (A fórmula é gerada conforme você cria a métrica, abaixo do cabeçalho Resumo. Como resultado, não é necessário adicionar a fórmula à descrição.) |
| Formato | As opções incluem Decimal, Hora, Porcentagem e Moeda. |
| Casas decimais | Mostra quantas casas decimais serão exibidas no relatório. O número máximo de casas decimais que você pode especificar é 10. |
| Mostrar tendência para cima como... | A configuração de polaridade desta métrica mostra se o Analytics deve considerar uma tendência para cima na métrica como algo positivo (verde) ou negativo (vermelho). Como resultado, o gráfico do relatório será exibido em verde ou vermelho ao subir. |
| Moeda | A moeda base dessa visualização de dados. |
| Tags | Adicionar tags é uma boa maneira de organizar as métricas. Todos os usuários podem criar tags e aplicar uma ou mais tags a uma métrica. No entanto, você pode visualizar tags somente para seus segmentos ou os compartilhados com você. Que tipos de tags você deve criar? Estas são algumas sugestões para tags úteis:<ul><li>Tags com base em nomes de equipe, como Marketing social, Marketing móvel.</li><li>Tags de projeto (tags de análise), como análises de página de entrada.</li><li>Tags de categoria: masculino; geografia.</li><li>Tags de fluxo de trabalho: para ser aprovado; auxiliar para (uma unidade de negócios específica).</li></ul> |
| Resumo | A fórmula [!UICONTROL Resumo] é atualizada sempre que a definição da métrica é alterada. Esta fórmula também é exibida no painel Métricas à esquerda, ao passar o mouse sobre uma métrica e clicar no ícone . |
| Definição | É aqui que você arrasta métricas/métricas calculadas, filtros e/ou funções para criar a métrica calculada. Se você arrastar uma métrica calculada, ela expandirá automaticamente sua definição de métrica. Você pode aninhar definições em contêineres. Contudo, diferentemente dos contêineres de segmentos, esses contêineres funcionam como uma expressão matemática e determinam a ordem das operações. |
| Operador | [!UICONTROL Dividido por] é o operador padrão, além dos operadores +, - e x. |
| Visualização | Fornece uma leitura rápida sobre possíveis erros. A visualização abrange os últimos 90 dias. Esta é uma maneira de medir, ao menos de maneira inicial, se você selecionou os componentes certos para a sua métrica. Um resultado inesperado significa que você precisa analisar a definição da métrica novamente. |
| Adicionar | Para todos os tipos de métricas calculadas, é possível adicionar contêineres e números estáticos à definição. Para métricas calculadas avançadas, também é possível adicionar filtros e funções.<ul><li>Os contêineres funcionam como uma expressão matemática e determinam a ordem das operações. Todo o conteúdo do contêiner será processado antes da próxima operação.</li><li>Arrastar um segmento para um contêiner segmenta todo o conteúdo do mesmo. (Somente métricas calculadas avançadas)</li><li>Você pode empilhar vários filtros em um contêiner.</li></ul> |
| Ícone de engrenagem (Tipo de métrica,  Atribuição) | Selecionar o ícone de engrenagem ao lado de uma métrica permite especificar o tipo de métrica e os modelos de atribuição. |
| + Novo | Permite criar um novo componente, como um novo filtro (que leva você ao Construtor de filtros .) |
| Pesquisar componentes | Esta barra de pesquisa permite que você pesquise dimensões, métricas, segmentos (somente métricas calculadas avançadas) e funções (somente métricas calculadas avançadas). |
| Lista de dimensões | Em vez de sair do Criador de métricas calculadas para criar um filtro simples (no Construtor de filtros), por exemplo &quot;Página = Página inicial&quot;, você pode arrastar para a Página e selecionar Página inicial diretamente do Criador de métricas calculadas. Isso resulta em um fluxo de trabalho muito mais simplificado para a criação de métricas calculadas filtradas. |
| Lista de métricas | As métricas possuem 3 categorias:<ul><li>Métricas padrão</li><li>Métricas calculadas</li><li>Modelos de métricas - na parte inferior da lista.</li></ul>Ao passar o mouse sobre uma métrica, é possível ver o ícone Informações à direita. Clicar neste ícone fornece as seguintes informações:<ul><li>A fórmula de como é calculado.</li><li>Uma tendência prevista da métrica.</li><li>Um ícone para editar (lápis) localizado na parte superior direita que direciona você para o Criador de métricas calculadas, onde é possível editar a métrica calculada.</li></ul> |
| Lista de filtros | (Somente métricas calculadas avançadas) Como administrador, esta lista mostra todos os filtros criados na sua empresa de logon. Se você for um usuário não administrativo, esta lista mostra os filtros que possui e os compartilhados com você. |
| Lista de funções | (Somente métricas calculadas avançadas) As funções estão divididas em duas listas: Básicas (usadas com mais frequência) e Avançadas. |
| Seletor de visualizações de dados | Esse seletor (na parte superior direita) permite alternar para uma visualização de dados diferente. |

