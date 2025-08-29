---
title: Configurações de componente
description: Exibir as configurações principais de um componente de visualização de dados.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 96d6882c31a5e130219986d156c8e6eda84ec325
workflow-type: tm+mt
source-wordcount: '3739'
ht-degree: 55%

---

# Configurações de componente {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Configurações de componente"
>abstract="Visualize e configure o nome, a descrição e outras configurações relacionadas a um componente. Marque esta caixa para ocultar este componente de usuários não admins nos relatórios. Admins ainda podem acessar o componente selecionando **[!UICONTROL Mostrar todos os componentes]** em um projeto do espaço de trabalho."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Rótulos de contexto"
>abstract="A remoção de um rótulo de contexto pode afetar painéis ou relatórios específicos que utilizam o componente."

<!-- markdownlint-enable MD034 -->


As informações a seguir descrevem as configurações que um componente de visualização de dados usa.

![Configurações de componente descritas nesta seção](../assets/component-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Obrigatório. Permite alterar um componente de Métrica para Dimension ou o oposto. Alterar esta seleção suspensa desloca o componente para sua respectiva área de componentes incluídos. |
| [!UICONTROL Nome do componente] | Obrigatório. Permite especificar o nome amigável que aparecerá no Analysis Workspace. É possível renomear um componente, dando a ele um nome específico para a visualização de dados. |
| [!UICONTROL Descrição] | Opcional, mas recomendado. Fornece informações sobre o componente para outros usuários. |
| [!UICONTROL Tags] | Opcional. Permitem marcar o componente com tags personalizadas ou prontas para uso para facilitar a pesquisa/filtragem na interface do usuário do Analysis Workspace. |
| [!UICONTROL Rótulos de contexto] | Opcional. Um menu suspenso de [rótulos de contexto](#context-labels) disponíveis definidos pelo sistema que podem ser aplicados a um componente. |
| [!UICONTROL Nome do campo de esquema] | O nome do campo de esquema. |
| [!UICONTROL Tipo de conjunto de dados] | Obrigatório. Um campo não editável que mostra de qual tipo de conjunto de dados (evento, pesquisa ou perfil) o componente veio. |
| [!UICONTROL Conjunto de dados] | Um campo não editável que mostra de qual conjunto de dados o componente se originou. Este campo pode conter vários conjuntos de dados. |
| [!UICONTROL Tipo de esquema] | Um campo não editável que mostra o tipo de dados do componente.  Embora você possa usar qualquer tipo de campo de esquema compatível na Platform, nem todos os tipos de campos são compatíveis com o Customer Journey Analytics.  Os seguintes tipos de dados são compatíveis: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` e `Boolean`. Atualmente, apenas o tipo de dados de esquema `String` é permitido em conjuntos de dados de pesquisa. |
| [!UICONTROL ID de componente] | Obrigatório. A [API do Customer Journey Analytics](https://www.adobe.io/cja-apis/docs) usa esse campo para fazer referência ao componente. Cada componente em uma visualização de dados deve ser exclusivo. A Adobe gera automaticamente uma ID para cada componente; no entanto, você pode clicar no ícone editar e modificar a ID do componente. Alterar a ID do componente interrompe todos os projetos existentes do Workspace que contêm esse componente. Embora cada componente precise de uma ID exclusiva em uma única visualização de dados, é possível usar a mesma ID do componente em outras visualizações de dados. Se você usar a mesma ID do componente em outras visualizações de dados, será possível tornar os projetos do espaço de trabalho compatíveis entre as visualizações de dados. <br/>Para componentes baseados em perfil e pesquisa, a ID do componente tem um prefixo baseado na ID do conjunto de dados (por exemplo: `642b28fcc1f0ee1c074265a0.person.name.firstName`). Quando quiser reutilizar um perfil ou componente baseado em pesquisa (como `person.name.firstName`) no projeto do espaço de trabalho e configurar esse componente em diferentes visualizações de dados, forneça um nome exclusivo para a ID do componente (por exemplo: `myUniqueID.person.name.firstName`) em suas visualizações de dados. |
| [!UICONTROL Caminho] | Obrigatório. Um campo não editável que mostra o caminho do esquema de onde o componente veio. |
| [!UICONTROL Rótulos de uso de dados] | Quaisquer rótulos de uso de dados atribuídos a este componente no Adobe Experience Platform. [Saiba mais](/help/data-views/data-governance.md). |
| [!UICONTROL Ocultar componente nos relatórios] | Permitem a preparação do componente fora da visualização de dados para não administradores. Os administradores ainda podem acessá-lo clicando em [!UICONTROL Mostrar todos os componentes] em um projeto do Analysis Workspace. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Configurações do tipo de componente](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


## Rótulos de contexto

Rótulos de contexto são tags definidas pelo sistema aplicadas a componentes em uma visualização de dados. Quando rótulos de contexto são aplicados a componentes (dimensão ou métricas), o Customer Journey Analytics é instruído a usar esses componentes rotulados de contexto automaticamente em determinadas visualizações ou recursos.

Os rótulos de contexto permitem fornecer contexto semântico para dados individuais.  Em geral, a Customer Journey Analytics não precisa saber o significado semântico de uma dimensão ou métrica para executar sua análise.  No entanto, algumas situações (modelos de projeto e algumas visualizações selecionadas) exigem que o Customer Journey Analytics entenda o significado semântico para executar algum tipo de análise. Rótulos de contexto são criados para essas situações.

Os rótulos de contexto operam no nível do componente (dimensão ou métrica) e permitem grande flexibilidade na visualização de dados para o cliente. Por exemplo, é possível atribuir um rótulo de contexto a uma dimensão depois de aplicar várias transformações de pós-processamento a um campo. Ou até mesmo em uma dimensão que se baseia em um campo derivado.  Os rótulos de contexto fornecem uma camada de abstração sobre os componentes e campos.

Por motivos de conveniência, os rótulos de contexto padrão inteligentes são aplicados automaticamente a componentes com base em campos com um caminho XDM específico. Por exemplo, o rótulo de contexto **[!UICONTROL Commerce: Categoria do Produto]** é aplicado automaticamente a uma dimensão **[!UICONTROL Nome da categoria]** baseada no caminho do esquema `productListItems.productCategories.categoryName`. No entanto, você pode mover o rótulo de contexto para um componente diferente sem qualquer problema.

Para simplificar os modelos de projeto fornecidos pela Adobe, várias integrações (como Journey Optimizer, Content Analytics e muito mais) configuram visualizações de dados em que os componentes prontos para uso são construídos de uma maneira específica. Os rótulos de contexto apropriados são aplicados automaticamente. Novamente, basta mover qualquer um desses rótulos de contexto para outros componentes criados na visualização de dados, para que o componente personalizado seja usado.

Os rótulos de contexto também são relevantes para a divulgação de modelos de projeto. Os modelos de projeto criam rapidamente a base de relatórios para vários casos de uso diferentes criados com propósitos específicos. No entanto, nem todos os modelos fazem sentido para cada visualização de dados e você não deseja mostrar modelos não aplicáveis. Os rótulos de contexto são usados para mostrar modelos com base no fato de os rótulos de contexto serem incluídos na visualização de dados selecionada.  Basta adicionar mais rótulos de contexto à visualização de dados (componentes) e mais modelos serão disponibilizados. Ou remova rótulos de contexto para ocultar modelos específicos.

>[!NOTE]
>
>Você pode aplicar mais de um rótulo de contexto a um componente, mas não pode aplicar um rótulo de contexto a vários componentes em uma visualização de dados.
>

Os benefícios dos rótulos de contexto são:

* **Conveniência**: não é necessário selecionar novamente o mesmo componente em cada painel ou visualização.
* **Desbloqueia a funcionalidade**: algumas visualizações (como [Mapa](/help/analysis-workspace/visualizations/map.md)) exigem conhecimento sobre qual componente é latitude e longitude. A atribuição de rótulos de contexto divulga essas informações para a visualização.
* **Consistência**: todas as pessoas na sua organização que trabalham em um ou mais projetos baseados em uma visualização de dados que usa rótulos de contexto têm o mesmo comportamento.
* **Visibilidade de recursos e modelos**: certas visualizações e recursos só aparecem quando o rótulo de contexto adequado é atribuído. Por exemplo:

   * Uma visualização de [Mapa](/help/analysis-workspace/visualizations/map.md) é exibida corretamente somente quando o Customer Journey Analytics sabe quais campos representam latitude e longitude.
   * Os [modelos](/help/analysis-workspace/templates/use-templates.md) específicos ficam visíveis somente quando os rótulos de contexto corretos são aplicados e os componentes associados ficam disponíveis.

Os rótulos de contexto podem ser necessários nas seguintes situações:

* Para definir um conjunto de componentes, você pode usar o nos relatórios de experimentação usando o [painel de Experimentação](/help/analysis-workspace/c-panels/experimentation.md) em projetos do Analysis Workspace.

  Consulte [Integrar ao Journey Optimizer](/help/integrations/ajo.md#data-view) e [Relatórios do Target](/help/integrations/at.md) para mais informações.

* Para definir um conjunto de componentes, você pode usar a visualização [Mapa](/help/analysis-workspace/visualizations/map.md) em projetos Analysis Workspace.

  Para obter mais informações, consulte [Adicionar rótulos de contexto em visualizações de dados](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) em [Mapa](/help/analysis-workspace/visualizations/map.md).

  **Observação**: a visualização de mapa está na fase de teste limitado da versão e pode ainda não estar disponível em seu ambiente.

* Quando você usa [modelos fornecidos pelo Adobe](/help/analysis-workspace/templates/use-templates.md). Alguns modelos fornecidos pelo Adobe podem não funcionar porque determinados componentes não estão na visualização de dados.

  Para cada componente ausente, um rótulo de contexto correspondente está disponível na visualização de dados. Você precisa adicionar o rótulo de contexto correspondente a um componente que já esteja em sua visualização de dados. Ou você precisa adicionar um novo componente à visualização de dados e adicionar o rótulo de contexto ao componente (se ainda não tiver sido fornecido automaticamente).

  Para obter mais informações, consulte [Adicionar componentes ausentes à visualização de dados para um determinado modelo](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) no artigo [Criar e gerenciar modelos](/help/analysis-workspace/templates/create-templates.md).


Os seguintes grupos de rótulos de contexto estão disponíveis, cada um com uma lista de rótulos de contexto específicos.

+++ Campanha

| Nome | Descrição |
|------|-------------|
| Código de rastreamento | Código de rastreamento. |
| Instâncias de código de rastreamento | Rastrear instâncias de código. |

+++

+++ Comércio

| Nome | Descrição |
|------|-------------|
| Adições ao carrinho | Adições ao carrinho |
| Aberturas do carrinho | O carrinho é aberto. |
| Remoções do carrinho | Remoções do carrinho |
| Visualizações do carrinho | Visualizações do carrinho |
| Check-outs | Check-outs. |
| Pedidos | Pedidos. |
| Produto | Produto. |
| Categoria de produto | Categoria do produto. |
| Visualizações de produtos | Visualizações de produto. |
| Receita | Receita. |
| Loja | Loja. |
| Unidades | Unidades. |

+++

+++ Experimentação

| Nome | Descrição |
|------|-------------|
| Experimento de experimentação | Um experimento é um conjunto de variações em uma experiência que foram expostas aos usuários finais para determinar qual é a melhor opção a ser mantida como permanente. |
| Variante de experimentação | A variante é uma das duas ou mais alterações na experiência de um usuário final que estão sendo comparadas com o objetivo de identificar a melhor alternativa. |

+++

+++ Mídia

| Nome | Descrição |
|------|-------------|
| ID de conteúdo | ID de conteúdo. |
| Tempo gasto no conteúdo | Tempo gasto no conteúdo. |
| Episódio | Episódio. |
| Tipo de evento | Tipo de evento. |
| Tempo gasto com a mídia | Tempo gasto com a mídia. |
| Temporada | Temporada. |
| Segundos desde a última chamada | Segundos desde a última chamada. |
| Programa | Mostrar. |
| Hora de início | Hora de início. |
| Duração total do buffer | Duração total do buffer. |
| Duração total da pausa | Duração total da pausa. |
| Duração do vídeo | Duração do vídeo. |
| Nome do vídeo | Nome do vídeo. |

+++

+++ Central de atendimento

| Nome | Descrição |
|------|-------------|
| Nome da central de atendimento | Nome da central de atendimento. |
| Custos das chamadas | Custos de chamada. |
| Horas de chamada | Horário de atendimento. |
| Duração da chamada | Comprimento da chamada. |
| Motivo da chamada | Motivo da chamada. |
| Pontuação da pesquisa de chamadas | Pontuação de pesquisa de chamada. |
| Chamadas | Chamadas. |

+++

+++ Demográfico

| Nome | Descrição |
|------|-------------|
| Gênero | Sexo. |

+++

+++ Ambiente

| Nome | Descrição |
|------|-------------|
| Navegador | Navegador. |
| Tipo de navegador | Tipo de navegador. |
| Idioma | Idioma. |
| Sistema operacional | Sistema operacional. |
| Grupo do sistema operacional | Grupo do sistema operacional. |
| Nome do sistema operacional | Nome do sistema operacional. |

+++

+++ Geral

| Nome | Descrição |
|------|-------------|
| Nome da ação | Nome da ação. |
| Ações | Ações. |
| Canal de interação | Canal de interação. |

+++

+++ Geografia 

| Nome | Descrição |
|------|-------------|
| Cidade geográfica | Cidade geográfica. |
| País geográfico | País geográfico. |
| DMA geográfico | Geo dma. |
| Região geográfica | Região geográfica. |
| Latitude | Latitude |
| Longitude | Longitude. |
| Ponto de interesse | Ponto de interesse. |
| Estado | Estado. |

+++

+++ Canal de marketing

| Nome | Descrição |
|------|-------------|
| Canal de primeiro contato | Canal de primeiro contato. |
| Detalhes do canal de primeiro contato | Detalhes do canal de primeiro contato. |
| Canal de último contato | Canal de último contato. |
| Detalhes do canal de último contato | Detalhes do canal de último contato. |
| Canal de marketing | Canal de marketing. |

+++

+++ Dispositivo móvel

| Nome | Descrição |
|------|-------------|
| ID da aplicação | ID do aplicativo. |
| Operadora de celular | Operadora de celular. |
| Falhas em dispositivos móveis | Falhas de dispositivo móvel. |
| Nome do dispositivo móvel | Nome do dispositivo móvel. |
| Tipo de dispositivo móvel | Tipo de dispositivo móvel. |
| Nome da mensagem no aplicativo para dispositivos móveis | Mobile in app message name (Nome da mensagem no aplicativo móvel). |
| Instalações em dispositivos móveis | Instalações móveis. |
| Inicializações em dispositivos móveis | Lançamentos para dispositivos móveis. |
| Fabricante do dispositivo móvel | Fabricante móvel. |
| Cancelamentos de mensagens em dispositivos móveis | Cancelamentos de mensagem para dispositivo móvel. |
| Cliques de mensagens móveis | Cliques na mensagem móvel. |
| impressões de mensagens para dispositivos móveis | Impressões de mensagens móveis. |
| Aceitação de mensagens por push para dispositivos móveis | Aceitação de push de mensagem móvel. |
| Nome da mensagem por push para dispositivos móveis | Nome da mensagem de push do dispositivo móvel. |
| Atualizações para dispositivos móveis | Atualizações móveis. |
| Tempo dedicado por ação cronometrada | Tempo gasto por ação programada. |

+++

+++ Pesquisar

| Nome | Descrição |
|------|-------------|
| Mecanismo de pesquisa | Mecanismo de pesquisa. |
| Palavra-chave do mecanismo de pesquisa | Palavra-chave do mecanismo de pesquisa. |
| Mecanismo de pesquisa natural | Mecanismo de pesquisa natural. |
| Palavra-chave do mecanismo de pesquisa natural | Palavra-chave natural do mecanismo de pesquisa. |
| Mecanismo de pesquisa pago | Mecanismo de pesquisa pago. |
| Palavra-chave do mecanismo de pesquisa pago | Palavra-chave paga do mecanismo de pesquisa. |

+++

+++ Survey

| Nome | Descrição |
|------|-------------|
| Survey | Pesquisa. |
| Resposta da pesquisa | Resposta da pesquisa. |
| Pesquisa concluída | A pesquisa é concluída. |
| Pergunta da pesquisa | Pergunta da pesquisa. |
| Início da pesquisa | A pesquisa começa. |

+++

+++ Web

| Nome | Descrição |
|------|-------------|
| Tempo médio da página | Tempo médio da página. |
| Rejeições | Devoluções. |
| Página de entrada | Página de entrada. |
| Página de saída | Página de saída. |
| Página | Página. |
| Exibições de página | Exibições de página. |
| Referenciador | Referenciador. |
| Tipo de referenciador | Tipo de referenciador. |
| Domínio de referência | Domínio referenciador. |
| Domínio referenciador original | Domínio referenciador original. |
| Recargas | Recargas. |
| Visitas em única página | Visitas em única página. |
| Seções do site | Seções do site. |

+++

+++ B2B

| Nome | Descrição |
|------|-------------|
| Nome da conta | Nome da conta. |
| Nome do grupo de compra | Nome do grupo de compras |
| Nome da oportunidade | Nome da oportunidade |

+++

+++ Análise de conteúdo

| Nome | Descrição |
|------|-------------|
| Esquerda absoluta do ativo | Ativo absoluto à esquerda. |
| Topo absoluto do ativo | Ativo Absoluto Superior. |
| Atributos do ativo | Atributos do ativo. |
| Cores do plano de fundo do ativo | Cores de fundo do ativo. |
| Posições da câmera do ativo | Posicionamentos da câmera do ativo. |
| Proximidades da câmera do ativo | Proximidades da câmera do ativo. |
| Configurações da câmera do ativo | Configurações da câmera do ativo. |
| Cliques no ativo | Cliques em ativos. |
| Ativo criado por | Ativo criado por. |
| Data de criação do ativo | Data de criação do ativo.e |
| Altura de exibição do ativo | Altura de exibição do ativo. |
| Largura de exibição do ativo | Largura de exibição do ativo. |
| Cores de primeiro plano do ativo | Cores de primeiro plano do ativo. |
| ID do ativo | ID do ativo. |
| Tipos de imagem do ativo | Tipos de imagem de ativo. |
| Ativo atualizado pela última vez por | Última atualização do ativo. |
| Data da última atualização do ativo | Data da última atualização do ativo. |
| Condições de iluminação do ativo | Condições de iluminação do ativo. |
| URL do link do ativo | URL do link do ativo. |
| Nome do ativo | Nome do ativo. |
| Categorias de pessoas do ativo | Categorias de pessoas do ativo. |
| ID da percepção do ativo | Identificador exclusivo dos ativos que são perceptualmente os mesmos. |
| Estilos de fotografia do ativo | Estilos de fotografia de ativos. |
| Cenas do ativo | Cenas de ativos. |
| Origem do ativo | Source de ativos. |
| Tags do ativo | Tags de ativos. |
| Tipo de ativo | Tipo de ativo. |
| Visualizações do ativo | Exibições de ativos. |
| Distribuição da atenção visual do ativo | Difusão da atenção visual do ativo. |
| Densidade do conteúdo visual do ativo | Densidade de conteúdo visual do ativo. |
| Atributos da experiência | Atributos da experiência. |
| Canal da experiência | Canal de experiência. |
| Cliques da experiência | Cliques de experiência. |
| Contagem de emojis da experiência | Contagem de Emoji da experiência. |
| Contagem de hashtags da experiência | Contagem de hashtags de experiência. |
| Profundidade da porcentagem horizontal da experiência | Profundidade da porcentagem horizontal da experiência. |
| Palavras-chave da experiência | Palavras-chave de experiência. |
| Emoções de marketing da experiência | Experimente Emoções De Marketing. |
| Narrativas da experiência | Narrativas de experiência. |
| Estratégias de persuasão da experiência | Estratégias de Persuasão de Experiência. |
| Contagem de Palavras por Frase da Experiência de Leitura | Contagem De Palavras Por Frase Da Experiência De Leitura. |
| Pontuação de legibilidade da experiência | Pontuação da legibilidade da experiência. |
| Contagem de frases da legibilidade da experiência | Contagem de sentenças da experiência e legibilidade. |
| Contagem de palavras de irrelevantes da legibilidade da experiência | Contagem de Palavras de Interrupção da Legibilidade da Experiência. |
| Contagem de aspas no texto da legibilidade da experiência | Contagem de aspas de texto da experiência de leitura. |
| Contagem de palavras da legibilidade da experiência | Contagem de Palavras da Experiência de Legibilidade. |
| Origem da experiência | Experience Source. |
| Tons da experiência | Tons de experiência. |
| Profundidade da porcentagem vertical da experiência | Profundidade percentual vertical da experiência. |
| Visualizações da experiência | Exibições da experiência. |

+++

+++ Journey Optimizer

| Nome | Descrição |
|------|-------------|
| Erro de ação (AJO) | Contagem de erros gerados pelas ações de jornada. |
| Erro de execução da ação | Condição de erro que impediu o tempo de execução da jornada de executar a ação. |
| Rótulo da ação (AJO) | O nome de exibição gerado pelo cliente do elemento com o qual o usuário final interagiu. |
| Saídas alternativas (AJO) | A contagem de saídas que não ocorreram devido a um perfil que atingiu um nó final ou que falhou devido a um erro. |
| Instalações do aplicativo (AJO) | Número de instalações de aplicativos. |
| Inicializações do aplicativo (AJO) | Número de vezes que um aplicativo móvel é iniciado. |
| ID do lote (AJO) | GUID criado na invocação de cada nova instância do lote para uma ação agendada de campanha ou jornada. Por exemplo: se uma Jornada ou Ação de campanha programada for executada às 8h e às 10h, haverá dois batchInstanceIDs diferentes. |
| Carimbo de data e hora da instância do lote (AJO) | O carimbo de data e hora da instância do lote. |
| Rejeições pelos canais de saída (descontinuadas) | A contagem total de mensagens rejeitadas nos canais de saída. |
| Nome da ação da campanha (AJO) | O nome da ação da campanha. |
| ID da campanha (AJO) | A ID da campanha. |
| Nome da campanha (AJO) | O nome da campanha. |
| ID da versão do Campaign (AJO) | A ID da versão da campanha. |
| Canal | O canal ao qual esses dados devem estar correlacionados. |
| Cliques (AJO) | Contagem total de cliques em todos os canais. |
| Rejeições da política de consentimento (AJO) | Contagem de ações de jornada rejeitadas devido a uma ou mais políticas de consentimento. |
| Erro de decisão de conteúdo (AJO) | Mensagens de erro geradas pelos nós de decisão de conteúdo da jornada. |
| Erros de decisão de conteúdo (AJO) | Contagem de erros gerados pelos nós de decisão de conteúdo da jornada. |
| Nome do nó de decisão de conteúdo (AJO) | O nome do nó de decisão de conteúdo da jornada. |
| ID de correlação | ID de correlação. |
| Contagem de ofertas (AJO) | O número de itens de oferta na proposta. |
| Chave de associação de item de decisão | Um identificador composto que combina ID de item com ID de solicitação do Experience Decisioning, permitindo a persistência de dados entre interações. |
| Provedor de decisão (AJO) | O provedor que teve que tomar a decisão. Esta dimensão é usada quando vários serviços podem tomar decisões para o mesmo posicionamento ou atividade. |
| Provedor de decisão (persistente) (AJO) | O provedor de decisão com a vinculação de persistência habilitada. |
| ID da política de decisão (AJO) | A ID da política de decisão usada ao decidir quais itens incluir nessa proposta. |
| Métrica de desduplicação (AJO) | Métrica de desduplicação. |
| Entregues (descontinuado) | Contagem total de mensagens entregues. |
| Exibições (AJO) | Essa contagem exibe mensagens do AJO. Essa contagem inclui aberturas de email, exibições da Web e exibições no aplicativo. As plataformas móveis não relatam exibições de SMS e mensagens de push; portanto, não são contadas. |
| Descartado (AJO) | Conta todas as vezes em que a mensagem no aplicativo é fechada pelo SDK da Adobe, independentemente da ação escolhida pelo usuário final para fechá-la. |
| ID da execução de teste (AJO) | Identificador exclusivo da execução de teste. |
| Aberturas de email por bots (AJO) | Contagem total de aberturas de email executadas por bots. |
| Aberturas de email (AJO) | Contagem total de aberturas de email. |
| Domínio do destinatário do email (AJO) | Domínio do endereço de email. |
| Assunto do email | Assunto do email, não personalizado. |
| ID do evento | Um identificador exclusivo do evento da série temporal. |
| ID dos critérios de saída (AJO) | A ID dos critérios de saída usada para determinar se a jornada deve ser fechada. |
| Nome dos critérios de saída (AJO) | Nome dos critérios de saída. |
| ID do experimento (AJO) | A ID do experimento. |
| Nome do experimento (AJO) | O nome do experimento. |
| Contagem de ofertas substitutas (AJO) | O número de ofertas de fallback. |
| Erro de busca | Condição de erro que impediu o tempo de execução da jornada de executar a obtenção. |
| Cliques de entrada (AJO) | Contagem total de cliques nos canais de entrada. |
| Dispensas de entrada (AJO) | Contagem total de descartes nos canais de entrada. |
| Impressões de entrada (AJO) | Contagem total de impressões em canais de entrada. |
| Envios de entrada (AJO) | Contagem total de envios em canais de entrada. |
| Entrada acionada (AJO) | A proposta foi escolhida para ser exibida pelo SDK da Adobe. Outros fatores podem impedir que ela seja exibido de fato. |
| É otimizado para o tempo de envio (AJO) | A execução da mensagem é SendTimeOtimized? |
| É uma jornada de teste | O evento faz parte de uma execução de jornada de teste? |
| É mensagem de teste (AJO) | A mensagem é enviada como execução de teste? |
| ID do item (persistente) (AJO) | A ID do item com a vinculação de persistência habilitada. |
| ID do item (AJO) | O ID do item. |
| Nome do item (AJO) | O nome do item. |
| Nome do item (persistente) (AJO) | O nome do item com a vinculação de persistência habilitada. |
| Erros de ação da jornada (AJO) | Mensagens de erro geradas por ações de jornada. |
| Nome do nó da ação da jornada | O nome do nó da ação de jornada. |
| Entradas da jornada | “Verdadeiro” se o evento de etapa for um evento de entrada na jornada por um perfil. |
| Fim da jornada (AJO) | O fim da jornada. |
| Nome do nó do evento da jornada | Este valor é definido sempre que um segmento ou evento externo ocorre em uma jornada. |
| Motivo da exclusão da jornada | Motivo da exclusão da instância do jornada. |
| Nome da regra de exclusão da jornada | Nome da regra que causou a negação da entrada da jornada. |
| Exclusões da jornada (AJO) | Indica se o evento de etapa atual resultou em um descarte de jornada para um perfil. Isso normalmente ocorre devido à aplicação das regras de limite ou simultaneidade, impedindo maior progressão na jornada. |
| Tipo de saída da jornada (AJO) | O tipo de saída que ocorreu para a instância do jornada. |
| Falhas da jornada | Fornece o estado atual da etapa que terminou de ser executada. |
| ID da jornada | A ID da jornada. |
| Nome da jornada | O nome da jornada. |
| Nome e versão da jornada | O nome e a versão da jornada. |
| ID da versão da jornada | A ID da versão da jornada. |
| JourneyExits | &quot;Verdadeiro&quot; se a etapa atual levou ao encerramento de uma instância da jornada. Ou seja, a última etapa em uma jornada para um determinado perfil foi executada com sucesso. |
| Conversões na página de destino (AJO) | Contagem total de conversões na página de destino. |
| ID da página de destino (AJO) | Identificador exclusivo da página de destino. |
| Origem da página de destino (AJO) | A origem da página de destino. |
| Visualizações da página de destino (AJO) | Contagem total de visualizações da página de destino. |
| Cliques na página de destino (AJO) | Contagem total de cliques na página de destino. |
| URL do link (AJO) | O URL em que o usuário clicou. |
| Motivo da rejeição da mensagem (AJO) | O motivo da rejeição da mensagem. |
| Motivo do erro na mensagem (AJO) | O motivo do erro na mensagem. |
| Motivo da exclusão da mensagem (AJO) | Motivo da exclusão. |
| Categoria de falha da mensagem (AJO) | Categoria da falha . |
| Motivo da falha da mensagem (AJO) | Motivo da falha. |
| Tipo de falha da mensagem (AJO) | Tipo de falha. |
| ID da mensagem (AJO) | A ID da mensagem ao qual esses dados devem ser correlacionados. |
| Idioma da mensagem (AJO) | O idioma da mensagem. |
| Nome da mensagem (AJO) | O nome da mensagem. |
| Nova tentativa de mensagem (AJO) | Contagem de tentativas. |
| Status da mensagem (AJO) | Status da mensagem (por exemplo, enviado, rejeitado, erro etc.) |
| Tipo de mensagem (AJO) | Se a mensagem é de marketing ou transacional. |
| Status de feedback da mensagem (descontinuado) | Status de feedback. |
| Entradas de nó | “Verdadeiro” se o evento de etapa for um evento de entrada de nó por um perfil. |
| ID do nó | A ID do nó da jornada. |
| Nome do nó | O nome do nó da jornada. |
| Tipo de nó | O tipo de nó da jornada. |
| Namespace de identidade da ação da campanha orquestrada (AJO) | O namespace de identidade da ação de campanha orquestrada. |
| Nome da ação da campanha orquestrada (AJO) | O nome da ação da campanha orquestrada. |
| ID do nó da ação da campanha orquestrada (AJO) | A ID de ação da campanha orquestrada. |
| ID da campanha orquestrada (AJO) | A ID da campanha orquestrada. |
| Nome da campanha orquestrada (AJO) | O nome da campanha orquestrada. |
| ID da versão da campanha orquestrada (AJO) | A ID da versão da campanha orquestrada. |
| Cliques de saída (AJO) | Contagem total de cliques em canais de saída. |
| Erros de saída (descontinuado) | Contagem total de mensagens com erros nos canais de saída. |
| Exclusões de saída (descontinuado) | Contagem total de eventos de exclusão em canais de saída. |
| Envios de saída (descontinuado) | Contagem total de mensagens enviadas em canais de saída. |
| Ponto de interesse | ponto de interesse. |
| ID da proposta (AJO) | A ID da proposta. |
| Ações personalizadas por push (AJO) | Contagem total de ações personalizadas na interação por push. |
| Interações por push (AJO) | Número de vezes que um aplicativo móvel é iniciado devido a uma interação direta com a mensagem por push. |
| Plataforma de push (AJO) | Serviço de provedor de push, por exemplo, APNS ou FCM. |
| Título de push | Título do push, não personalizado. |
| ID da estratégia de classificação (AJO) | A ID da estratégia de classificação. |
| Nome da política de consentimento rejeitada | Nome da política de consentimento rejeitada correspondente. |
| Contagem de novas tentativas (AJO) | Número de vezes que um envio de mensagem foi repetido antes do sucesso ou da falha. |
| Nome da regra | Nome da regra que causou a negação da entrada da jornada. |
| Tipo de seleção (AJO) | Este é o tipo de seleção usado quando um item é derivado como parte de uma decisão. |
| Envios (descontinuado) | Contagem total de mensagens enviadas em todos os canais. |
| Mensagem SMS de entrada (AJO) | Resposta de entrada de SMS, por exemplo, parar, iniciar, assinar etc. |
| Mensagens SMS de entrada (AJO) | Resposta de entrada de SMS, por exemplo: parar, iniciar, assinar etc. |
| Tipo de mensagem SMS (AJO) | Provedor de SMS, por exemplo, inbound, inboundReply ou send. |
| Provedor de SMS (AJO) | Provedor de SMS, por exemplo, Sinch ou Twilio. |
| Reclamação de spam (AJO) | Contagem total de reclamações de spam. |
| Nome da estratégia (AJO) | Nome da estratégia. O nome da estratégia da qual o item foi derivado. |
| Nome da estratégia (persistente) (AJO) | O nome da estratégia com a vinculação de persistência habilitada. |
| Adições à lista de assinaturas (AJO) | Contagem total de adições a uma lista de assinaturas. |
| ID da lista de assinaturas (AJO) | Identificador exclusivo da lista de assinaturas. |
| Remoções da lista de assinaturas (AJO) | Contagem total de remoções de uma lista de assinaturas. |
| Superfície (AJO) | A superfície do canal na qual a mensagem foi exibida. |
| Direcionados (descontinuado) | Essa contagem do número de vezes que uma proposta foi direcionada a uma pessoa. É o número de vezes que uma proposta foi considerada para exibição a uma pessoa. |
| Nome da regra de direcionamento (AJO) | O nome da regra de direcionamento. |
| Evento de teste (AJO) | Evento de teste. |
| Hora de início | Hora de início. |
| Duração total do buffer | Duração total do buffer. |
| Duração total da pausa | Duração total da pausa. |
| Tipo de tráfego (AJO) | O tipo de tráfego da classificação. |
| ID do tratamento (AJO) | A ID do tratamento selecionado para o experimento. |
| Nome do tratamento (AJO) | O nome do tratamento do experimento. |
| Visitantes únicos no experimento (AJO) | Os visitantes únicos no experimento. |
| Cancelamentos de inscrições (AJO) | Contagem total de cancelamentos de inscrição. |
| Rótulo do URL (AJO) | Rótulo amigável do URL. |
| ID do URL (AJO) | Identificador exclusivo do URL clicado pelo usuário. |

+++
