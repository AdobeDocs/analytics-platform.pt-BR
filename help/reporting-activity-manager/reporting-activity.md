---
title: Exibir atividade de relatórios no Gerenciador de atividades de relatórios
description: Saiba mais sobre como usar o Gerente de atividade de relatórios para diagnosticar e corrigir problemas de capacidade durante o pico dos relatórios.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 9c76b7c9f5f99da70b5c097a11cfb4cfd1370e9f
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 13%

---

# Exibir atividade de relatórios no Gerenciador de atividades de relatórios

A variável [!UICONTROL Gerenciador de atividades de relatórios] O permite que os administradores diagnostiquem e corrijam rapidamente os problemas de capacidade dos relatórios durante o pico dos relatórios.

Para obter mais informações sobre o Gerente de atividades de relatórios, incluindo os principais benefícios e requisitos de permissão, consulte [Visão geral do Gerenciador de atividades de relatórios](/help/reporting-activity-manager/reporting-activity-overview.md).

## Exibir atividade de relatório para todas as conexões {#view-all-report-suites}

1. No Customer Journey Analytics, acesse **[!UICONTROL Ferramentas]** > **[!UICONTROL Gerenciador de atividades de relatórios]**.

   Uma lista de suas conexões base ativadas é exibida.

   ![fila de relatórios](assets/reporting-activity1.png)

1. (Opcional) É possível pesquisar ou filtrar a lista de conexões:

   * Use o campo de pesquisa para procurar uma conexão específica. Comece a digitar o nome ou ID da conexão e a lista de conexões será atualizada conforme você digitar.

   * Selecione o [!UICONTROL **Filtro**] ícone ![Ícone Filtrar](assets/filter-icon.png) para expandir a lista de opções de filtro. Você pode filtrar por [!UICONTROL **Favoritos**] ou [!UICONTROL **Status**].

     Para marcar uma conexão como favorita, selecione o ícone de estrela à esquerda do nome da conexão.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Exibir informações de utilização sobre cada conexão. Você pode selecionar um cabeçalho de coluna para classificar a tabela por essa coluna.

   As seguintes colunas estão disponíveis:

   | Elemento da interface | Descrição |
   | --- | --- |
   | **[!UICONTROL Conexão]** | A conexão cuja atividade de relatório você está monitorando. |
   | **[!UICONTROL Visualizações de dados]** | Mostra todas as visualizações de dados que usam a conexão. A configuração da visualização de dados pode adicionar complexidade às solicitações de relatórios. |
   | **[!UICONTROL Utilização da capacidade]** | A porcentagem da capacidade de relatório da conexão que está sendo usada, em tempo real. <p>**Nota** Uma capacidade de uso de 100% não necessariamente sugere que você deve começar a cancelar imediatamente as solicitações de relatórios. A capacidade de uso de 100% pode estar íntegra se o tempo médio de espera for razoável. Por outro lado, a capacidade de uso de 100% pode sugerir um problema se o número de solicitações em fila também estiver crescendo.</p> |
   | **[!UICONTROL Solicitações na fila]** | O número de solicitações aguardando para serem processadas. <!-- ??? --> |
   | **[!UICONTROL Tempo de espera na fila]** | O tempo médio de espera antes do início do processamento das solicitações. <!-- ???? --> |
   | **[!UICONTROL Status]** | Os status possíveis são: <ul><li>[!UICONTROL **Ativo**] (azul): os relatórios foram executados na conexão e a atividade dele está sendo monitorada.</li><li>[!UICONTROL **Inativo**] (cinza): nenhum relatório foi executado na conexão. Esse status é exibido somente quando as conexões são criadas pela primeira vez.</li></ul> |

   {style="table-layout:auto"}

## Exibir atividade de relatórios para uma única conexão

1. No Customer Journey Analytics, selecione [!UICONTROL **Ferramentas**] > [!UICONTROL **Gerenciador de atividades de relatórios**].

1. Selecione o título vinculado da conexão para a qual deseja exibir detalhes.

   Os dados de atividade de relatórios são exibidos para a conexão selecionada.

