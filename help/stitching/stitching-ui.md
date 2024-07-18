---
title: Compilação
description: Saiba como criar e gerenciar conjuntos de dados compilados
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
exl-id: 8820a093-e573-45f9-bcd2-0933e21c231b
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 1%

---

# Criar e gerenciar conjuntos de dados compilados

{{select-package}}

A configuração permite que os administradores compilem identidades em conjuntos de dados disponíveis no Customer Journey Analytics. A compilação de conjuntos de dados aumenta a precisão da representação de um perfil, resultando em uma melhor análise e relatórios.

O processo de compilação permite definir uma **ID persistente** existente em um conjunto de dados. Em seguida, identificador persistente para uma janela de repetição especificada (diariamente, semanalmente) com a **ID transitória** (pessoa ou identificador autenticado) mais precisa disponível para esse conjunto de dados. Exemplos de identificadores transitórios são email, número de telefone, ID de CRM ou outras identidades armazenadas no gráfico. Consulte [Visão geral](overview.md) para obter mais informações sobre compilação.

## Criar

Para iniciar a compilação, crie um ou mais conjuntos de dados compilados. Para criar um conjunto de dados compilado:

1. Selecione **[!UICONTROL ** Compilação **]** em **[!UICONTROL ** Gerenciamento de Dados **]** na barra superior.

2. Na tela [!UICONTROL Conjuntos de dados compilados], selecione **[!UICONTROL ** Criar conjunto de dados compilado **]**.

   Será apresentado um diálogo explicando suas responsabilidades.

3. Selecione **[!UICONTROL ** Continuar **]** se você aceitar essas responsabilidades.

   >[!NOTE]
   >
   >    Se você selecionar **[!UICONTROL ** Cancelar **]**, não poderá criar um conjunto de dados compilado.

4. Na tela [!UICONTROL Conjuntos de dados compilados > Conjunto de dados compilado sem título]:

   1. Definir um **[!UICONTROL ** Nome do conjunto de dados **]** e (opcional) **[!UICONTROL ** Descrição **]**,

   2. Selecione a sandbox na lista **[!UICONTROL ** Sandbox **]** onde o conjunto de dados do evento está armazenado.

      ![Tela de criação inicial](./assets/create-initial.png)

   3. Selecione o botão **[!UICONTROL ** Selecionar conjunto de dados de origem **]**.

      Na janela pop-up [!UICONTROL Selecione um conjunto de dados para compilar]:

      ![Selecionar um conjunto de dados](./assets/select-one-dataset.png)

      - Selecione um conjunto de dados e selecione **[!UICONTROL ** Selecionar **]** para continuar.

   4. Selecione um identificador persistente na lista **[!UICONTROL ** ID persistente **]**.

   5. Selecione um identificador transitório na lista **[!UICONTROL ** ID Transitória **]**.

      Observe que um painel de visualização parece calcular as taxas de saturação (número de vezes que há um valor para cada um dos identificadores especificados sobre o número de eventos) para os últimos sete dias. Quando terminar de calcular, o painel visualiza com cores se as condições mínimas para compilação foram atendidas (verde) ou não (vermelho).

      ![Criar conjunto de dados compilado com taxas de saturação](./assets/create-before-experimenting.png)

      As condições mínimas são:

      - saturação persistente do identificador: taxa >= 95%

      - saturação transitória do identificador: taxa >= 5%

        Se as condições mínimas forem atendidas, você poderá experimentar com valores de amostra.

      - Selecione **[!UICONTROL ** Criar IDs de demonstração compiladas **]**.

        Na caixa de diálogo [!UICONTROL Experimento com valores de amostra], uma tabela é mostrada com um valor de exemplo para [!UICONTROL carimbo de data/hora], [!UICONTROL ID Persistente], [!UICONTROL ID Transitória], [!UICONTROL ID Compilada (Ao Vivo)], [!UICONTROL ID Compilada (repetição de 1 dia)] e [!UICONTROL ID Compilada (repetição de 7 dias)].

            ![Experimento com valores de amostra](./assets/experiment-sample-values.png)
            
            1.  Insira um valor para a **[!UICONTROL **ID persistente**]**.
            
            2.  Selecione **[!UICONTROL **Atualizar IDs compiladas**]** para ver o efeito do processo de compilação nos dados do conjunto de dados.
            
            3.  Selecione **[!UICONTROL **Fechar**]** quando terminar de testar valores de amostra.
        

        De volta à tela [!UICONTROL Conjuntos de dados compilados > _Nome do conjunto de dados_]:

   6. Selecione uma opção para a frequência e o período de reinicialização de dados históricos na lista **[!UICONTROL ** Janela de repetição **]**.

      Você pode selecionar entre o valor padrão **[!UICONTROL ** Dia anterior, diariamente **]** ou **[!UICONTROL ** Dias anteriores, semanalmente **]**.

   7. Selecione um valor na lista **[!UICONTROL ** Número médio de eventos diários **]**.

   8. Insira um valor (entre `0` e `12`) em **[!UICONTROL ** Número de meses para preenchimento retroativo **]**.

   9. Selecione **[!UICONTROL ** Salvar **]** para salvar o conjunto de dados compilado e iniciar a compilação.

