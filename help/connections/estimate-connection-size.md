---
title: Estimar tamanho da conexão
description: Relatório sobre o uso atual do Customer Journey Analytics (para fins de faturamento)
translation-type: tm+mt
source-git-commit: 27b3b1d9e6042f4c61cd1d5bb9d574cc268c3460
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# Estimar tamanho da conexão

Talvez seja necessário saber quantas linhas de dados você tem atualmente em [!UICONTROL Customer Journey Analytics]. O objetivo deste tópico é mostrar como reportar sobre o uso atual de [!UICONTROL Customer Journey Analytics].

1. Em [!UICONTROL Customer Journey Analytics], clique na guia **[!UICONTROL Conexões]**.
1. Na tela [!UICONTROL Editar conexão], selecione uma conexão para a qual deseja determinar o tamanho de uso/conexão.

   ![Editar conexão](assets/edit-connection.png)

1. Selecione um conjunto de dados que faça parte da conexão no painel esquerdo. Nesse caso, é o conjunto de dados &quot;Impressão B2B&quot;.

   ![conjunto de dados](assets/dataset.png)

1. Clique no ícone azul (i) (informações) ao lado de seu nome. Você observará que o Conjunto de dados tem 3,8 mil linhas/eventos. Além disso, para o número exato de linhas, clique em **[!UICONTROL Editar em Experience Platform]** abaixo da tabela de pré-visualização. Isso redirecionará você para os conjuntos de dados em [!UICONTROL Adobe Experience Platform].

   ![Informações do conjunto de dados AEP](assets/data-size.png)

1. Observe que o **[!UICONTROL Total de registros]** desse conjunto de dados é de 3,83 k, com o tamanho dos dados de 388,59 KB.

1. Repita as etapas de 1 a 5 para outros conjuntos de dados em sua conexão e adicione o número de registros/linhas. O número agregado final será a métrica de uso de sua conexão, e esse é o número de linhas dos conjuntos de dados de sua conexão que você vai assimilar de [!UICONTROL Adobe Experience Platform].

## Determinar o número de linhas ingeridas

O número de eventos realmente ingeridos no CJA depende das configurações de sua conexão. Além disso, se você selecionou a ID de pessoa incorreta ou se essa ID não estiver disponível para algumas linhas nos conjuntos de dados, então [!UICONTROL Customer Journey Analytics] ignorará essas linhas. Para determinar as linhas reais de eventos ingeridos, execute as seguintes etapas:

1. Depois de salvar a conexão, crie uma visualização de dados da mesma conexão sem filtros.
1. Crie um projeto do Workspace e selecione a visualização de dados correta. Crie uma tabela de forma livre e arraste e solte a métrica **[!UICONTROL Eventos]** com uma dimensão **[!UICONTROL Ano]**. Escolha um intervalo de datas grande o suficiente do seu calendário de seleção de datas para encapsular todos os dados em sua conexão. Isso permitirá que você veja o número de eventos sendo ingeridos em [!UICONTROL Customer Journey Analytics].

   ![Projeto do espaço de trabalho](assets/event-number.png)

   >[!NOTE]
   >
   >Isso permite que você veja o número de eventos que estão sendo assimilados do conjunto de dados de eventos. Ela não inclui conjuntos de dados de tipo de perfil e pesquisa. Siga as etapas de 1 a 3 para conjuntos de dados de perfil e pesquisa e adicione os números para obter o número total de linhas para essa conexão.

## Diagnosticando discrepâncias

Em alguns casos, você pode notar que o número total de eventos ingeridos pela sua conexão é diferente do número de linhas no conjunto de dados no AEP. Nesse caso, o conjunto de dados &quot;Impressão B2B&quot; tem 7650 linhas, mas o conjunto de dados contém 3830 linhas no AEP. Há várias razões pelas quais podem ocorrer discrepâncias e as seguintes etapas podem ser executadas para diagnosticar:

1. Analise essa dimensão por **[!UICONTROL ID do conjunto de dados da plataforma]** e você observará dois conjuntos de dados com o mesmo tamanho, mas diferentes **[!UICONTROL IDs do conjunto de dados da plataforma]**. Cada conjunto de dados tem 3825 registros. Isso significa que [!UICONTROL Customer Journey Analytics] ignorou 5 registros devido a IDs de pessoa ausentes ou a carimbos de data e hora ausentes:

   ![detalhamento](assets/data-size2.png)

1. Além disso, se verificarmos [!UICONTROL Adobe Experience Platform], não há conjunto de dados com a ID &quot;5f21c12b732044194bffc1d0&quot;, portanto, alguém excluiu esse conjunto de dados específico de [!UICONTROL Adobe Experience Platform] quando a conexão inicial estava sendo criada. Mais tarde, ele foi adicionado ao [!UICONTROL Customer Journey Analytics] novamente, mas um [!UICONTROL ID do conjunto de dados da plataforma] diferente foi gerado pelo [!UICONTROL Adobe Experience Platform].

   Leia mais sobre as [implicações do conjunto de dados e da exclusão de conexão](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components) em [!UICONTROL Customer Journey Analytics] e [!UICONTROL Adobe Experience Platform].
