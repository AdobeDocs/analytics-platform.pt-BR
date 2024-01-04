---
description: A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 93%

---

# Gerenciar fontes de dados

A sincronização de visualizações permite que você controle qual tabela de dados ou fonte de dados corresponde a uma visualização.

**Dica:** saiba quais visualizações têm relação umas com as outras pela cor do ponto ao lado do título. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.

O gerenciamento de uma fonte de dados permite exibir a fonte de dados ou bloquear a seleção. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

1. [Crie um projeto](/help/analysis-workspace/home.md) com uma tabela de dados e uma [visualização](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. Na tabela de dados, selecione as células (fonte de dados) que você deseja associar à visualização.
1. Na visualização, clique no ponto ao lado do título para abrir a caixa de diálogo **[!UICONTROL Fonte de dados]**. Selecione **[!UICONTROL Exibir fonte de dados]** ou **[!UICONTROL Bloquear seleção]**.

   ![A caixa de diálogo da opção Fonte de dados mostrando as opções descritas na próxima seção.](assets/manage-data-source.png)

   A sincronização de uma visualização a uma célula da tabela cria uma nova tabela (oculta) e coloca códigos de cor na visualização sincronizada à tabela.

| Elemento | Descrição |
|--- |--- |
| [!UICONTROL Visualizações vinculadas] | Se houver visualizações conectadas a uma de forma livre ou tabela de coorte, o ponto no alto à esquerda abre uma lista de visualizações conectadas com uma opção de caixa de seleção “Mostrar” para mostrar/ocultar a tabela.  Passar o mouse destaca a visualização vinculada; para acessá-la, clique nela. |
| [!UICONTROL Exibir fonte de dados] | Permite exibir (ativando a caixa de seleção) ou ocultar (desativando) a tabela de dados que corresponde à visualização. |
| [!UICONTROL Bloquear seleção] | Ative essa configuração para bloquear a visualização de dados selecionados no momento na tabela de dados correspondente. Uma vez ativada, escolhe entre:  <ul><li>**Posições selecionadas**: escolha essa opção se desejar que a visualização continue bloqueada nas posições selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados. Por exemplo, escolha essa opção se desejar mostrar os cinco principais nomes de campanha nessa visualização o tempo todo, não importa quais nomes de campanha apareçam entre as cinco principais.</li> <li>**Itens selecionados**: escolha essa opção se desejar que a visualização continue bloqueada nos itens especificados atualmente selecionados na tabela de dados correspondente. Esses itens continuarão a ser visualizados, mesmo que as suas classificações sejam alteradas na tabela. Por exemplo, escolha essa opção se desejar mostrar os cinco mesmos nomes de campanha específicos nessa visualização o tempo todo, não importa a classificação desses nomes de campanha.</li></ul> |

Essa arquitetura difere da anterior no sentido de que o Analysis Workspace já não cria uma tabela oculta duplicada que armazena a seleção bloqueada para você. Agora, a fonte de dados aponta para a tabela da qual você criou a visualização.

**Exemplo de casos de uso:**

* É possível criar uma visualização de resumo e bloqueá-la a uma célula na tabela a partir da qual você a criou. Ao ativar a opção “Exibir fonte de dados”, ela mostra exatamente de onde vem a informação na tabela. Os dados de origem aparecerão em cinza:

  ![Local da fonte de dados em uma planilha.](assets/data-source2.png)>
* É possível adicionar várias visualizações e extraí-las de diferentes células na mesma tabela, como mostrado abaixo. A tabela é igual à mostrada no exemplo acima, mas a célula extraída e a métrica são diferentes:

  ![Local da fonte de dados com visualizações adicionadas provenientes de várias células](assets/data-source3.png)>
* Você pode ver se há visualizações conectadas a uma tabela de forma livre ou tabela coorte ao clicar no ponto esquerdo superior (Configurações da fonte de dados). Passar o mouse destacará a visualização vinculada e clicar nela levará você para o link especificado.

  ![Configurações da fonte de dados que destacam uma visualização vinculada para as Principais exibições da página.](assets/linked-visualizations.png)>
