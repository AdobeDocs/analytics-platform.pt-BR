---
title: Painel Público-alvo médio por minuto de mídia
description: Como usar e interpretar o painel Público-alvo médio por minuto de mídia no Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: 92e35e59d77f2bb3f7d33914bf825a3325a71051
workflow-type: tm+mt
source-wordcount: '1656'
ht-degree: 31%

---

# Painel Audiência média por minuto da mídia

>[!NOTE]
>
>O painel Público-alvo médio por minuto de mídia está disponível somente para clientes que compraram o complemento do Media Analytics para Customer Journey Analytics.
>
>Entre em contato com o representante de vendas do Adobe ou com a equipe de conta do Adobe para adquirir o Media Analytics.

No Analysis Workspace, a Audiência média por minuto é o tempo gasto visualizando seu fluxo de mídia dividido pela duração do conteúdo ou pela seleção total do período e granularidade selecionada.

O painel Audiência média por minuto da mídia permite entender melhor o consumo médio do conteúdo comparando programas de qualquer comprimento ou gênero. Por exemplo, você pode entender o consumo médio ao comparar um sitcom de 30 minutos com um evento esportivo de 3 horas.

Além disso, você pode usar o painel Audiência média por minuto da mídia para comparar ou anexar essa Audiência média por minuto digital às métricas de média por minuto lineares da TV.

O painel Público-alvo médio por minuto da mídia oferece os seguintes benefícios em relação à métrica Público-alvo médio por minuto:

* Oferece suporte a períodos personalizados

* Permite atualizar a classificação de duração após o processamento das exibições (se ela não estava presente ou se precisa ser corrigida)

  Se você fizer isso ao usar a métrica, ela não existirá (se a classificação não estiver presente) ou estará desatualizada (se a classificação estava presente, mas incorreta).

## Acessar o painel Público-alvo médio por minuto de mídia

1. No Analysis Workspace, vá para um conjunto de relatórios que tenha os componentes do Media Analytics ativados.

1. Na navegação à esquerda, selecione o **Painéis** ícone.

   ![Ícone Painéis na navegação à esquerda](assets/panels-icon.png)

1. Arraste o [!UICONTROL **Público médio a cada minuto de mídia**] na tela do Analysis Workspace.

