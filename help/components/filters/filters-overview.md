---
title: Visão geral dos filtros
description: Entenda para que os filtros são usados e como criar um filtro simples.
translation-type: tm+mt
source-git-commit: 74b99933fb1b599c829e11117c41235754c189b9
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 100%

---


# Visão geral dos filtros

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar filtros de público-alvo avançados e concentrados nos seus relatórios. Os filtros permitem identificar subconjuntos de visitantes de acordo com características ou interações de site. Os filtros são projetados como insights codificados de público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os filtros podem ser baseados em atributos (tipo de navegador, dispositivo, número de visitas, país, gênero), interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa), saídas e entradas (visitantes do Facebook, uma página de aterrissagem definida, domínio de referência), variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente) e outros critérios.

Você pode criar e salvar filtros no Construtor de filtros ou gerar filtros de uma visualização de Fallout (no Workspace). Além disso, filtros podem ser usados juntos como filtros empilhados.

>[!IMPORTANT]
>Filtros são conhecidos como “segmentos” no Adobe Analytics. Renomeamos os segmentos para filtros porque a Adobe Experience Platform tem [uma definição diferente de “segmento”](https://docs.adobe.com/content/help/pt-BR/experience-platform/segmentation/home.html).

A filtragem inclui o [Construtor de filtros](/help/components/filters/create-filters.md) para construir segmentos e executar um pré-teste, e o [Gerenciador de filtros](/help/components/filters/manage-filters.md) para coletar, marcar, aprovar, definir a segurança e compartilhar filtros na organização.

## Filtros sequenciais

Os filtros sequenciais permitem identificar visitantes de acordo com a navegação e visualização de página no site, o que fornece um filtro de ações e interações definidas. Os segmentos sequenciais ajudam você a identificar o que um visitante gosta e o que um visitante evita. Ao construir filtros sequenciais, o operador ENTÃO é usado para definir e organizar a navegação do visitante.

Exemplo:

![](assets/sequential_fil.png)

| Visita um | Visita dois | Visita três |
| --- | --- | --- |
| O visitante foi para a página de aterrissagem principal (A), excluiu a página da campanha (B) e, em seguida, visualizou a página do Produto (C). | O visitante novamente foi para a página de aterrissagem principal (A), excluiu a página da campanha (B) e, novamente, foi para a página do Produto (C), em seguida, foi para a nova página (D). | O visitante entrou e seguiu o mesmo caminho da primeira e segunda visita, em seguida, excluiu a página F para ir diretamente para a página de produto direcionada (G). |

## Filtrar contêineres

Os filtros são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de contêiner aninhado. Os contêineres aninhados permitem que você defina atributos de pessoa e ações com base em regras entre e nos contêineres.

>[!NOTE]
>O contêiner Pessoa era anteriormente conhecido como o contêiner Visitante. O contêiner Sessão era chamado de contêiner Visita, e o contêiner Evento costumava ser o contêiner Ocorrência.

Um filtro define as condições para filtrar um visitante de acordo com atributos ou interações no site. Para definir as condições em um filtro, você define regras para filtrar visitantes com base nas características de visitante e/ou nas características de navegação. Para detalhar ainda mais os dados do visitante, você pode filtrar com base em visitantes específicos e/ou ocorrências de visualização de página para cada visitante. O Construtor de filtros fornece uma arquitetura simples para construir esses subconjuntos e aplicar regras como contêineres Pessoa, Sessão ou Evento aninhados e hierárquicos.

A arquitetura de contêiner empregada no Construtor de filtros define Pessoa como o contêiner mais externo, contendo dados abrangentes específicos para visitantes em visitas e visualizações de página. Um contêiner Sessão aninhado permite definir regras para detalhar os dados do visitante com base em sessões e um contêiner Evento aninhado permite detalhar as informações do visitante com base em visualizações de página individuais. Cada contêiner permite informar o histórico do visitante, as interações detalhadas por sessões ou detalhar por eventos individuais.

### Contêiner pessoa

O contêiner Pessoa inclui cada visita e visualização de página de visitante em um período especificado. Um filtro no nível de Pessoa retorna a página que atende à condição, além de todas as páginas visualizadas pelo visitante (e somente restrita pelos intervalos de datas definidos). Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornarão visualizações de página em todas as visitas e permite que você gere uma análise multivisita. Consequentemente, o contêiner Pessoa é o mais suscetível às mudanças com base em intervalos de datas definidos. Os contêineres Pessoa podem incluir valores com base no histórico geral do visitante.

* Dias antes da primeira compra
* Página de entrada original
* Domínios de referência originais

### Contêiner sessão

O contêiner Sessão permite identificar as interações de página, campanhas ou conversões de uma sessão da específica. O contêiner Sessão é o mais usado porque capta comportamentos para a sessão de visita inteira depois que a regra é atendida e permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um segmento. Ele pode ajudá-lo a responder a estas perguntas:

* Quantos visitantes visualizaram a seção Notícias e Esportes na mesma sessão?
* Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os contêineres Sessão incluem valores de acordo com a ocorrência por visita:

* Número da sessão
* Página de entrada
* Frequência de Retorno
* Métricas de participação
* Métricas alocadas linearmente

### Contêiner evento

O contêiner Evento define quais eventos de página você deseja incluir ou excluir de um filtro. É o mais estrito dos contêineres disponível para permitir a identificação de cliques e visualizações de página específicos, nos quais a condição é verdadeira, o que lhe permite visualizar um único código de rastreamento, ou isolar um comportamento em uma seção específica do site. Você também pode desejar indicar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido é efetuado.

Os contêineres de evento contam com detalhamentos de página única com base em valores:

* Produtos
* Props de lista
* Dimensões de lista
* Dimensões de merchandising (no contexto de eventos)