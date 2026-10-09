---
title: Usar resultados em cache para agilizar o carregamento no Analysis Workspace
description: Ative uma configuração de projeto no Analysis Workspace que armazena em cache os resultados por 12 horas para que os projetos sejam carregados instantaneamente. Atualize a qualquer momento para ver os dados mais recentes.
feature: Workspace Basics
hide: true
exl-id: 6d7b9d34-ec7e-45ec-98cc-0fd4cbfd43d3
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 32dfb7790f57293ea297bdcb8319c3d3b187a2ae
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 5%
---

# Usar resultados em cache em projetos do Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Usar resultados em cache para um carregamento mais rápido"
>abstract="Quando habilitado, os resultados são carregados instantaneamente por 12 horas após um projeto ser aberto pela primeira vez por um usuário ou entregue por um agendamento. Qualquer pessoa que abrir o projeto durante esse período verá os mesmos resultados, mesmo que os dados continuem a fluir em segundo plano. Para carregar os resultados mais recentes, atualize os painéis individuais ou o projeto inteiro."

{{release-limited-testing}}

Você pode configurar projetos Analysis Workspace para mostrar resultados em cache para uma janela de 12 horas, permitindo que os resultados sejam carregados instantaneamente para qualquer pessoa que abra o projeto depois que ele for carregado inicialmente.

Os projetos podem ser carregados inicialmente por um usuário que abre o projeto ou por um delivery de projeto agendado.

## Entender os resultados em cache em um projeto

### Quando os resultados são armazenados em cache

Na primeira vez que o projeto for carregado, os resultados serão carregados na velocidade normal e o Analysis Workspace os armazenará em cache por uma janela de 12 horas. Isso acontece quando:

* Alguém abra o projeto

* O projeto é executado para um delivery agendado

Por exemplo, se um projeto estiver agendado para entrega às 6h, os resultados serão armazenados em cache até às 18h. Todos os que abrirem o projeto entre 6h e 18h verão os resultados serem carregados instantaneamente, incluindo a primeira pessoa a abri-lo.

Após 12 horas, os resultados em cache expiram. Na próxima vez que o projeto for carregado, independentemente de um usuário abri-lo ou executar um delivery agendado, os resultados serão carregados na velocidade normal e uma nova janela de 12 horas será iniciada.

### Quais resultados são armazenados em cache

#### Inicialmente, o projeto é armazenado em cache com sua configuração original

O Analysis Workspace armazena em cache os resultados do projeto como ele foi configurado originalmente, com suas visualizações de dados selecionadas, segmentos aplicados, intervalos de datas, seleções suspensas de painel e assim por diante. Todos que abrirem o projeto verão esses resultados em cache.