1. (Opcional) Quando uma conexão é carregada pela primeira vez no Gerenciador de atividades de relatórios, os dados exibidos representam as métricas de utilização atuais. Para ver as métricas atualizadas após o carregamento inicial, selecione o [!UICONTROL **Atualizar**] botão para atualizar manualmente a página.

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. Use os gráficos e tabelas disponíveis para entender a atividade de relatórios na conexão.

   * [Visualizar gráficos](#view-graphs)

   * [Exibir tabela](#view-table)

### Visualizar gráficos

Os gráficos a seguir estão disponíveis para ajudá-lo a entender melhor a atividade que ocorre na conexão.

Se os gráficos não estiverem visíveis, selecione a variável [!UICONTROL **Mostrar gráficos**] botão.

#### Gráfico de utilização {#utilization}

O gráfico Utilização mostra a utilização de relatórios da conexão selecionada nas últimas 2 horas.

Passe o mouse sobre o gráfico para ver os pontos no tempo em que a porcentagem de capacidade de uso foi mais alta naquele minuto.

* **Eixo X**: a capacidade de uso de relatórios nas últimas 2 horas.
* **Eixo Y**: a porcentagem da capacidade de uso do relatório, por minuto.

  ![gráfico de utilização](assets/utilization-graph.png)

#### Gráfico de usuários distintos

O gráfico Usuários distintos mostra a atividade de relatórios da conexão selecionada nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de usuários foi mais alto naquele minuto.

* **Eixo X**: a atividade de relatórios no período das últimas 2 horas.
* **Eixo Y**: o número de usuários que fizeram solicitações de relatórios, por minuto.

  ![Gráfico de usuários distintos](assets/distinct-users-graph.png)

#### Gráfico de solicitações

O gráfico Solicitações mostra o número de solicitações processadas e em fila para a conexão selecionada nas últimas 2 horas.

Passe o mouse sobre o gráfico para visualizar os pontos no tempo em que o número máximo de solicitações foi mais alto naquele minuto.

* **Eixo X**: o número de solicitações processadas e enfileiradas durante o último período de 2 horas.
* **Eixo Y**: o número de solicitações processadas (em verde) e solicitações em fila (em roxo), por minuto.

  ![Gráfico de usuários distintos](assets/requests-graph.png)

#### Gráfico de enfileiramento

O gráfico Enfileiramento mostra o tempo médio de espera da fila (em segundos) para as solicitações de relatório da conexão selecionada nas últimas 2 horas.

Passe o mouse sobre o gráfico para exibir os pontos no tempo em que o tempo médio máximo de espera foi mais alto para esse minuto.

* **Eixo X**: o tempo médio de espera da fila para solicitações de relatórios nos últimos 2 horas.
* **Eixo Y**: o tempo médio de espera (em segundos).

  ![Gráfico de usuários distintos](assets/queueing-graph.png)

### Exibir tabela {#view-table}

Ao exibir a tabela, considere o seguinte:

* Você pode optar por exibir dados escolhendo qualquer uma das seguintes tabs na parte superior da tabela de dados: [!UICONTROL **Solicitação**], [!UICONTROL **Usuário**], [!UICONTROL **Projeto**] ou [!UICONTROL **Aplicativo**].

* Você pode pesquisar ou filtrar a lista de conexões:

   * Use o campo de pesquisa para procurar uma conexão específica. Comece a digitar o nome ou ID da conexão e a lista de conexões será atualizada conforme você digitar.

   * Selecione o [!UICONTROL **Filtro**] ícone ![Ícone Filtrar](assets/filter-icon.png) para expandir a lista de opções de filtro. Você pode filtrar por [!UICONTROL **Status**], [!UICONTROL **Complexo**], [!UICONTROL **Aplicativo**], [!UICONTROL **Usuário**] ou [!UICONTROL **Projeto**].

   * É possível selecionar [!UICONTROL **Ocultar gráficos**] para mostrar somente a tabela.

![guias de tabela](assets/report-activity-tabs.png)

#### Exibir dados por solicitação

Ao selecionar a variável [!UICONTROL **Solicitação**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **ID da solicitação**] | Um identificador exclusivo que pode ser usado para fins de solução de problemas. Para copiar o ID, selecione a solicitação e, em seguida, selecione a opção, [!UICONTROL **Copiar IDs de solicitação**]. |
| [!UICONTROL **Tempo de execução**] | Por quanto tempo a solicitação está em execução. |
| [!UICONTROL **Hora de início**] | Quando a solicitação iniciou o processamento (com base no horário local do administrador). |
| [!UICONTROL **Tempo de espera**] | Por quanto tempo a solicitação está aguardando antes de ser processada. Esse valor geralmente está em &quot;0&quot; quando há capacidade suficiente. |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 2.0</li><li>Alertas inteligentes<li>Exportação de tabela completa</li><li>Compartilhar com qualquer pessoa através de links</li><li>Análise guiada</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></li></ul><p>**Nota:** Se o valor dessa coluna for [!UICONTROL **Desconhecido**], isso significa que os metadados da solicitação não estão disponíveis para o usuário.</p> |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. <p>**Nota:** Se o valor dessa coluna for [!UICONTROL **Desconhecido**], isso significa que os metadados da solicitação não estão disponíveis para o usuário.</p> |
| [!UICONTROL **Projeto**] | Nomes de projeto salvos do Espaço de trabalho, IDs de relatório da API etc. (Os metadados podem variar em vários aplicativos.)<p>**Nota:** Se o valor dessa coluna for [!UICONTROL **Desconhecido**], isso significa que o projeto não foi salvo ou que os metadados da solicitação não estão disponíveis para o usuário.</p> |
| [!UICONTROL **Status**] | Indicadores de status: <ul><li>**Em execução**: a solicitação está sendo atualmente processada.</li><li>**Pendente**: a solicitação está aguardando para ser processada.</li></ul> |
| [!UICONTROL **Complexidade**] | Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação. <p>Os valores possíveis incluem:</p> <ul><li>[!UICONTROL **Baixa**]</li><li>[!UICONTROL **Médio**]</li><li>[!UICONTROL **Alta**]</li></ul>Esse valor é influenciado pelos valores nas seguintes colunas:<ul><li>[!UICONTROL **Limites do mês**]</li><li>[!UICONTROL **Colunas**]</li><li>[!UICONTROL **Segmentos**]</li></ul> |
| [!UICONTROL **Limites do mês**] | O número de meses incluídos em uma solicitação. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Colunas**] | O número de métricas e divisões na solicitação. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Segmentos**] | O número de segmentos aplicados à solicitação. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por usuário

