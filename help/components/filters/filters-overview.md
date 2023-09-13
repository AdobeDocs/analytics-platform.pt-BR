---
title: Visão geral dos filtros
description: Entenda para que os filtros são usados e como criar um filtro simples.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
source-git-commit: 8d681a956cc826642e8fc22081acd2c579543b2e
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 26%

---


# Visão geral dos filtros {#overview}

O Customer Journey Analytics permite criar, gerenciar, compartilhar e aplicar filtros de público-alvo avançados e concentrados nos seus relatórios. Os filtros permitem identificar subconjuntos de pessoas com base em características ou interações. Os filtros são projetados como insights codificados de público-alvo que você pode criar de acordo com suas necessidades específicas e, em seguida, verificar, editar e compartilhar com outros membros da equipe.

Os filtros podem ser baseados em

- atributos (tipo de navegador, dispositivo, número de visitas, país, gênero),
- interações (campanhas, pesquisa por palavra-chave, mecanismo de pesquisa),
- saídas e entradas (pessoas do Facebook, uma página inicial definida, domínio de referência, evento de geofence),
- variáveis personalizadas (campo de formulário, categorias definidas, ID do cliente),
- e outros critérios.

Você pode criar e salvar filtros no Construtor de filtros ou gerar filtros de uma visualização de Fallout (no Espaço de trabalho). Além disso, filtros podem ser usados juntos como filtros empilhados.

A filtragem inclui o [Construtor de filtros](/help/components/filters/filter-builder.md) para construir segmentos e executar um pré-teste, e o [Gerenciador de filtros](/help/components/filters/manage-filters.md) para coletar, marcar, aprovar, definir a segurança e compartilhar filtros na organização.

O número máximo de filtros que podem ser criados por organização IMS é 50.000.

## Tipos de filtro {#types}

Para obter informações sobre os tipos de filtros disponíveis e como criá-los, consulte [Criar filtros](/help/components/filters/create-filters.md).

## Filtros sequenciais {#sequential}

Os filtros sequenciais permitem identificar as pessoas com base na navegação (exibições de página no site, interações com cenas no aplicativo móvel ou uso de um menu em um decodificador de sinais). Os filtros sequenciais fornecem um filtro de ações e interações definidas e ajudam a identificar do que uma pessoa gosta e o que ela evita. Ao construir filtros sequenciais, o operador THEN é usado para definir e organizar a navegação da pessoa.

>[!IMPORTANT]
>
>Você deve ter o **Selecionar** pacote para criar filtros sequenciais entre canais. Entre em contato com o administrador se não tiver certeza do pacote de Customer Journey Analytics que possui.

Veja um exemplo:

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

Um filtro define as condições para filtrar uma pessoa com base nos atributos ou interações dela com seu site, aplicativo móvel ou outro tipo de dispositivo do qual você coletou dados. Para definir condições em um filtro, você define regras para filtrar pessoas com base nas características de pessoa e/ou nas características de navegação. Para detalhar ainda mais os dados da pessoa, você pode filtrar com base em visitas específicas e/ou ocorrências de exibição de página, toques na tela, opções de menu em um decodificador de sinais para cada pessoa. Mas também filtre os atributos que você assimilou de um CRM ou sistema de fidelidade. O Construtor de filtros fornece uma arquitetura simples para construir esses subconjuntos e aplicar regras como contêineres Pessoa, Sessão ou Evento aninhados e hierárquicos.

A arquitetura de contêiner empregada no Construtor de filtros define Pessoa como o contêiner mais externo. O container contém dados abrangentes específicos para a pessoa em visitas e visualizações de página, telas de aplicativos móveis ou telas de menu em um decodificador de sinais. Um contêiner Sessão aninhado permite definir regras para detalhar os dados da pessoa com base em sessões, e um contêiner Evento aninhado permite detalhar as informações da pessoa com base em interações individuais. Cada contêiner permite informar o histórico de uma pessoa, as interações detalhadas por sessões ou detalhar por eventos de experiência individuais.

### Contêiner pessoa {#person}

O contêiner Pessoa inclui cada visita e visualização de página, tela de aplicativo móvel, decodificador de sinais ou interação entre jogos de console para pessoas em um intervalo de tempo especificado. Basicamente, todos os eventos de experiência que fazem parte dos conjuntos de dados definidos na conexão Customer Journey Analytics. Um filtro no nível de Pessoa retorna as exibições de página, o aplicativo móvel ou as telas do decodificador de sinais que atendem à condição. Além de todas as outras interações da mesma pessoa entre canais online e offline (e somente restritas por intervalos de datas definidos). Como o contêiner mais amplamente definido, os relatórios gerados no nível do contêiner Pessoa retornam exibições de página, telas de aplicativos móveis e muito mais, em todas as visitas, e permite gerar uma análise entre canais de várias visitas. Portanto, o contêiner Pessoa é o mais susceptível às alterações com base em intervalos de datas definidos.
Os contêineres Pessoa podem incluir valores com base no histórico geral de uma pessoa:

- Dias antes da primeira compra
- Página de entrada original ou tela inicial do aplicativo móvel
- Domínios de referência originais

### Contêiner sessão {#session}

O contêiner Sessão permite identificar as interações de página ou as interações, campanhas ou conversões do aplicativo móvel de uma sessão específica. O contêiner Sessão é o mais usado porque capta comportamentos para a sessão de visita inteira depois que a regra é atendida. O container Sessão também permite definir quais sessões você deseja incluir ou excluir na criação e aplicação de um filtro. Ele pode ajudá-lo a responder às seguintes perguntas:

- Quantas sessões se envolveram com fontes de dados da Web e do Call Center?
- Quais páginas contribuíram para uma conversão bem-sucedida em uma venda?

Os contêineres Sessão incluem valores de acordo com a ocorrência por visita:

- Tipo de sessão
- Página de entrada
- Frequência de Retorno
- Métricas de participação
- Métricas alocadas linearmente

As visualizações de dados no Customer Journey Analytics permitem determinar a duração de uma sessão, mas também quando uma nova sessão deve ser criada. Por exemplo, você pode definir uma nova sessão de aplicativo móvel com base em toda vez que um usuário iniciar seu aplicativo móvel. Consulte [Configurações de sessão](/help/data-views/session-settings.md) para obter mais informações.

### Contêiner evento {#event}

O container Evento define qual página, aplicativo móvel ou outro tipo de evento você deseja incluir ou excluir de um filtro. É o mais estreito dos contêineres disponíveis para permitir a identificação de cliques específicos, exibição de página, toques no botão em um aplicativo móvel onde uma condição é verdadeira. O container Evento permite visualizar um único código de rastreamento ou isolar o comportamento em uma área específica do aplicativo móvel. Você também pode desejar indicar um valor específico quando uma ação ocorre, como o canal de marketing quando um pedido é efetuado.

Os contêineres Evento incluem detalhamentos de página única com base em valor para:

- Produtos
- Props de lista
- Dimensões de lista
- Dimensões de merchandising (no contexto de eventos)

## Modelo de filtro pronto para uso {#template}

O Analytics tradicional vem com vários modelos prontos para uso e métricas calculadas. Muitos deles não se aplicam ao Customer Journey Analytics ou precisam ser renomeados ou recriados. Outros dependem de uma solução para variáveis com reconhecimento de contexto no Customer Journey Analytics.

| Nome do filtro | Descrição |
| --- | --- |
| Todos os dados | Todos os dados é um filtro necessário que é adicionado dinamicamente aos relatórios quando uma métrica é adicionada à linha de uma tabela de forma livre. |
