---
title: Visão geral dos filtros
description: Entenda para que os filtros são usados e como criar um filtro simples.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 34%

---


# Visão geral dos filtros {#overview}

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar filtros de público-alvo avançados e concentrados nos seus relatórios. Os filtros permitem identificar subconjuntos de pessoas com base em características ou interações de site. Os filtros são projetados como insights codificados de público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os filtros podem ser baseados em

- atributos (tipo de navegador, dispositivo, número de visitas, país, gênero),
- interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa),
- saídas e entradas (pessoas do Facebook,
- uma página de aterrissagem definida, domínio de referência),
- variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente),
- e outros critérios.

Você pode criar e salvar filtros no Construtor de filtros ou gerar filtros de uma visualização de Fallout (no Espaço de trabalho). Além disso, filtros podem ser usados juntos como filtros empilhados.

A filtragem inclui o [Construtor de filtros](/help/components/filters/filter-builder.md) para construir segmentos e executar um pré-teste, e o [Gerenciador de filtros](/help/components/filters/manage-filters.md) para coletar, marcar, aprovar, definir a segurança e compartilhar filtros na organização.

O número máximo de filtros que podem ser criados por organização IMS é 50.000.

## Tipos de filtro {#types}

Para obter informações sobre os tipos de filtros disponíveis e como criá-los, consulte [Criar filtros](/help/components/filters/create-filters.md).

## Filtros sequenciais {#sequential}

Os filtros sequenciais permitem identificar pessoas com base na navegação e na exibição de página no site, fornecendo um filtro de ações e interações definidas. Os filtros sequenciais ajudam você a identificar do que uma pessoa gosta e o que ela evita. Ao construir filtros sequenciais, o operador THEN é usado para definir e organizar a navegação da pessoa.

Veja um exemplo:

<!--![](assets/sequential_fil.png)-->

| Sessão um | Sessão dois | Sessão três |
| --- | --- | --- |
| A pessoa foi para a página inicial principal A, excluiu a página B da campanha e, em seguida, visualizou a página C do produto. | A pessoa novamente foi para a página inicial principal A, excluiu a página B da campanha e, novamente, foi para a página C do produto e, em seguida, foi para a nova página D. | A pessoa entrou e seguiu o mesmo caminho da primeira e segunda visita, em seguida, excluiu a página F para ir diretamente para a página de produto direcionada G. |

## Filtrar contêineres {#containers}

Os filtros são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de container aninhado. Os contêineres aninhados permitem que você defina atributos de pessoa e ações com base em regras entre e nos contêineres.


<table style="table-layout: fixed; border: none;">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Pessoa</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Sessão</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Evento </td>
</tr>
</table>

>[!NOTE]
>O contêiner Pessoa era anteriormente conhecido como o contêiner Visitante. O contêiner Sessão era chamado de contêiner Visita, e o contêiner Evento costumava ser o contêiner Ocorrência.

Um filtro define as condições para filtrar uma pessoa com base nos atributos ou interações dessa pessoa com seu site. Para definir condições em um filtro, você define regras para filtrar pessoas com base nas características de pessoa e/ou nas características de navegação. Para detalhar ainda mais os dados da pessoa, você pode filtrar com base em visitas específicas e/ou ocorrências de exibição de página para cada pessoa. O Construtor de filtros fornece uma arquitetura simples para construir esses subconjuntos e aplicar regras como contêineres Pessoa, Sessão ou Evento aninhados e hierárquicos.

A arquitetura de contêiner empregada no Construtor de filtros define Pessoa como o contêiner mais externo, contendo dados abrangentes específicos para a pessoa entre visitas e visualizações de página. Um contêiner Sessão aninhado permite definir regras para detalhar os dados da pessoa com base em sessões, e um contêiner Evento aninhado permite detalhar as informações da pessoa com base em visualizações de página individuais. Cada contêiner permite que você informe o histórico de uma pessoa, as interações detalhadas por sessões ou detalhar por eventos individuais.

### Contêiner pessoa {#person}

O container Pessoa inclui cada visita e exibição de página de pessoas em um intervalo de tempo especificado. Um filtro no nível de Pessoa retorna a página que atende à condição, além de todas as outras páginas visualizadas pela pessoa (e somente restrita pelos intervalos de datas definidos). Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornam exibições de página em todas as visitas e permite que você gere uma análise de várias visitas. Portanto, o contêiner Pessoa é o mais susceptível às alterações com base em intervalos de datas definidos.
Os contêineres Pessoa podem incluir valores com base no histórico geral de uma pessoa:

- Dias antes da primeira compra
- Página de entrada original
- Domínios de referência originais

### Contêiner sessão {#session}

O contêiner Sessão permite identificar as interações de página, campanhas ou conversões de uma sessão da específica. O contêiner Sessão é o mais usado porque capta comportamentos para a sessão de visita inteira depois que a regra é atendida. O container Sessão também permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um filtro. Ele pode ajudá-lo a responder às seguintes perguntas:

- Quantas sessões se envolveram com fontes de dados da Web e do Call Center?
- Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os contêineres Sessão incluem valores de acordo com a ocorrência por visita:

- Tipo de sessão
- Página de entrada
- Frequência de Retorno
- Métricas de participação
- Métricas alocadas linearmente

### Contêiner evento {#event}

O container Evento define quais eventos de página você deseja incluir ou excluir de um filtro. É o mais estreito dos contêineres disponíveis para permitir que você identifique cliques específicos e exibições de página em que uma condição é verdadeira. O container Evento permite visualizar um único código de rastreamento ou isolar o comportamento em uma seção específica do site. Você também pode desejar indicar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido é efetuado.

Os contêineres de evento contam com detalhamentos de página única com base em valores:

- Produtos
- Props de lista
- Dimensões de lista
- Dimensões de merchandising (no contexto de eventos)

## Modelo de filtro pronto para uso {#template}

O Analytics tradicional vem com vários modelos de filtros (filtros) e métricas calculadas prontos para uso. Muitos deles não se aplicam ao Customer Journey Analytics ou precisam ser renomeados ou recriados. Outros dependem de uma solução para variáveis com reconhecimento de contexto no Customer Journey Analytics.

| Nome do filtro | Descrição |
| --- | --- |
| Todos os dados | Todos os dados é um filtro necessário que é adicionado dinamicamente aos relatórios quando uma métrica é adicionada à linha de uma tabela de forma livre. |
