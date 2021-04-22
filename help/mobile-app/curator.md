---
description: Instruções para configuração de scorecards para painéis.
title: Manual do curador de painéis do Customer Journey Analytics
translation-type: ht
source-git-commit: 026771a61bcbd0eec8cb59a1d06f3dad0b96acf6
workflow-type: ht
source-wordcount: '2403'
ht-degree: 100%

---


# Guia do curador para painéis do Analytics

As informações a seguir instruem os curadores de dados do Adobe Analytics sobre como configurar e apresentar painéis para usuários executivos. Para ver um vídeo que demonstra essas informações, consulte o vídeo do Construtor de scorecard dos painéis do Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/34544)

## Introdução

Os painéis do Adobe Analytics fornecem insights a qualquer hora e em qualquer lugar com base nos dados do Customer Journey Analytics. O aplicativo permite aos usuários acesso móvel a scorecards intuitivos criados e compartilhados na interface de desktop do Customer Journey Analytics. Os cartões de pontuação são uma coleção das métricas principais e de outros componentes apresentados em um layout lado a lado, que você pode usar para obter detalhamentos mais minuciosos e visualizações de dados de tendências. Você pode adaptar os Scorecards de acordo com os dados mais importantes para você. Os painéis do Analytics são aceitos em sistemas operacionais iOS e Android.

## Mais informações sobre este guia

Este manual tem como objetivo ajudar os curadores de dados do Customer Journey Analytics a configurar os scorecards para os usuários executivos nos painéis. Os curadores podem ser administradores organizacionais ou pessoas em outras funções responsáveis pela configuração dos Scorecards para aplicativos, que permitem aos usuários executivos visualizar uma ampla renderização de dados sumários importantes de maneira rápida e fácil em seus próprios dispositivos móveis. Embora os usuários executivos sejam os usuários finais dos painéis do Analytics, este guia ajudará os curadores de dados a configurar o aplicativo de maneira eficaz para esses usuários.

## Glossário de termos

A tabela a seguir descreve os termos para entender o público-alvo, as funções e a operação dos painéis do Analytics.

| Termo | Definição |
|--- |--- |
| Consumidor | Usuário executivo que visualiza os insights e as métricas principais do CJA em um dispositivo móvel |
| Curador | Usuário com conhecimento de dados que encontra e distribui insights do CJA e configura os scorecards para serem visualizados pelo consumidor |
| Preparação | O ato de criar ou editar um Scorecard para dispositivos móveis com métricas, dimensões e outros componentes relevantes para o consumidor |
| Scorecard | Uma exibição de painéis que contém um ou mais blocos |
| Bloco | Uma renderização para uma métrica em uma Exibição de scorecard |
| Detalhamento | Uma exibição secundária acessível ao tocar em um bloco no Scorecard. Essa exibição é expandida na métrica mostrada no bloco e, opcionalmente, relata as dimensões adicionais de detalhamento |
| Intervalo de datas | O intervalo de datas principal dos relatórios de painéis |
| Intervalo de datas de comparação | O Intervalo de datas comparado ao intervalo de datas principal |

## Criar um Scorecard para usuários executivos

Um Scorecard exibe as principais visualizações de dados para usuários executivos em um layout lado a lado, como mostrado abaixo:

![Exemplo de scorecard](assets/intro_scorecard.png)

Como curador deste Scorecard, você pode usar o Construtor de scorecards para configurar quais blocos são exibidos no Scorecard para o consumidor. Você também configura como as exibições detalhadas ou os Detalhamentos podem ser ajustados quando os blocos forem tocados. A interface do Construtor de scorecards é mostrada abaixo:

![Construtor de scorecards](assets/scorecard_builder.png)

Para criar o Scorecard, é necessário fazer o seguinte:

1. Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco].
2. Configure o Scorecard com os dados e salve.

### Acesse o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco]

Você pode acessar o modelo de [!UICONTROL Scorecard para dispositivos móveis em branco] de uma das seguintes maneiras:

**Criar um novo projeto**

1. Abra o Customer Journey Analytics e clique em **Projetos**.
2. Clique no botão **[!UICONTROL Criar novo projeto]** e selecione o modelo de projeto de **[!UICONTROL Scorecard para dispositivos móveis em branco]**.
3. Clique no botão **[!UICONTROL Criar]**.

![Modelo de Scorecard](assets/new_template_cja.png)

