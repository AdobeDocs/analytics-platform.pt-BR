---
description: Obtenha alertas quando os componentes do projeto atingirem determinados limites.
title: Criar alertas (Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 8f866d47ef0caccb91bd0e9cb9043bb1e16e0d89
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 21%

---

# Criar alertas

>[!NOTE]
>
>Os Alertas inteligentes estão disponíveis para todos os clientes. No entanto, para usar a Detecção de anomalias em Alertas inteligentes, você deve ter o Customer Journey Analytics Select, Prime ou Ultimate.

Os Alertas inteligentes (ou apenas &quot;alertas&quot;) no Customer Journey Analytics permitem que você seja notificado imediatamente quando ocorrerem eventos anormais em seus dados.

Para obter informações mais detalhadas sobre a visão geral dos Alertas inteligentes, consulte [Visão geral dos Alertas inteligentes](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md).

Para criar um alerta:

1. Comece a criar um alerta acessando o criador de alertas. Você pode acessar o criador de alertas de qualquer uma das seguintes maneiras:

   * Abra um projeto no Analysis Workspace e selecione **[!UICONTROL Componentes]** > **[!UICONTROL Criar alerta]**.
   * Abra um projeto no Analysis Workspace e use o seguinte atalho:

     `ctrl (or cmd) + shift + a`
   * Abra um projeto no Analysis Workspace, selecione um ou mais itens de linha em uma tabela de forma livre, clique com o botão direito do mouse e selecione **[!UICONTROL Criar alerta a partir da seleção]**.

     Essa ação preenche o criador de alertas automaticamente para criar um alerta com as métricas e filtros corretos.
   * No Customer Journey Analytics, selecione **[!UICONTROL Componentes]** > [!UICONTROL **Alertas**] > **[!UICONTROL Criar novo alerta]**.

   O criador de alertas é exibido. Essa interface é semelhante àquela que cria segmentos ou métricas calculadas no Analytics:

   ![](assets/alert-builder.png)

1. Especifique as seguintes opções para configurar o alerta:

   | Opção | Descrição |
   |---------|----------|
   | [!UICONTROL **Título**] | Especifique um nome para o alerta. O nome do alerta pode conter o nome do relatório ou o limite da métrica. |
   | [!UICONTROL **Descrição (opcional)**] | Especifique uma descrição para o alerta. |
   | [!UICONTROL **Granularidade de tempo**] | Selecione a frequência com que deseja verificar a métrica: diariamente, semanalmente ou mensalmente.<p><b>Observação:</b>Para exibições de dados com um calendário personalizado, não oferecemos suporte à granularidade mensal no Criador de alertas.<!--true?--></p> |
   | [!UICONTROL **Destinatários**] | Especifique para onde o alerta pode ser enviado. Um alerta pode ser enviado a um usuário do Analytics, a um grupo do Analytics, a um endereço de email bruto ou a um número de telefone.<p><b>Importante:</b>O número de telefone deve ser precedido por um &quot;+&quot; e um [código do país](https://countrycode.org/).</p><p>O email que um usuário recebe depois que um alerta é acionado é semelhante a:</p><p>![Email de alerta](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **Data de expiração**] | Defina a data e a hora em que deseja que o alerta expire. |
   | [!UICONTROL **Atraso**] | O tempo necessário antes que os dados sejam concluídos e estejam disponíveis para serem relatados em Customer Journey Analytics varia de acordo com a organização, normalmente variando de 3 a 9 horas depois do tempo do evento de dados. Para que os alertas sejam precisos, os dados de evento para um determinado intervalo de eventos devem ser completos, o que significa que o Adobe não está mais recebendo dados de evento para o intervalo de eventos especificado.<p>Para levar em conta esse atraso no tempo de assimilação, os alertas têm um atraso padrão de 9 horas antes de serem enviados.</p><p>Você pode ajustar o atraso padrão de 9 horas para qualquer valor entre 0 e 24 horas. No entanto, diminuir o atraso para menos de 9 horas pode significar que você está relatando dados incompletos, o que resulta em informações de alerta imprecisas.</p><p>Considere o seguinte ao diminuir o tempo de atraso:</p><ul><li>**Entenda a disponibilidade dos dados versus a integridade dos dados**: embora alguns dados possam estar disponíveis para relatórios antes, todos os dados em lote são assimilados em um conjunto de dados da Platform somente após um período de 3 a 9 horas. Para que os alertas sejam precisos, a assimilação de dados deve ser completa, com todos os dados em lote disponíveis no conjunto de dados.</li><li>**Determine quanto tempo leva para que seus dados sejam completos e estejam disponíveis no conjunto de dados**: os tempos de assimilação de dados diferem de acordo com a organização. Verifique se o tempo de atraso escolhido para a entrega de alertas é o mesmo ou menos frequente do que o tempo necessário para que os dados em lote fiquem disponíveis no conjunto de dados da plataforma <!--add link? -->.</li><p>**Dica:** a maneira mais precisa de saber o tempo necessário para que todos os dados em lote sejam concluídos e assimilados no conjunto de dados da plataforma é consultar os engenheiros de dados em sua organização.</p><p>Como alternativa, você pode ter uma ideia geral de quanto tempo leva para que a entrega em lote em sua organização fique disponível no conjunto de dados da Plataforma criando a seguinte tabela de forma livre no Analysis Workspace:</p><ol><li>Em uma tabela de forma livre no Analysis Workspace, adicione uma métrica [!UICONTROL **Eventos**] e uma dimensão [!UICONTROL **Dia**].</li><li>Detalhe a dimensão [!UICONTROL **Dia**] usando uma dimensão [!UICONTROL **Horas**].<p>Horas que não têm dados serão exibidas como 0.</p></li></ol><li>**Contabilize erros em seus cálculos**: se você diminuir o tempo de atraso padrão, recomendamos configurar o atraso por pelo menos uma hora a mais do que o tempo necessário à organização para a integridade da assimilação de dados. Por exemplo, se houver um atraso de 3 horas antes da conclusão da assimilação de dados, você deverá definir o atraso como 4 horas.</li></ul><p>Para obter mais informações, consulte [Os tempos de assimilação de dados variam em Customer Journey Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics) no artigo [Comparação de recursos de Alertas inteligentes: Customer Journey Analytics e Adobe Analytics](/help/analysis-workspace/c-intelligent-alerts/alerts-feature-comparison.md). |
   | [!UICONTROL **Enviar um alerta quando**] | [!UICONTROL **Qualquer uma destas métricas aciona**]: arraste e solte métricas (incluindo métricas calculadas) aqui para criar acionadores para o alerta.<p>Uma mensagem **&quot;componentes incompatíveis&quot;** será exibida se nem todas as métricas, dimensões ou segmentos no alerta forem compatíveis com a exibição de dados selecionada no momento.</p><p>Determine o limite que a métrica deve exceder antes de definir um alarme. Você pode definir este valor para um limite e, em seguida, para uma das condições a seguir:</p><ul><li>a anomalia existe</li><li>a anomalia está acima do esperado</li><li>a anomalia está abaixo do esperado</li><li>é igual ou maior que</li><li>é igual ou menor que</li><li>alterações por</li><li>Você pode definir um limite de 90%, 95%, 99%, 99,75% e 99,9%.</li></ul><p>[!UICONTROL **Com todos esses filtros**]: arraste e solte segmentos ou dimensões para adicionar filtros. Por exemplo, adicionar um segmento &quot;Somente dispositivos móveis&quot; significaria que a regra seria acionada somente para dispositivos móveis. Você pode adicionar filtros extras usando uma instrução AND. Você pode adicionar regras AND ou OR, clicando no ícone de engrenagem.</p><p>Consulte [Alertas inteligentes - casos de uso](/help/analysis-workspace/c-intelligent-alerts/alerts-use-cases.md), por exemplo, casos de uso.</p> |
   | [!UICONTROL **Pré-visualizar**] | A visualização de alertas interativa mostra a frequência de disparo aproximada de um alerta com base na experiência passada.<p>Por exemplo, se você definir a granularidade de tempo para diário, a visualização pode informar se o alarme foi disparado para uma determinada métrica x vezes durante os últimos 30 ou 31 dias.</p><p>Se achar que muitos alertas podem ter sido disparados, você pode ajustar o limite no [Gerenciador de alertas](/help/analysis-workspace/c-intelligent-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Selecione [!UICONTROL **Salvar**].

