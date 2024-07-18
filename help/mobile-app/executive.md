---
description: Instruções para usar os scorecards de painéis.
title: Guia executivo de painéis do Analytics
feature: Analytics Dashboards
role: User
exl-id: 12901a76-cb88-45a5-81e9-59fb310328be
solution: Customer Journey Analytics
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 75%

---

# Guia de início rápido do usuário executivo

As informações a seguir fornecem aos usuários executivos informações sobre as práticas recomendadas para usar e exibir painéis do Analytics. Assista a um vídeo demonstrando essas informações:

>[!VIDEO](https://video.tv.adobe.com/v/343460/)

Este manual tem como objetivo ajudar usuários executivos a ler e interpretar cartões de pontuação nos painéis do Analytics. O aplicativo permite que os usuários executivos visualizem uma ampla renderização de importantes dados resumidos de maneira rápida e fácil em seus próprios dispositivos móveis.

## Configure os painéis no seu dispositivo

Para usar os painéis de maneira eficaz, você precisará do curador do Scorecard para ajudar a configurar. Esta seção fornece informações para ajudar a configurar com a assistência do curador.

### Obter acesso

Para acessar os Scorecards nos painéis, verifique se:

* Você tem um logon válido no Customer Journey Analytics
* O curador criou corretamente os Scorecards para dispositivos móveis e os compartilhou com você

### Painéis de download e instalação

Para baixar e instalar o aplicativo, siga as etapas de acordo com o sistema operacional do dispositivo.

>[!NOTE]
>
>Embora o aplicativo móvel seja chamado de painel do Adobe Analytics na loja de aplicativos, ele pode ser usado igualmente com cartões de pontuação móveis Customer Journey Analytics.

**Para usuários executivos no iOS:**

Clique no link a seguir (ele também está disponível no Customer Journey Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

[Link para iOS](https://apple.co/2zXq0aN)

**Para usuários executivos no Android:**

Clique no link a seguir (ele também está disponível no Customer Journey Analytics em **[!UICONTROL Ferramentas]** > **[!UICONTROL Painéis do Analytics (aplicativo móvel)]**) e siga as instruções para baixar, instalar e abrir o aplicativo:

[Link do Android](https://bit.ly/2LM38Oo)

Após o download e a instalação, os usuários executivos podem fazer logon no aplicativo usando suas credenciais de Customer Journey Analytics existentes.

![tela de boas-vindas do aplicativo Customer Journey Analytics](assets/welcome.png)

## Usar painéis {#use-dashboards}

Para usar painéis:

1. Faça logon no aplicativo. A tela de logon será exibida ao iniciar os painéis. Siga as instruções usando suas credenciais de Customer Journey Analytics existentes. Oferecemos suporte para Adobe ID e Enterprise/Federated ID.

   ![Sequência de logon](assets/signseq.png)

1. Escolha uma empresa. Efetuado o logon nos painéis, a tela **[!UICONTROL Escolha uma empresa]** é exibida. Esta tela lista as empresas de logon às quais você pertence. Toque no nome da empresa associado ao cartão de pontuação compartilhado com você.

   A lista de scorecards mostra todos os scorecards compartilhados com você.

1. Toque no cartão de pontuação que deseja exibir.

   Se você tiver acesso a mais de uma organização em um logon, todos os scorecards de suas organizações estarão disponíveis na lista de scorecards.

   Você pode classificar a lista de cartões de pontuação de acordo com o título do cartão de pontuação, o nome da organização ou a visualização mais recente. Você pode até mesmo pesquisar por um scorecard específico.

   ![Escolha uma empresa](assets/mobile-home-screen.png)

   Se você fizer logon e vir uma mensagem informando que nada foi compartilhado, verifique o seguinte com o curador:

   * Você pode fazer logon na sandbox Customer Journey Analytics correta.
   * O Scorecard foi compartilhado com você.

   ![Nada compartilhado](assets/nothing.png)

1. Analisar como os blocos aparecem no Scorecard (o primeiro Scorecard é mostrado no modo escuro; consulte **[!UICONTROL Preferências]** abaixo para obter mais informações).

   ![Explicação dos blocos](assets/newexplain.png)

   Informações adicionais sobre blocos:

   * A granularidade dos minigráficos depende da duração do intervalo de datas:

      * Um dia mostra uma tendência horária
      * Mais de um dia e menos de um ano mostra uma tendência diária.
      * Um ano ou mais mostra uma tendência semanal.

   * A fórmula de alteração do valor percentual é o total da métrica (intervalo de datas atual) - total da métrica (intervalo de datas de comparação) / total da métrica (intervalo de datas de comparação).

   * Você pode puxar a tela para baixo para atualizar o Scorecard.

   O exemplo de Scorecard a seguir é mostrado no modo normal:

   ![Exemplo de scorecard](assets/intro_scorecard.png)

1. Toque em um bloco para mostrar como funciona um detalhamento minucioso do bloco.

   ![Exibição de detalhamento](assets/sparkline.png)


1. Para alterar os intervalos de datas do Scorecard:

   ![Alterar datas](assets/changedate.png)

   * Você também pode alterar os intervalos de datas na exibição de Detalhamento mostrada acima da mesma maneira.

   * Dependendo do intervalo em que você tocar (**Dia**, **Semana**, **Mês** ou **Ano**), você verá duas opções para os intervalos de datas - o período de tempo atual ou o imediatamente anterior. Toque em uma dessas duas opções para selecionar o primeiro intervalo. Na lista **[!UICONTROL COMPARAR COM]**, toque em uma das opções apresentadas para comparar os dados desse período com o primeiro intervalo de datas selecionado. Toque em **[!UICONTROL Concluído]** no canto superior direito da tela. O campo **[!UICONTROL Intervalos de datas]** e os blocos de Scorecard são atualizados com os novos dados de comparação dos novos intervalos selecionados.

1. Para aplicar um filtro de segmento ao Scorecard, toque na lista suspensa de filtros e selecione um segmento que foi configurado pelo curador. [Os Filtros](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html?lang=pt-BR) no aplicativo funcionam da mesma forma que no Workspace.

   ![Filtro de segmentos](assets/segment_filter.png)

1. Obter atualizações do Scorecard. Se um Scorecard não incluir todas as métricas ou detalhamentos em que você possa estar interessado, entre em contato com a equipe de Customer Journey Analytics para atualizar o Scorecard. Depois da atualização, puxe o cartão para baixo na tela para atualizá-lo e carregar os dados adicionados recentemente.

1. Para deixar comentários sobre este aplicativo:

   1. Toque no ícone de configurações no canto superior direito da tela do aplicativo.
   2. Na tela **[!UICONTROL Configurações]**, toque na opção **[!UICONTROL Feedback]**.
   3. Toque para ver as opções para deixar comentários.

      ![Tela de configurações](assets/settings.png)

1. Para alterar as preferências, toque na opção **[!UICONTROL Preferências]** mostrada acima. Em preferências, você pode ativar o logon biométrico ou pode definir o aplicativo para o modo escuro, como mostrado abaixo:

   ![Modo escuro](assets/darkmode.png)


**Para relatar um erro**:

Toque na opção e escolha uma subcategoria do erro. No formulário para relatar um erro, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar o relatório, toque no ícone de plano de papel na parte superior direita do formulário.

![Relatar erro](assets/newbug.png)

**Para sugerir uma melhoria**:

Toque na opção e escolha uma subcategoria para a sugestão. No formulário de sugestão, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a sugestão, toque no ícone de plano de papel na parte superior direita do formulário.

**Para fazer uma pergunta**:

Toque na opção e informe o endereço de email no campo superior e a pergunta no campo abaixo. Uma captura de tela é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a pergunta, toque no ícone de plano de papel na parte superior direita do formulário.

## Glossário de termos

| Termo | Definição |
|--- |--- |
| Consumidor | Usuário executivo que visualiza os insights e as métricas principais do Customer Journey Analytics em um dispositivo móvel |
| Curador | Usuário com conhecimento de dados que encontra e distribui insights do Customer Journey Analytics e configura os Scorecards para serem visualizados pelo consumidor |
| Preparação | O ato de criar ou editar um scorecard para dispositivos móveis com métricas, dimensões e outros componentes relevantes para o consumidor |
| Scorecard | Uma exibição de painéis que contém um ou mais blocos |
| Bloco | Uma renderização para uma métrica em uma Exibição de scorecard |
| Detalhamento | Uma exibição secundária acessível ao tocar em um bloco no Scorecard. Essa exibição é expandida na métrica mostrada no bloco e, opcionalmente, relata as dimensões adicionais de detalhamento |
| Intervalo de datas | O intervalo de datas principal dos relatórios de painéis |
| Intervalo de datas de comparação | O Intervalo de datas comparado ao intervalo de datas principal |
