---
title: Introdução à atualização para o Customer Journey Analytics
description: Planeje sua atualização do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 56%

---

# Etapa 1: Introdução à atualização para o Customer Journey Analytics

>[!AVAILABILITY]
>
>As informações nesta página estão sendo substituídas pelas seguintes informações de atualização mais abrangentes: <ul><li>**Etapas de atualização recomendadas**<p>Para obter informações detalhadas, consulte [Caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Guia de Atualização do Customer Journey Analytics**<p>Um novo guia de atualização está disponível e gera dinamicamente etapas de atualização personalizadas para sua organização e suas circunstâncias exclusivas.</p><p>Para acessar o guia pelo Customer Journey Analytics, selecione a guia **[!UICONTROL Workspace]** e clique em **[!UICONTROL Atualizar para o Customer Journey Analytics]** no painel esquerdo. Siga as instruções na tela.</p></li></ul>

O Customer Journey Analytics é a próxima geração de análises. Ele permite coletar dados em vários canais (online e offline) e possui uma eficiente funcionalidade de processamento no tempo do relatório (por meio da definição de componentes e campos derivados em visualizações de dados).

Antes de começar o processo de atualização do Adobe Analytics para o Customer Journey Analytics, você deve entender os benefícios do Customer Journey Analytics, bem como as etapas necessárias para atualizar com êxito.

## Compreender os benefícios do Customer Journey Analytics

Veja a seguir alguns dos principais benefícios: (para obter uma lista abrangente e mais informações sobre cada um desses recursos principais, consulte [Recursos exclusivos do Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Relatórios de vários canais](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  O Customer Journey Analytics possui a habilidade da Experience Platform de armazenar toda espécie de esquemas de dados e tipos. Colete e relate dados de vários canais, como canais digitais (web), sistemas de ponto de venda, dispositivos móveis, sistemas de CRM e muito mais.

* [Transformações de tempo de relatório em visualizações de dados](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  As visualizações de dados no Customer Journey Analytics permitem interpretar ainda mais os dados de uma conexão. É possível alterar ou remover dados sem alterar sua implementação, usar substrings para manipular dimensões, criar métricas a partir de qualquer valor, filtrar subeventos ou usar campos derivados. Todas essas transformações são feitas de maneira não destrutiva. 

* [As transformações se aplicam a dados históricos e novos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  A manipulação da visualização de dados pode ser aplicada a dados históricos e novos de maneira não destrutiva.

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

  Os campos derivados permitem transformações de dados em tempo de relatório. Os dados podem ser combinados, corrigidos ou criados rapidamente, aplicando-se retroativamente a todos os relatórios.

* [As visualizações de dados substituem os conjuntos de relatórios virtuais](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  As visualizações de dados adotam o conceito atual dos conjuntos de relatórios virtuais e o expande para permitir controles adicionais sobre os dados disponibilizados pelas conexões. Essas alterações possibilitam a retroatividade e o ajuste de configurações gerais, como fuso horário e intervalos de tempo limite da sessão. 

* [Dimensões e métricas ilimitadas de cliente](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Os valores podem ser números, texto, objetos, listas ou uma mistura de todos eles. As dimensões podem ser aninhadas ou hierárquicas. 

## Entender o processo de atualização

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
As informações nesta página abordam a Etapa 1 do processo de atualização, conforme destacado na tabela abaixo. Conclua todas as etapas nesta tabela para atualizar do Adobe Analytics para o Customer Journey Analytics.

| Atualizar tarefa | Detalhes |
|---------|----------|
| <span class="preview">**Etapa 1: Introdução à atualização**</span> | <span class="preview">Saiba mais sobre as vantagens de atualizar para o Customer Journey Analytics e o processo básico de atualização.</span> |
| **Etapa 2: [Escolher o caminho de atualização](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Vários métodos estão disponíveis para atualizar para o Customer Journey Analytics. Escolha o método mais adequado de acordo com o ambiente atual do Adobe Analytics e as metas de longo prazo da sua organização. |
| **Etapa 3: [enviar dados à Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere dependendo do caminho de atualização escolhido na Etapa 2. |
| **Etapa 4: [reter dados históricos](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | A maioria das organizações precisa reter dados históricos do Adobe Analytics por um determinado período. Há várias opções disponíveis para fazer isso. |
| **Etapa 5: [executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de atualização, é necessário executar várias tarefas antes que o ambiente do Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às atualizações do Adobe Analytics, bem como às novas implementações do Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Migrar outros dados para a Experience Platform</li><li>Criar conexões entre conjuntos de dados da Platform e o Customer Journey Analytics</li><li>Criar visualizações de dados</li><li>Transferir o uso da API de relatórios</li><li>Contabilizar feeds de dados e data warehouse</li><li>Migrar projetos e componentes</li><li>Planejar a integração de usuários</li></ul> <p>Para mais informações, consulte [Introdução ao Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Primeiro, escolha o caminho de atualização

Vários métodos estão disponíveis para atualizar para o Customer Journey Analytics. [Escolha o método mais apropriado para sua organização](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

O caminho de atualização escolhido depende do ambiente Adobe Analytics atual da sua organização e das metas de longo prazo.
