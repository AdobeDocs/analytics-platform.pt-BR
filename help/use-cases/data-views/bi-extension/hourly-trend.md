---
title: Tendência por Hora
description: Caso de uso de tendência por hora para a extensão de BI em várias ferramentas de BI no Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Tendência horária


## Tendência horária

Nesse caso de uso, é desejável exibir uma tabela e uma visualização de linha simples que mostre uma tendência horária de ocorrências (eventos) para 1º de janeiro de 2023.

+++ Customer Journey Analytics

Um exemplo de painel **[!UICONTROL Tendência por hora]** para o caso de uso:

![Visualizações de tendências por hora do Customer Journey Analytics](../assets/cja_hourly_trend.png)

+++

+++ Ferramentas de BI

>[!PREREQUISITES]
>
>Verifique se você validou [uma conexão bem-sucedida, pode listar visualizações de dados e usar uma visualização de dados](connect-and-validate.md) para a ferramenta de BI para a qual deseja experimentar este caso de uso.
>

>[!BEGINTABS]

>[!TAB Power BI Desktop]

O ![AlertRed](/help/assets/icons/AlertRed.svg) Power BI **não** entende como lidar com campos de data e hora; portanto, dimensões como **[!UICONTROL daterangehour]** e **[!UICONTROL daterangeminute]** não são suportadas.

>[!TAB Tableau Desktop]

1. Selecione a guia **[!UICONTROL Folha 1]** na parte inferior para alternar da **[!UICONTROL Fonte de dados]**. Na exibição **[!UICONTROL Folha 1]**:
   1. Arraste a entrada **[!UICONTROL Daterange]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada na prateleira **[!UICONTROL Filtros]**.
   1. Na caixa de diálogo **[!UICONTROL Campo de Filtros \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e selecione **[!UICONTROL Próximo >]**.
   1. Na caixa de diálogo **[!UICONTROL Filtro \[Intervalo de datas\]]**, selecione **[!UICONTROL Intervalo de datas]** e especifique um período de `01/01/2023` a `02/01/2023`.

      ![Filtro do Tableau Desktop](../assets/uc3-tableau-filter.png)

   1. Arraste e solte **[!UICONTROL Daterangehour]** da lista **[!UICONTROL Tabelas]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Colunas]**.
      * Selecione **[!UICONTROL Mais]** > **[!UICONTROL Horas]** no menu suspenso **[!UICONTROL Daterangeday]**, para atualizar o valor para **[!UICONTROL HOUR(Daterangeday)]**.
   1. Arraste e solte **[!UICONTROL Ocorrências]** da lista **[!UICONTROL Tabelas (*Nomes de Medidas*)]** no painel **[!UICONTROL Dados]** e solte a entrada no campo ao lado de **[!UICONTROL Linhas]**. O valor é convertido automaticamente em **[!UICONTROL SUM(Occurrences)]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[!UICONTROL Ajustar]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Gráfico do Tableau Desktop](../assets/uc3-tableau-graph.png)

1. Selecione **[!UICONTROL Duplicar]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para criar uma segunda planilha.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1]** para renomear a planilha como `Graph`.
1. Selecione **[!UICONTROL Renomear]** no menu de contexto da guia **[!UICONTROL Planilha 1 (2)]** para renomear a planilha como `Data`.
1. Verifique se a folha de **[!UICONTROL Dados]** está selecionada. Na exibição **[!UICONTROL Dados]**:
   1. Selecione **[!UICONTROL Mostrar-me]** no canto superior direito e selecione **[!UICONTROL Tabela de texto]** (visualização superior esquerdo) para modificar o conteúdo do modo de exibição de Dados para uma tabela.
   1. Arraste **[!UICONTROL HOUR(Daterangeday)]** de **[!UICONTROL Colunas]** para **[!UICONTROL Linhas]**.
   1. Modifique **[!UICONTROL Padrão]** para **[!UICONTROL Exibição inteira]** do menu suspenso **[!UICONTROL Ajustar]** na barra de ferramentas.

      A área de trabalho do Tableau deve ser parecida com a exibida abaixo.

      ![Dados do Tableau Desktop](../assets/uc3-tableau-data.png)

1. Selecione o botão de guia **[!UICONTROL Novo Painel]** (na parte inferior) para criar um novo modo de exibição **[!UICONTROL Painel]**. No modo de exibição **[!UICONTROL Painel 1]**:
   1. Arraste e solte a planilha **[!UICONTROL Gráfico]** da prateleira **[!UICONTROL Folhas]** no modo de exibição **[!UICONTROL Painel 1]** que lê *Folhas de soltar aqui*.
   1. Arraste e solte a planilha **[!UICONTROL Dados]** da prateleira **[!UICONTROL Folhas]** abaixo da planilha **[!UICONTROL Gráfico]** no modo de exibição **[!UICONTROL Painel 1]**.
   1. Selecione a planilha **[!UICONTROL Dados]** no modo de exibição e modifique a **[!UICONTROL Exibição Inteira]** para **[!UICONTROL Corrigir Largura]**.

      A exibição do **[!UICONTROL Painel 1]** deve ser semelhante à mostrada abaixo.

      ![Tableau Desktop Dashboard 1](../assets/uc3-tableau-dashboard.png)


>[!TAB Pesquisador]


1. Na interface **[!UICONTROL Explorar]** do Looker, verifique se você possui uma configuração limpa. Caso contrário, selecione ![Configuração](/help/assets/icons/Setting.svg) **[!UICONTROL Remover campos e filtros]**.
1. Selecione **[!UICONTROL + Filtro]** abaixo de **[!UICONTROL Filtros]**.
1. Na caixa de diálogo **[!UICONTROL Adicionar Filtro]**:
   1. Selecionar **[!UICONTROL ‣ Visualização De Dados Cc]**
   1. Na lista de campos, selecione **[!UICONTROL ‣ Data do Intervalo de Datas]** e **[!UICONTROL Data do Intervalo de Datas]**.
      ![Filtro de pesquisa](../assets/uc2-looker-filter.png)
1. Especifique o filtro **[!UICONTROL Data do Intervalo de Datas da Visualização de Dados Cc]**, pois **[!UICONTROL está no intervalo]** **[!UICONTROL 2023/01/01]** **[!UICONTROL até (antes)]** **[!UICONTROL 2023/01/02]**.
1. Na seção **[!UICONTROL Visualização de Dados Cc]** no painel esquerdo,
   1. Selecione **[!UICONTROL ‣ Data Daterangehour]**, depois **[!UICONTROL Hora]** da lista de **[!UICONTROL DIMENSÕES]**.
   1. Selecione **[!UICONTROL Contagem]** abaixo de **[!UICONTROL MEDIDAS]** no painel esquerdo (na parte inferior).
1. Selecione **[!UICONTROL Executar]**.
1. Selecione **[!UICONTROL ‣ Visualização]** para exibir a visualização de linha.

Você deve ver uma visualização e tabela semelhantes, como mostrado abaixo.

![Tendência diária do resultado da pesquisa](../assets/uc3-looker-result.png)


>[!TAB Jupyter Notebook]

1. Insira as seguintes instruções em uma nova célula.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. Execute a célula. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![Resultados do Jupyter Notebook](../assets/uc3-jupyter-results.png)


>[!TAB RStudio]

1. Insira as seguintes instruções entre ` ```{r} ` e ` ``` ` em uma nova parte.

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. Execute o pedaço. Você deve ver uma saída semelhante à captura de tela abaixo.

   ![RSudio Results](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