**Adicionar um projeto**

Na tela **[!UICONTROL Projetos]**, na guia **[!UICONTROL Componentes]**, clique no botão **[!UICONTROL Adicionar]** e selecione **[!UICONTROL Scorecard para dispositivos móveis]**.

![Adicionar projetos](assets/add_project.png)

**Ou**

No menu **[!UICONTROL Ferramentas]** selecione **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**. Na tela seguinte, clique no botão **[!UICONTROL Criar novo scorecard]**.

### Configure o Scorecard com os dados e salve

Para implementar o modelo de Scorecard:

1. Em **[!UICONTROL Propriedades]** (no painel direito), especifique uma **[!UICONTROL Visualização de dados do projeto]** da qual você quer usar dados.

   ![Seleção da visualização de data](assets/properties_save.png)

2. Para adicionar um novo bloco ao Scorecard, arraste uma métrica do painel esquerdo e solte-a na zona **[!UICONTROL Arrastar e soltar métricas aqui]**. Também é possível inserir uma métrica entre dois blocos usando um fluxo de trabalho semelhante.

   ![Adicionar blocos](assets/build_list.png)


   *Em cada bloco, é possível acessar uma exibição detalhada que mostra informações adicionais sobre a métrica, como itens principais para uma lista de dimensões relacionadas.*


3. Para adicionar uma dimensão relacionada a uma métrica, arraste uma dimensão do painel esquerdo e solte-a em um bloco. Por exemplo, você pode adicionar dimensões apropriadas (como **[!DNL DMA Region]**, neste exemplo) às métricas **[!UICONTROL Visitantes únicos]** arrastando e soltando no bloco; as dimensões que você adicionar aparecerão na seção de detalhamento das **[!UICONTROL Propriedades]** específicas do bloco. É possível adicionar várias dimensões a cada bloco.

   ![Adicionar dimensões](assets/layer_dimensions.png)

   Quando você clica em um bloco no Construtor de scorecards, o painel direito exibe as propriedades e características associadas a esse bloco. Nesse painel, você pode fornecer um novo **[!UICONTROL Título]** para o bloco e, como alternativa, configurá-lo especificando os componentes, em vez de arrastá-los e soltá-los no painel esquerdo.

   ![Bloco de propriedades](assets/properties_tile.png)

   Além disso, se você clicar nos blocos, um pop-up dinâmico mostrará como a exibição Detalhamento aparecerá para o usuário executivo no aplicativo. Se nenhuma dimensão tiver sido aplicada ao bloco, a dimensão de detalhamento será a **hora** ou os **dias**, dependendo do intervalo de datas padrão.

   ![Detalhamento_exibição](assets/break_view.png)

   Cada dimensão adicionada ao bloco será mostrada em uma lista suspensa na exibição detalhada do aplicativo. O usuário executivo pode então escolher entre as opções indicadas na lista suspensa.

4. Para aplicar filtros a blocos individuais, arraste um filtro do painel esquerdo e solte-o diretamente na parte superior do bloco. Se você quiser aplicar o filtro a todos os blocos no cartão de pontuação, solte o bloco sobre o cartão de pontuação. Ou você também pode aplicar filtros selecionando filtros no menu de filtro abaixo dos intervalos de datas. Você [configura e aplica filtros para seus Scorecards](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) da mesma forma que faria no Adobe Analytics Workspace.

   ![Criar um filtro](assets/segment_ui.png)

5. Da mesma forma, para remover um componente aplicado a todo o cartão de pontuação, clique em qualquer lugar do cartão de pontuação fora dos blocos e remova-o clicando no **x** que aparece ao passar o mouse sobre o componente, como mostrado abaixo para o filtro **Novas visitas**:

   ![Remover_componentes](assets/new_remove.png)

6. Adicione e remova combinações de intervalo de datas que podem ser selecionadas no cartão de pontuação selecionando o menu suspenso Intervalo de datas.

   ![Novo cartão de pontuação](assets/new_score_card.png)

   Cada novo cartão de pontuação começa com seis combinações de intervalo de datas focadas nos dados de hoje e ontem. Você pode remover intervalos de datas desnecessários clicando no x ou editar cada combinação de intervalo de datas clicando no lápis.

   ![Novo cartão de pontuação2](assets/new_score_card2.png)

   Para criar ou alterar uma data principal, use o menu suspenso para selecionar dentre os intervalos de datas disponíveis ou arraste e solte um componente de data do painel direito na área designada.

   ![Novo cartão de pontuação3](assets/new_score_card3.png)

   Para criar uma data de comparação, você pode selecionar entre predefinições convenientes para comparações de tempo comuns no menu suspenso. Você também pode arrastar e soltar um componente de data no painel direito.

   ![Novo cartão de pontuação4](assets/new_score_card4.png)

   Se o intervalo de datas desejado ainda não tiver sido criado, será possível criar um novo clicando no ícone de calendário.

   ![Novo cartão de pontuação4](assets/new_score_card5.png)