Se alguém alterar a configuração do projeto ao visualizar o projeto em cache, os resultados serão carregados normalmente (não instantaneamente) e [uma nova variação de projeto será armazenada em cache](#project-variations-are-cached-as-the-project-is-modified).

#### As variações de projeto são armazenadas em cache quando o projeto é modificado

Uma nova variação do projeto é criada quando alguém altera sua configuração original, por exemplo, selecionando um item em um menu suspenso de painel, aplicando um segmento, alterando um intervalo de datas ou alterando a visualização de dados selecionada.

Uma nova variação é carregada na velocidade normal pela primeira vez. Depois disso, seus resultados também são armazenados em cache, para que qualquer pessoa que carregue a mesma variação veja os resultados instantaneamente.

Considere o seguinte:

* O Analysis Workspace armazena em cache cada variação de um projeto que alguém carrega. Ele não armazena em cache todas as variações possíveis de um projeto.

* O armazenamento em cache de uma nova variação não substitui nem invalida resultados que já estejam em cache. O projeto original é armazenado em cache junto com outras variações que as pessoas carregaram.

>[!BEGINSHADEBOX]

**Exemplo de cenário**

Suponha que um projeto de Desempenho de campanha global inclua segmentos para diferentes regiões e esteja programado para entrega às 6h:

| Hora | Ação | Velocidade da carga |
| --- | --- | --- |
| 6:00 | Entrega programada do projeto | Normal (os resultados são armazenados em cache para uso futuro) |
| 19:06 h | O usuário A abre o projeto | Instantâneo |
| 19:07 h | O usuário A aplica o segmento das Américas | Normal (os resultados são armazenados em cache para uso futuro) |
| 20:01 h | O usuário B abre o projeto | Instantâneo |
| 20:05 h | O usuário B aplica o segmento das Américas | Instantâneo |
| 20:12 h | O usuário B aplica o segmento EMEA | Normal (os resultados são armazenados em cache para uso futuro) |

>[!ENDSHADEBOX]

### Alterações que fazem com que os resultados em cache sejam atualizados com a próxima carga do projeto

As seguintes alterações na configuração subjacente de um projeto fazem com que o Analysis Workspace atualize os resultados na próxima vez que alguém abrir o projeto, mesmo que a janela de 12 horas não tenha expirado:

* Alterações em um componente na visualização de dados, como editar as [configurações do componente](/help/data-views/component-settings/overview.md) de uma dimensão ou métrica

* Alterações em um [campo derivado](/help/data-views/derived-fields/derived-fields.md)

* Alterações em uma definição de segmento usada no projeto

Os resultados são carregados na velocidade normal e são armazenados em cache, o que inicia uma nova janela de 12 horas.

### Quem vê os resultados em cache

Os resultados em cache são exibidos por padrão para todos os que:

* Tem acesso ao projeto

* Tem acesso às visualizações de dados usadas no projeto

* Está carregando uma variação do projeto que já está armazenado em cache, como um com os mesmos segmentos ou seleções suspensas do painel (para obter mais informações, consulte [Quais resultados estão armazenados em cache](#what-results-are-cached))

Ao visualizar os resultados em cache, você pode ver os dados mais recentes [atualizando manualmente os resultados](#manually-refresh-results-on-cached-projects).

### Quando deixar os resultados em cache desabilitados em um projeto

Alguns projetos dependem dos resultados para refletir os dados mais recentes sempre que alguém os abrir. Isso é comum para projetos que dependem muito de dados de mesmo dia, dados de chegada tardia ou [conjuntos de dados de pesquisa](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) que são atualizados com frequência.

Deixe os resultados em cache desabilitados no seu projeto se a maioria das pessoas que acessam o projeto precisar ver:

* **Dados do dia atual**

  Se um projeto for armazenado em cache às 7h, os resultados não incluirão dados que chegam após as 7h até que os resultados em cache expirem às 19h.

* **Dados de chegada atrasados imediatamente**

  Os dados de chegada tardia têm carimbos de data e hora de um período anterior, mas chegam após esse período ter passado. Por exemplo, [dados em lote](/help/data-ingestion/batch.md) de uma central de atendimento podem ser carregados no dia seguinte, ou um aplicativo móvel pode enviar eventos armazenados offline. Os resultados em cache não incluem esses dados até que expirem.

* **Valores de pesquisa atualizados**

  Os resultados em cache continuam mostrando os valores de pesquisa anteriores, como nomes de produtos antigos, até que expirem.

>[!NOTE]
>
>Se essas necessidades surgirem apenas ocasionalmente, habilite os resultados em cache e [atualize o projeto manualmente](#manually-refresh-results-on-cached-projects) quando precisar dos dados mais recentes.

## Habilitar resultados em cache para um projeto

Qualquer pessoa que possa atualizar as configurações do projeto pode habilitar os resultados em cache. Isso inclui o proprietário do projeto e qualquer pessoa com a função **[!UICONTROL Editar original]** para o projeto. Para obter mais informações sobre funções de projeto, consulte [Compartilhar uma função de projeto específica](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>Os resultados em cache podem não ser um bom ajuste se você precisar ver dados do dia atual, dados de chegada tardia ou valores de pesquisa atualizados imediatamente. Antes de habilitar esta configuração, analise [Quando deixar os resultados em cache desabilitados em um projeto](#when-to-leave-cached-results-disabled-on-a-project).

No projeto do Workspace, onde você deseja ativar os resultados em cache para agilizar o carregamento:

1. Vá para **[!UICONTROL Projetos]** > **[!UICONTROL Informações e configurações do projeto]**.

1. Selecione **[!UICONTROL Usar resultados em cache para um carregamento mais rápido]**.

1. Selecione **[!UICONTROL Salvar]**.

## Exibir quando os resultados em cache são mostrados em um projeto

Um carimbo de data e hora é exibido na parte superior do projeto quando os resultados em cache são exibidos. O carimbo de data e hora especifica se todos os resultados são armazenados em cache ou apenas alguns resultados:

* **[!UICONTROL Mostrando resultados de] [_data e hora_]**: todos os painéis no projeto mostram resultados em cache da data e hora mostradas.

* **[!UICONTROL Mostrando alguns resultados de] [_data e hora_]**: alguns painéis mostram resultados em cache da data e hora mostradas, enquanto outros foram atualizados mais recentemente.

![Carimbo de data/hora no projeto em cache](assets/project-cache-timestamp.png)

Os painéis também exibem um carimbo de data e hora, mostrando quando os resultados foram armazenados em cache:

* **[!UICONTROL Mostrando resultados de] [_data e hora_]**: o painel mostra resultados em cache da data e hora mostradas.

  >[!NOTE]
  >
  >Essa opção não está disponível durante a fase alfa da versão.

## Atualizar manualmente os resultados em projetos em cache

Somente os resultados mostrados no projeto são armazenados em cache. Os dados subjacentes do evento continuam a fluir para o Customer Journey Analytics como de costume.

Para ver os dados mais recentes antes da expiração dos resultados em cache, você pode atualizar manualmente os resultados de um projeto a qualquer momento durante a janela de 12 horas. Quando você atualiza o projeto inteiro, uma nova janela de 12 horas é iniciada e todos que abrirem o projeto durante essa janela verão os resultados atualizados.

No projeto do Workspace em que deseja exibir os dados mais recentes, você pode atualizar os resultados do projeto inteiro ou de um único painel.

### Atualizar resultados para todo o projeto

Para carregar os resultados mais recentes de todos os painéis e iniciar uma nova janela de 12 horas:

1. Selecione o ícone **[!UICONTROL Atualizar]** ![Atualizar](/help/assets/icons/Refresh.svg) na parte superior do projeto ao lado do carimbo de data/hora do projeto.

### Atualizar resultados para um único painel

>[!NOTE]
>
>Essa opção não está disponível durante a fase alfa da versão.

Para carregar os resultados mais recentes apenas para um único painel:

1. Selecione o ícone **[!UICONTROL Atualizar]** ![Atualizar](/help/assets/icons/Refresh.svg) ao lado do carimbo de data/hora de um painel.

