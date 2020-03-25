---
title: Visão geral dos Filtros
description: Entenda para que filtros são usados e como criar um filtro simples.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Visão geral dos Filtros

A Análise de jornada do cliente permite que você crie, gerencie, compartilhe e aplique filtros de audiência avançados e focados em seus relatórios. Os Filtros permitem identificar subconjuntos de visitantes com base em características ou interações de site. Os Filtros são projetados como insights codificados de audiência que você pode criar para suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os Filtros podem ser baseados em atributos (tipo de navegador, dispositivo, número de visitas, país, gênero), interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa), saídas e entradas (visitantes do Facebook, uma landing page definida, domínio de referência), variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente) e outros critérios.

Você pode criar e salvar filtros no Construtor de filtro ou gerar filtros de uma visualização de Fallout (no Workspace). Além disso, filtros podem ser usados juntos como filtros empilhados.

>[!IMPORTANT]
Filtros são conhecidos como &quot;segmentos&quot; no Adobe Analytics. Renomeamos segmentos para filtros porque a Adobe Experience Platform tem uma definição diferente de &quot;segmento&quot;. Um segmento no AEP se refere a...

A filtragem inclui o Construtor [de](/help/components/filters/create-filters.md) filtros para construir filtros e executar um pré-teste, e o Gerenciador [de](/help/components/filters/manage-filters.md) filtros para coletar, marcar, aprovar, definir a segurança e compartilhar filtros em sua organização.

## filtros sequenciais

filtros sequenciais permitem identificar visitantes com base na navegação e na visualização de página no site, fornecendo um filtro de ações e interações definidas. Os segmentos sequenciais ajudam a identificar o que um visitante gosta e o que um visitante evita. Ao criar filtros sequenciais, o operador ENTÃO é usado para definir e ordenar a navegação do visitante.

Exemplo:

![](assets/sequential_fil.png)

| Visita um | Visita dois | Visita três |
|---|---|---|
| O visitante foi para a landing page principal (A), excluiu a página de campanha (B) e, em seguida, visualizou a página de Produto (C). | O visitante voltou para a landing page principal (A), excluiu a página de campanha (B) e voltou para a página de Produto (C) e, em seguida, para uma nova página (D). | O visitante entrou e seguiu o mesmo caminho da primeira e segunda visitas, depois excluiu a página F para ir diretamente para uma página de produto direcionada (G). |

## Filtrar container

Os Filtros são baseados em uma hierarquia de nível de Pessoa, Sessão e Evento usando um modelo de container aninhado. Os container aninhados permitem que você defina atributos e ações da pessoa com base em regras entre e dentro dos container.

>[!NOTE]
>O container Pessoa era anteriormente conhecido como o container do Visitante. O container Session era chamado de container Visita, e o container Evento costumava ser o container Ocorrência.

Um Filtro define condições para filtrar um visitante com base em seus atributos ou interações com o site. Para definir condições em um filtro, defina regras para filtrar visitantes com base nas características do visitante e/ou nas características de navegação. Para detalhar ainda mais os dados do visitante, você pode filtrar com base em visitas específicas e/ou ocorrências de visualização de página para cada visitante. O Construtor de filtro fornece uma arquitetura simples para criar esses subconjuntos e aplicar regras como container aninhados e hierárquicos, Pessoa, Sessão ou Evento.

A arquitetura de container empregada no Construtor de filtro define a Pessoa como o container mais externo, contendo dados abrangentes específicos para o visitante em visitas e visualizações de página. Um container de sessão aninhado permite que você defina regras para detalhar os dados do visitante com base em sessões, e um container de Evento aninhado permite detalhar as informações do visitante com base em visualizações de página individuais. Cada container permite que você informe o histórico de um visitante, as interações detalhadas por sessões ou detalhe eventos individuais.

### container pessoal

O container Pessoa inclui todas as visitas e visualizações de página para visitantes dentro de um período especificado. Um filtro no nível da Pessoa retorna a página que atende à condição, além de todas as outras páginas visualizadas pelo visitante (e somente restringidas por intervalos de datas definidos). Como o container mais amplamente definido, os relatórios gerados no nível do container Pessoa retornarão visualizações de página em todas as visitas e permitirão que você gere uma análise de várias visitas. Consequentemente, o container Pessoa é o mais susceptível a alterações com base em intervalos de datas definidos.
Os container da pessoa podem incluir valores com base no histórico geral do visitante:

* Dias Antes da Primeira Compra

* Página de Entrada Original

* Domínios de referência originais

### container da sessão

O container Session permite identificar interações de página, campanhas ou conversões para uma sessão específica. O container Session é o container mais usado porque captura comportamentos para toda a sessão de visita, uma vez que a regra é atendida, e permite que você defina quais sessões deseja incluir ou excluir na criação e aplicação de um segmento. Ele pode ajudá-lo a responder a essas perguntas:

* Quantos visitantes visualizaram a seção Notícias e Esportes na mesma sessão?

* Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os container de sessão incluem valores com base na ocorrência por sessão:

* Número da sessão

* Página de entrada

* Frequência de Retorno

* Métricas de participação

* Métricas alocadas linearmente

### container Evento

O container Evento define quais eventos de página você gostaria de incluir ou excluir de um filtro. É o mais restrito dos container disponíveis para permitir identificar cliques específicos e visualização de página onde uma condição é verdadeira, permitindo que você visualização um único código de rastreamento ou isole o comportamento em uma seção específica do site. Você também pode indicar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido é feito.

Os container de Eventos incluem valores com base em detalhamentos de página única:

* Produtos

* Propriedades de lista

* dimensões de Lista

* Dimensões de comercialização (no contexto de eventos)