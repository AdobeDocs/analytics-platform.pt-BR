---
title: Visão geral dos filtros
description: Entenda para quais filtros são usados e como criar um filtro simples.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Visão geral dos filtros

A Análise de jornada do cliente permite que você crie, gerencie, compartilhe e aplique filtros de público-alvo avançados e focados em seus relatórios. Os filtros permitem identificar subconjuntos de visitantes com base em características ou interações de site. Os filtros são projetados como insights codificados do público que você pode criar para suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os filtros podem ser baseados em atributos (tipo de navegador, dispositivo, número de visitas, país, gênero), interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa), saídas e entradas (visitantes do Facebook, uma página de aterrissagem definida, domínio de referência), variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente) e outros critérios.

Você pode criar e salvar filtros no Construtor de filtro ou gerar filtros de uma visualização de Fallout (no Workspace). Além disso, os filtros podem ser usados juntos como filtros empilhados.

>[!IMPORTANT]
Os filtros são conhecidos como &quot;segmentos&quot; no Adobe Analytics. Renomeamos segmentos para filtros porque a Adobe Experience Platform tem uma definição diferente de &quot;segmento&quot;. Um segmento no AEP se refere a...

Filtering includes the [Filter Builder](/help/components/filters/create-filters.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

## Filtros sequenciais

Os filtros sequenciais permitem identificar os visitantes com base na navegação e exibição de página no site, fornecendo um filtro de ações e interações definidas. Os segmentos sequenciais ajudam você a identificar o que um visitante gosta e o que um visitante evita. Ao criar filtros sequenciais, o operador ENTÃO é usado para definir e ordenar a navegação do visitante.

Exemplo:

![](assets/sequential_fil.png)

| Visita um | Visita dois | Visita três |
|---|---|---|
| O visitante foi para a página de aterrissagem principal (A), excluiu a página da campanha (B) e, em seguida, visualizou a página do Produto (C). | O visitante voltou para a página de aterrissagem principal (A), excluiu a página da campanha (B) e foi novamente para a página de Produto (C) e, em seguida, para uma nova página (D). | O visitante entrou e seguiu o mesmo caminho da primeira e segunda visitas, em seguida, excluiu a página F para ir diretamente para uma página de produto direcionada (G). |

## Filtrar contêineres

Os filtros são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de contêiner aninhado. Os contêineres aninhados permitem que você defina atributos e ações da pessoa com base em regras entre e dentro dos contêineres.

>[!NOTE]
>O contêiner Pessoa era conhecido anteriormente como contêiner de Visitante. O contêiner de Sessão era chamado de contêiner de Visita e o contêiner de Evento era usado como contêiner de Ocorrência.

Um Filtro define condições para filtrar um visitante com base em seus atributos ou interações com o site. Para definir as condições em um filtro, defina regras para filtrar os visitantes com base nas características do visitante e/ou nas características de navegação. Para detalhar ainda mais os dados do visitante, você pode filtrar com base em visitantes específicos e/ou ocorrências de visualização de página para cada visitante. O Construtor de filtro fornece uma arquitetura simples para criar esses subconjuntos e aplicar regras como contêineres aninhados e hierárquicos de Pessoa, Sessão ou Evento.

A arquitetura de contêiner empregada no Construtor de filtro define Pessoa como o contêiner mais externo, contendo dados abrangentes específicos para o visitante em visitas e exibições de página. Um contêiner aninhado de Sessão permite que você defina regras para detalhar os dados do visitante com base em sessões, e um contêiner aninhado de evento permite detalhar as informações do visitante com base em exibições de página individuais. Cada contêiner permite que você reporte o histórico de um visitante, as interações detalhadas por sessões ou detalhar eventos individuais.

### Contêiner de pessoa

O contêiner Pessoa inclui todas as visitas e visualizações de página para os visitantes dentro de um período especificado. Um filtro no nível da Pessoa retorna a página que atende à condição, além de todas as outras páginas visualizadas pelo visitante (e somente restritas por intervalos de datas definidos). Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornarão as exibições de página em todas as visitas e permitirão que você gere uma análise de várias visitas. Consequentemente, o contêiner Pessoa é o mais susceptível a alterações com base em intervalos de datas definidos.
Os contêineres da pessoa podem incluir valores com base no histórico geral do visitante:

* Dias Antes da Primeira Compra

* Página de entrada original

* Domínios de referência originais

### Contêiner de sessão

O contêiner Sessão permite identificar interações, campanhas ou conversões de página para uma sessão específica. O contêiner de Sessão é o mais usado porque captura comportamentos para toda a sessão de visita depois que a regra é cumprida e permite que você defina quais sessões deseja incluir ou excluir na criação e aplicação de um segmento. Ele pode ajudá-lo a responder a essas perguntas:

* Quantos visitantes visualizaram a seção Notícias e esportes na mesma sessão?

* Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os contêineres de sessão incluem valores com base na ocorrência por sessão:

* Número da sessão

* Página de entrada

* Frequência de Retorno

* Métricas de participação

* Métricas alocadas linearmente

### Contêiner de eventos

O contêiner de evento define quais eventos de página você deseja incluir ou excluir de um filtro. É o mais estrito dos contêineres disponível para permitir a identificação de cliques e visualizações de página específicos, nos quais a condição é verdadeira, o que lhe permite visualizar um único código de rastreamento, ou isolar um comportamento em uma seção específica do site. Você também pode desejar indicar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido é efetuado.

Contêineres de evento incluem valores com base em detalhamentos de página única:

* Produtos

* Propriedades de lista

* Dimensões da lista

* Dimensões de comercialização (no contexto de eventos)