## Exibir status

Você pode visualizar o status da compilação na lista [!UICONTROL Conjuntos de dados compilados].

- Selecione **[!UICONTROL ** Compilação **]** em **[!UICONTROL ** Gerenciamento de Dados **]** na barra superior.

  Você verá uma lista de conjuntos de dados compilados, cada um identificado com [!UICONTROL Sandbox], [!UICONTROL Conjunto de dados do Source], [!UICONTROL Status], [!UICONTROL Status de preenchimento retroativo], [!UICONTROL Proprietário] e [!UICONTROL Data de criação].

  ![Visão geral dos conjuntos de dados compilados](./assets/overview-stitched-datasetts.png)

  Os valores possíveis para [!UICONTROL Status] são:

  | Valor | Explicação |
  |-----|-----|
  | **[!UICONTROL ** Em fila **]** | A solicitação é recebida e processada em breve. |
  | **[!UICONTROL ** Criação **]** em andamento | Os recursos e o conjunto de dados recém-compilado estão sendo criados. |
  | **[!UICONTROL ** Configuração em andamento **]** | Há recursos e conjunto de dados compilado e a compilação está em andamento |
  | **[!UICONTROL ** Erro **]** | Há um problema com a compilação. Talvez um esquema tenha sido alterado entre o conjunto de dados de origem e o conjunto de dados compilado, o volume diário seja muito grande ou... (_**precisa de mais informações aqui...**_) |

  >[!INFO]
  >
  >    Sempre que um status é alterado, uma notificação é enviada com a mensagem **[!UICONTROL ** O conjunto de dados compilado _nome do conjunto de dados_ foi alterado para o status _nome do status _**]**.


  O [!UICONTROL status de preenchimento retroativo] pode ter os seguintes valores: 0%, 25%, 50%, 75% ou 100%.

  Você pode selecionar o ícone de informações para exibir um pop-up com mais detalhes sobre o conjunto de dados compilado selecionado.


## Excluir

>[!NOTE]
>
>Você só pode excluir conjuntos de dados com o status [!UICONTROL Configuração em andamento], [!UICONTROL Erro] ou [!UICONTROL Em fila].


Para excluir um único conjunto de dados compilado:

- Selecione **[!UICONTROL **...**]** para o conjunto de dados compilado e selecione **[!UICONTROL ** Excluir **]** no menu.

  ![Excluir um conjunto de dados compilado](./assets/delete-stitched-dataset.png)

Para excluir vários dados compilados:

- Selecione vários conjuntos de dados compilados usando a caixa de seleção no início de cada conjunto de dados listado.

- Selecione **[!UICONTROL **...**]** de um dos conjuntos de dados compilados selecionados e selecione **[!UICONTROL ** Excluir **]** no menu.