Ao selecionar a variável [!UICONTROL **Usuário**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Usuário**] | O usuário que iniciou a solicitação. Se o valor dessa coluna for [!UICONTROL **Não reconhecido**], isso significa que o usuário está em uma empresa de logon na qual você não tem permissões administrativas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações iniciadas pelo usuário. |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao usuário. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 2.0</li><li>Alertas inteligentes<li>Exportação de tabela completa</li><li>Compartilhar com qualquer pessoa através de links</li><li>Análise guiada</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações iniciadas pelo usuário. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por projeto

Ao selecionar a variável [!UICONTROL **Projeto**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Projeto**] | O projeto em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao projeto. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao projeto. <!-- ??? --> |
| [!UICONTROL **Aplicativo**] | Os aplicativos compatíveis com o [!UICONTROL Gerenciador de Atividades de relatórios] são: <ul><li>Interface do Analysis Workspace</li><li>Projetos agendados do Espaço de trabalho.</li><li>Report Builder</li><li>Interfaces do construtor: segmento, métricas calculadas, anotações, públicos etc.</li><li>Chamadas de API da API 2.0</li><li>Alertas inteligentes<li>Exportação de tabela completa</li><li>Compartilhar com qualquer pessoa através de links</li><li>Análise guiada</li><li>Qualquer outro aplicativo que consulte o mecanismo de relatórios do Analytics</li></li></ul> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações incluídas no projeto. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p><ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

#### Exibir dados por aplicativo

Ao selecionar a variável [!UICONTROL **Aplicativo**] , as seguintes colunas estão disponíveis na tabela:

| Coluna | Descrição |
| --- | --- |
| [!UICONTROL **Aplicativo**] | O aplicativo em que as solicitações foram iniciadas. |
| [!UICONTROL **Número de solicitações**] | O número de solicitações associadas ao aplicativo. |
| [!UICONTROL **Número de usuários**] | O número de usuários associados ao aplicativo. <!--???--> |
| [!UICONTROL **Número de projetos**] | O número de projetos associados ao aplicativo. <!--???--> |
| [!UICONTROL **Complexidade média**] | A complexidade média das solicitações associadas ao aplicativo. <p>Nem todas as solicitações exigem o mesmo tempo para serem processadas. A complexidade da solicitação pode ajudar a fornecer uma ideia geral sobre o tempo necessário para processar a solicitação.</p><p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:</p>O valor desta coluna é baseado em uma pontuação determinada pelos valores das seguintes colunas:<ul><li>[!UICONTROL **Média de limites mensais**]</li><li>[!UICONTROL **Média de colunas**]</li><li>[!UICONTROL **Média de segmentos**]</li></ul> |
| [!UICONTROL **Média de limites mensais**] | O número médio de meses incluídos nas solicitações. Mais limites de mês aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de colunas**] | O número médio de métricas e detalhamentos nas solicitações incluídas. Mais colunas aumentam a complexidade da solicitação. |
| [!UICONTROL **Média de segmentos**] | O número médio de segmentos aplicados às solicitações incluídas. Mais segmentos aumentam a complexidade da solicitação. |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