1. Para configurar o painel, continue com [Entradas do painel](#panel-inputs).

## Entradas do painel {#Input}

Use as configurações de entrada descritas nesta seção para configurar o painel Público-alvo médio por minuto de mídia.

1. Comece a criar um painel Audiência média por minuto de mídia, conforme descrito em [Acessar o painel Público-alvo médio por minuto de mídia](#access-the-media-average-minute-audience-panel).

1. Defina as seguintes configurações de entrada:

   | Configuração | Descrição |
   |---------|------------|
   | **Intervalo de datas do painel** | O padrão do intervalo de datas do painel é [!UICONTROL **Este mês**]. É possível editá-lo para exibir um único dia ou muitos meses de cada vez. <br></br> Essa visualização é limitada a 1440 linhas de dados (por exemplo, 24 horas na granularidade no nível de minuto). Se uma combinação de intervalo de datas e granularidade resultar em mais de 1440 linhas, a granularidade será atualizada automaticamente para ajustar o intervalo de datas completo. |
   | [!UICONTROL **Solte um segmento aqui (ou qualquer outro componente)**] | Como outros painéis, essa configuração filtra as seleções com base nos segmentos criados. Essa é uma ótima maneira de observar plataformas específicas, fluxos ao vivo ou outros segmentos de mídia comuns. |
   | [!UICONTROL **Calcular métrica para**] | Escolha se deseja ver o público-alvo médio por minuto para um conteúdo específico ou se deseja ver o público-alvo médio por minuto de um período personalizado:<ul><li>**Conteúdo específico:** Isso só estará disponível se a duração tiver sido atualizada usando Classificações. Se a duração estiver indisponível, ou se você quiser visualizar o público-alvo médio por minuto de uma série de tempo com vários conteúdos ou conteúdos sem uma duração específica atribuída (como durante um fluxo ao vivo ou evento), selecione [!UICONTROL **Período personalizado**]. (As durações podem ser definidas usando classificações antes ou depois do tempo de processamento.)</li><li>**Período personalizado:** Isso está disponível independentemente de as durações serem disponibilizadas usando Classificações.</li></ul> <p>Essa configuração altera o fluxo de trabalho e a saída do relatório.</p> |

1. Continuar com [Conteúdo específico](#specific-content) ou [Período personalizado](#custom-time-period), dependendo da opção escolhida na caixa de diálogo [!UICONTROL **Calcular métrica para**] menu suspenso.

### Conteúdo específico

1. Se você selecionou [!UICONTROL **Conteúdo específico**] no [!UICONTROL **Calcular métrica para**] menu suspenso quando [configurando entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | [!UICONTROL **Dimensão de relatório**] | Ao escolher um conteúdo específico, é possível selecionar a saída do relatório para usar os campos nome do vídeo ou ID do conteúdo para mostrar o conteúdo e o público-alvo médio por minuto associado para o período selecionado. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Programa, temporada, episódio**]: exibe suas apresentações disponíveis no menu suspenso, que podem ser filtradas usando uma pesquisa (ou arrastando e soltando o nome da exibição na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: Se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que têm dados de público-alvo médio por minuto para a seleção que você escolheu. (Essa opção é selecionada por padrão.)</li></ul> |

1. Continuar com [Configurações avançadas de conteúdo específico](#specific-content-advanced-settings) para definir as configurações avançadas.

### Configurações avançadas de conteúdo específico

1. Com [!UICONTROL **Conteúdo específico**] selecionado na [!UICONTROL **Calcular métrica para**] selecione [!UICONTROL **Mostrar configurações avançadas**] e, em seguida, especifique as seguintes opções de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | Configurações da tabela | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove as duas colunas, deixando somente o público-alvo médio por minuto ao lado do nome do vídeo ou da ID do conteúdo. |
   | Métrica de tempo gasto | Você pode escolher o tempo de conteúdo padrão gasto, que inclui apenas o tempo de conteúdo, ou pode optar por usar o tempo de mídia gasto, que inclui o conteúdo e o tempo do anúncio juntos como cálculo do numerador para o público-alvo médio por minuto. |

1. Selecionar [!UICONTROL **Build**] para concluir a criação do painel Audiência média por minuto de mídia.

1. Continuar com [Saída do painel](#panel-output) para obter informações sobre como usar o painel Audiência média por minuto de mídia.

### Período personalizado

1. Se você selecionou [!UICONTROL **Período personalizado**] no [!UICONTROL **Calcular métrica para**] menu suspenso quando [configurando entradas do painel](#panel-inputs), especifique as seguintes opções de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | Granularidade | A granularidade padrão é [!UICONTROL **5 minutos**], mas você pode escolher qualquer uma das granularidades usadas como denominador para a série de tempo na seleção de período geral feita na seleção do calendário. Por exemplo, selecionar 12h às 12h30 com granularidade de 5 minutos retorna o público-alvo médio por minuto durante a meia hora completa, bem como seis linhas com o público-alvo médio por minuto para cada período de 5 minutos. Essas linhas são usadas como pontos de dados para o gráfico de série de tempo. |
   | [!UICONTROL **Filtrar conteúdo por (opcional)**] | Escolha como filtrar o conteúdo específico, dependendo da exibição desejada ou da maneira como seus dados são estruturados. <ul>[!UICONTROL **Programa, temporada, episódio**]: exibe suas apresentações disponíveis no menu suspenso, que podem ser filtradas usando uma pesquisa (ou arrastando e soltando o nome da exibição na coluna esquerda). Você pode terminar a seleção ali para ver todas as estações do programa, ou você pode filtrar por estações individuais e por episódios individuais. Esta configuração mostra os dados para esses programas, temporadas ou episódios do período selecionado.</li><li>[!UICONTROL **Dimensão personalizada**]: Se o seu nome de exibição estiver em uma dimensão personalizada, você poderá encontrá-lo pesquisando na lista suspensa da dimensão (opcional) ou usando a pesquisa de coluna à esquerda. O item de dimensão é preenchido automaticamente com base nessa seleção e é tratado como um episódio.</li><li>[!UICONTROL **Nenhum**]: mostra todos os nomes de vídeo que têm dados de público-alvo médio por minuto para a seleção que você escolheu. (Essa opção é selecionada por padrão.)</li></ul> |

1. Continuar com [Configurações avançadas do período personalizado](#custom-time-period-advanced-settings) para definir as configurações avançadas.

### Configurações avançadas do período personalizado

1. Com [!UICONTROL **Período personalizado**] selecionado na [!UICONTROL **Calcular métrica para**] selecione [!UICONTROL **Mostrar configurações avançadas**] e, em seguida, especifique a seguinte opção de configuração:

   | Configuração | Descrição |
   |---------|------------|
   | Configurações da tabela | A configuração padrão mostra os valores de cálculo na tabela, que mostra o numerador e o denominador do público-alvo médio por minuto como as colunas anteriores na tabela. Desmarcar essa opção remove essas duas colunas, deixando somente o público-alvo médio por minuto ao lado do período. |

1. Selecionar [!UICONTROL **Build**] para concluir a criação do painel Audiência média por minuto de mídia.

1. Continuar com [Saída do painel](#panel-output) para obter informações sobre como usar o painel Audiência média por minuto de mídia.

## Saída do painel

A saída do painel difere dependendo se você escolhe [!UICONTROL **Conteúdo específico**] ou [!UICONTROL **Período personalizado**] no [!UICONTROL **Calcular métrica para**] menu suspenso quando [configurando entradas do painel](#panel-inputs).

### Conteúdo específico

O painel Audiência média por minuto da mídia retorna o seguinte:

* Público-alvo médio por minuto para toda a seleção
* Filtros e público-alvo médio por minuto para vídeos individuais exibidos em uma tabela
* Tempo gasto no conteúdo e duração do vídeo (duração) se essa configuração avançada tiver sido selecionada

Para editar e recriar o painel a qualquer momento, selecione o ícone Editar (lápis) na parte superior direita.

![Visualização padrão](assets/specific-content-panel-output.png)

### Fonte de dados de conteúdo específico

O painel Público-alvo médio por minuto de mídia usa somente a métrica Público-alvo médio por minuto para coletar dados. Detalhamentos ou outras métricas não podem ser usadas no painel.

| Métrica | Descrição |
|--------|-------------|
| Público-alvo médio por minuto | O tempo gasto com a visualização do fluxo de mídia dividido pela duração do vídeo fornecido por Classificações. |

### Período personalizado {#custom-time-period-output}

O painel Audiência média por minuto da mídia retorna o seguinte:

* O público-alvo médio por minuto para toda a seleção

* O público-alvo médio por minuto máximo e mínimo

* O gráfico de série de linhas que mostra o público-alvo médio por minuto em toda a seleção.

* Uma tabela que mostra os filtros e o público-alvo médio por minuto para as granularidades, bem como o tempo gasto no conteúdo e a granularidade para cada período

  Esta tabela é exibida somente se a opção em configurações avançadas chamada [!UICONTROL **Mostrar valores de cálculo na tabela**] está selecionada.

Para editar e recriar o painel a qualquer momento, selecione o ícone Editar (lápis) na parte superior direita.

![saída de visualizadores simultâneos](assets/custom-time-period-panel-output.png)

### Fonte de dados de período personalizado

O painel Público-alvo médio por minuto de mídia usa somente a métrica Público-alvo médio por minuto para coletar dados. Detalhamentos ou outras métricas não podem ser usadas no painel.

| Métrica | Descrição |
|---|---|
| Público-alvo médio por minuto | O tempo gasto visualizando o fluxo de mídia dividido pela seleção total ou granularidade selecionada em minutos. |
