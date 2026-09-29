---
title: Usar resultados em cache para agilizar o carregamento no Analysis Workspace
description: Ative uma configuração de projeto no Analysis Workspace que armazena em cache os resultados da consulta por 12 horas para que os projetos sejam carregados instantaneamente. Atualize a qualquer momento para ver os dados mais recentes.
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
source-git-commit: 6bcbf10e6bff660f57f598f6cf75b43eb75c7db3
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 0%
---

# Usar resultados em cache em projetos do Workspace

>[!CONTEXTUALHELP]
>id="project_cached_results"
>title="Usar resultados em cache para um carregamento mais rápido"
>abstract="Quando habilitado, os resultados são carregados mais rapidamente por 12 horas depois que um projeto é aberto pela primeira vez por um usuário ou entregue por um agendamento. Qualquer pessoa que abrir o projeto durante esse período verá os mesmos resultados, mesmo que os dados continuem a fluir em segundo plano. Para carregar os resultados mais recentes, atualize os painéis individuais ou o projeto inteiro."

Você pode configurar projetos Analysis Workspace para mostrar resultados em cache para uma janela de 12 horas, permitindo que os resultados sejam carregados instantaneamente para qualquer pessoa que abra o projeto depois que ele for carregado inicialmente.

Os projetos podem ser carregados inicialmente por um usuário que abre o projeto ou por um delivery de projeto agendado.

>[!NOTE]
>
>Somente os resultados da consulta são armazenados em cache. Os dados subjacentes do evento continuam a fluir para o Customer Journey Analytics como de costume.
>
>Para ver os dados mais recentes antes da expiração dos resultados em cache, você pode [atualizar manualmente os resultados](#manually-refresh-results-on-cached-projects).

## Entender os resultados em cache em um projeto

### Quando os resultados são armazenados em cache

Na primeira vez que o projeto é executado, o Analysis Workspace executa a consulta como de costume e armazena os resultados em cache para uma janela de 12 horas. Isso acontece quando alguém abre o projeto ou quando o projeto é executado para um delivery agendado. Por exemplo, se um projeto estiver agendado para entrega às 6h, os resultados serão armazenados em cache até às 18h. Todos os que abrirem o projeto entre 6h e 18h verão os resultados serem carregados instantaneamente, incluindo a primeira pessoa a abri-lo.

Após 12 horas, os resultados em cache expiram. A próxima query no projeto, seja um usuário que a abra ou um delivery agendado, seja executada, seja carregada na velocidade normal e inicie uma nova janela de 12 horas.

### Quem pode ver os resultados em cache

Os resultados em cache são compartilhados com todos os que têm acesso ao projeto e às visualizações de dados usadas no projeto.

### Quais resultados são armazenados em cache

O Analysis Workspace armazena em cache cada consulta executada, não todas as versões possíveis de um projeto. Quando alguém altera a consulta, por exemplo, selecionando um item em um menu suspenso de painel ou aplicando um segmento, o Analysis Workspace executa uma nova consulta. A nova consulta é carregada na velocidade normal na primeira vez. Depois disso, seus resultados também são armazenados em cache.

O armazenamento em cache de uma nova consulta não substitui nem invalida resultados que já estejam em cache. A visualização original do projeto é armazenada em cache junto com outras variações que as pessoas executaram.

>[!BEGINSHADEBOX]

**Exemplo de cenário**

Suponha que um projeto de Desempenho de campanha global inclua segmentos para diferentes regiões e esteja programado para entrega às 6h:

| Hora | Ação | Velocidade da carga |
| --- | --- | --- |
| 6:00 | Entrega programada do projeto | Normal (os resultados são armazenados em cache para uso futuro) |
| 19:06 h | O usuário A abre o projeto | Rápido |
| 19:06 h | O usuário A aplica o segmento das Américas | Normal (os resultados são armazenados em cache para uso futuro) |
| 20:01 h | O usuário B abre o projeto | Rápido |
| 20:01 h | O usuário B aplica o segmento das Américas | Rápido |
| 20:01 h | O usuário B aplica o segmento EMEA | Normal (os resultados são armazenados em cache para uso futuro) |

>[!ENDSHADEBOX]

## Habilitar resultados em cache para um projeto

Qualquer pessoa que possa atualizar as configurações do projeto pode habilitar os resultados em cache. Isso inclui o proprietário do projeto e qualquer pessoa com a função **[!UICONTROL Editar original]** para o projeto. Para obter mais informações sobre funções de projeto, consulte [Compartilhar uma função de projeto específica](/help/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

No projeto do Workspace, onde você deseja ativar os resultados em cache para agilizar o carregamento:

1. Vá para **[!UICONTROL Projetos]** > **[!UICONTROL Informações e configurações do projeto]**.
1. Selecione **[!UICONTROL Usar resultados em cache para um carregamento mais rápido]**.
1. Selecione **[!UICONTROL Salvar]**.

## Exibir carimbos de data e hora de dados em projetos em cache

Quando um projeto é configurado para usar os resultados em cache, um carimbo de data e hora é exibido na parte superior do projeto, mostrando quando os resultados foram armazenados em cache:

* **[!UICONTROL Mostrando dados de] [_data e hora_]**: todos os painéis no projeto mostram resultados em cache a partir da data e hora mostradas.
* **[!UICONTROL Mostrando alguns dados de] [_data e hora_]**: alguns painéis mostram resultados em cache a partir da data e hora mostradas, enquanto outros foram atualizados mais recentemente.

Os painéis também exibem um carimbo de data e hora, mostrando quando os resultados foram armazenados em cache:

* **[!UICONTROL Mostrando dados de] [_data e hora_]**: o painel mostra resultados em cache a partir da data e hora mostradas.

## Atualizar manualmente os resultados em projetos em cache

Você pode atualizar manualmente os resultados de um projeto a qualquer momento durante a janela de 12 horas para visualizar os dados mais recentes. Quando você atualiza o projeto inteiro, uma nova janela de 12 horas é iniciada e todos que abrirem o projeto durante essa janela verão os resultados atualizados.

No projeto do Workspace em que deseja exibir os dados mais recentes, você pode atualizar os resultados do projeto inteiro ou de um único painel.

### Atualizar resultados para todo o projeto

Para carregar os resultados mais recentes de todos os painéis e iniciar uma nova janela de 12 horas:

1. Selecione **[!UICONTROL Atualizar]** na parte superior do projeto, ao lado do carimbo de data/hora do projeto.

### Atualizar resultados para um único painel

>[!NOTE]
>
>Essa opção não está disponível durante a fase alfa da versão.

Para carregar os resultados mais recentes apenas para um único painel:

1. Selecione **[!UICONTROL Atualizar]** ao lado do carimbo de data/hora de um painel.