7. Isso o levará ao construtor de intervalo de datas, em que é possível criar e salvar um novo componente de intervalo de datas. Para nomear o Scorecard, clique no namespace no canto superior esquerdo da tela e digite o novo nome.

   ![Nomeação_Scorecards](assets/new_name.png)

## Compartilhar o Scorecard

Para compartilhar o Scorecard com um usuário executivo:

1. Clique no menu **[!UICONTROL Compartilhar]** e selecione **[!UICONTROL Compartilhar scorecard]**.

2. No formulário **[!UICONTROL Compartilhar scorecard para dispositivos móveis]**, preencha os campos da seguinte forma:

   * Fornecer o nome do Scorecard
   * Fornecer uma descrição do Scorecard
   * Adicionar tags relevantes
   * Especificar os destinatários do Scorecard

3. Clique em **[!UICONTROL Compartilhar]**.

![Compartilhar_Scorecards](assets/new_share.png)

Depois de compartilhar um Scorecard, os destinatários podem acessá-lo nos painéis do Analytics. Se você fizer alterações subsequentes no Scorecard usando o Construtor de scorecards, elas serão atualizadas automaticamente no Scorecard compartilhado. Os usuários executivos verão as alterações depois de atualizar o Scorecard no aplicativo.

Se você atualizar o Scorecard adicionando novos componentes, convém compartilhar o scorecard novamente (e marcar a opção **[!UICONTROL Compartilhar componentes inseridos]**) para garantir que os usuários executivos tenham acesso a essas alterações.

## Configurar usuários executivos com o aplicativo

Em alguns casos, os usuários executivos podem precisar de assistência adicional para acessar e usar o aplicativo. Esta seção fornece informações para ajudá-lo a prestar essa assistência.

### Ajude os usuários executivos a obter acesso

Para ajudar os usuários executivos a acessar os Scorecards no aplicativo, verifique se:

* Os requisitos mínimos do sistema operacional móvel dos dispositivos são iOS versão 10 ou superior ou Android versão 4.4 (KitKat) ou superior
* Eles possuem um logon válido no Adobe Analytics
* Você criou corretamente os Scorecards para dispositivos móveis para eles e compartilhou esses Scorecards com eles
* Eles têm acesso ao Analysis Workspace e à visualização de dados em que o cartão de pontuação se baseia
* Eles têm acesso aos Componentes incluídos no Scorecard. Observe que é possível selecionar uma opção ao compartilhar os Scorecards para **[!UICONTROL Compartilhar componentes inseridos]**.

### Ajudar os usuários executivos com o aplicativo

Para ajudar usuários executivos:

1. Ajude-os a baixar e instalar o aplicativo. Para fazer isso, estabeleça as seguintes etapas para estender o acesso aos usuários executivos, dependendo se eles usam um dispositivo iOS ou Android.

   **Para usuários executivos no iOS:**

   * Clique no link a seguir (ele também está disponível no Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

      [Link para iOS](https://apple.co/2zXq0aN)
   **Para usuários executivos no Android:**

   * Clique no link a seguir (ele também está disponível no Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (Aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

      [Link do Android](https://bit.ly/2LM38Oo)
   Após o download e a instalação, os usuários executivos podem fazer logon no aplicativo usando suas credenciais atuais do Adobe Analytics. Oferecemos suporte para Adobe ID e Enterprise/Federated ID.

   ![Tela de boas-vindas do aplicativo](assets/welcome.png)

2. Ajude-os a acessar o Scorecard. Depois que os usuários executivos entram no aplicativo, a tela **[!UICONTROL Escolher uma empresa]** é exibida. Essa tela lista as empresas de logon às quais o usuário executivo pertence. Para ajudá-los a chegar ao Scorecard:

   * Toque no nome da empresa de logon ou na Experience Cloud Org que se aplica ao Scorecard que você compartilhou. A lista do Scorecard mostra todos os Scorecards que foram compartilhados com o executivo na empresa de logon.
   * Ajude-os a classificar essa lista pela **[!UICONTROL Modificação mais recente]**, se aplicável.
   * Toque no nome do Scorecard para visualizá-lo.

   ![Escolha uma empresa](assets/accesscard.png)

   Se o usuário executivo fizer logon e vir uma mensagem dizendo que nada foi compartilhado:

   * O usuário executivo pode ter selecionado a instância incorreta do Analytics

   * O Scorecard pode não ter sido compartilhado com o usuário executivo

      ![Nada compartilhado](assets/nothing.png)


   * Verifique se o usuário executivo pode fazer logon na instância correta do Analytics e se o Scorecard foi compartilhado.


3. Explique ao usuário executivo como os blocos aparecem nos cartões de pontuação que você compartilha (o primeiro cartão de pontuação abaixo é definido no modo escuro; consulte **[!UICONTROL Preferências]** abaixo se você achar que o usuário executivo prefere essa opção de visualização):

   ![Explicar blocos](assets/newexplain.png)

   ![Exemplo de scorecard](assets/intro_scorecard.png)

   Informações adicionais sobre blocos:

   * A granularidade dos minigráficos depende da duração do intervalo de datas:
      * Um dia mostra uma tendência horária
      * Mais de um dia e menos de um ano mostra uma tendência diária
      * Um ano ou mais mostra uma tendência semanal
   * A fórmula de alteração do valor percentual é o total da métrica (intervalo de datas atual) - total da métrica (intervalo de datas de comparação) / total da métrica (intervalo de datas de comparação).
   * Você pode puxar a tela para baixo para atualizar o Scorecard.


4. Toque em um bloco para mostrar como funciona um detalhamento minucioso do bloco.

   ![Exibição de detalhamento](assets/sparkline.png)

   * Toque em qualquer ponto em um minigráfico para ver os dados associados a esse ponto na linha.

   * Uma tabela é incluída para exibir dados de dimensões adicionadas ao bloco. Toque na seta para baixo para selecionar dimensões. Se nenhuma dimensão tiver sido adicionada ao bloco, a tabela exibirá os dados do gráfico.

5. Para alterar os intervalos de datas do cartão de pontuação, toque no cabeçalho Data e selecione a combinação de intervalo de datas principal e de comparação que deseja visualizar.

   ![Alterar datas](assets/changedate.png)

6. Para deixar comentários sobre este aplicativo:

   1. Toque no ícone de configurações no canto superior direito da tela do aplicativo.
   2. Na tela **[!UICONTROL Configurações]**, toque na opção **[!UICONTROL Feedback]**.
   3. Toque para ver as opções para deixar comentários.

      ![Tela de configurações](assets/settings.png)

7. Para alterar as preferências, toque na opção **[!UICONTROL Preferências]** mostrada acima. Em preferências, você pode ativar o logon biométrico ou pode definir o aplicativo para o modo escuro, como mostrado abaixo:

   ![Modo escuro](assets/darkmode.png)

**Para relatar um erro**:

Toque na opção e escolha uma subcategoria do erro. No formulário para relatar um erro, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar o relatório, toque no ícone de plano de papel na parte superior direita do formulário.


![Relatar erro](assets/newbug.png)

**Para sugerir uma melhoria**:

Toque na opção e escolha uma subcategoria para a sugestão. No formulário de sugestão, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a sugestão, toque no ícone de plano de papel na parte superior direita do formulário.

**Para fazer uma pergunta**:

Toque na opção e informe o endereço de email no campo superior e a pergunta no campo abaixo. Uma captura de tela é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a pergunta, toque no ícone de plano de papel na parte superior direita do formulário.

>[!IMPORTANT]
>
>Desde outubro de 2020, a Adobe está lançando gradualmente uma série de melhorias para otimizar o desempenho do aplicativo &quot;Painéis do Adobe Analytics&quot;. Essas melhorias se concentram no armazenamento em cache de dados históricos do Analytics que são usados para preencher scorecards com datas (exceto o dia atual). Esses dados serão armazenados em cache por até 24 horas em uma conta de armazenamento na nuvem pública segura do Microsoft Azure. Entre em contato com seu CSM se não quiser aceitar esses recursos de melhoria de desempenho.
