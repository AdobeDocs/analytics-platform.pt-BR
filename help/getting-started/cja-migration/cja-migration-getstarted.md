---
title: Introdução à migração para o Customer Journey Analytics
description: Planeje a migração do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: d734e5daf9b5c9a559c0390622ab5aa15f2aa7a2
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 10%

---

# Etapa 1: Introdução à migração para o Customer Journey Analytics

O Customer Journey Analytics é a próxima geração de análises. Ele permite a coleta de dados em vários canais (dados online e offline), combinada com uma eficiente funcionalidade de processamento no tempo do relatório (por meio da definição de componentes e campos derivados em visualizações de dados).

Antes de começar o processo de migração do Adobe Analytics para o Customer Journey Analytics, você deve entender os benefícios do Customer Journey Analytics, bem como as etapas necessárias para uma migração bem-sucedida.

## Compreender os benefícios do Customer Journey Analytics

A seguir estão alguns dos principais benefícios: (Para obter uma lista abrangente e mais informações sobre cada um desses recursos principais, consulte [Recursos disponíveis somente no Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).)

* [Relatórios de vários canais](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  O Customer Journey Analytics possui a habilidade da Experience Platform de armazenar toda espécie de esquemas de dados e tipos. Colete e relate dados de vários canais, como digitais (Web), sistemas de ponto de venda, dispositivos móveis, sistemas de CRM e muito mais.

* [Transformações de tempo do relatório em visualizações de dados](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  As visualizações de dados no Customer Journey Analytics permitem interpretar ainda mais os dados de uma conexão. É possível alterar ou remover dados sem alterar a implementação, usar substrings para manipular dimensões, criar métricas de qualquer valor, filtrar subeventes ou usar campos derivados. Todas essas transformações não são destrutivas.

* [As transformações se aplicam aos dados históricos e novos](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  A manipulação da Visualização de dados pode ser aplicada a dados históricos e novos de maneira não destrutiva.

* [Campos derivados](/help/data-views/derived-fields/derived-fields.md)

  Os campos derivados permitem transformações no tempo do relatório para seus dados. Os dados podem ser combinados, corrigidos ou criados rapidamente, aplicando-se retroativamente a todos os relatórios.

* [As visualizações de dados substituem os conjuntos de relatórios virtuais](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  As Visualizações de dados seguem o conceito de conjuntos de relatórios virtuais como eles existem hoje e os expande para ativar controles adicionais nos dados disponibilizado por conexões. Essas alterações fazem com que configurações gerais, como fuso horário e intervalos de tempo limite da sessão, sejam configuráveis e retroativas.

* [Dimensões e métricas ilimitadas de cliente](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  Os valores podem ser numéricos, texto, objetos, listas ou misturas de todos. Dimension pode ser aninhado ou hierárquico.

## Entender o processo de migração

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
As informações nesta página abordam a Etapa 1 da migração, conforme destacado na tabela abaixo. Conclua todas as etapas desta tabela para migrar do Adobe Analytics para o Customer Journey Analytics.

| Tarefa de migração | Detalhes |
|---------|----------|
| <span class="preview">**Etapa 1: Introdução à migração**</span> | <span class="preview">Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico.</span> |
| **Etapa 2: [Escolha o caminho de migração](/help/getting-started/cja-migration/cja-migration-path.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, dependendo do ambiente Adobe Analytics atual da organização e das metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do caminho de migração escolhido na Etapa 2. |
| **Etapa 4: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 5: [Executar tarefas de implementação adicionais](/help/getting-started/cja-getting-started.md)** | Nesse ponto do processo de migração, é necessário executar várias tarefas antes que o ambiente de Customer Journey Analytics esteja pronto para uso.<p>Essas tarefas adicionais se aplicam às migrações do Adobe Analytics, bem como às novas implementações de Customer Journey Analytics.</p><p>Essas tarefas incluem:</p><ul><li>Trazendo outros dados para o Experience Platform</li><li>Criação de conexões entre conjuntos de dados da plataforma e Customer Journey Analytics</li><li>Criação de visualizações de dados</li><li>Transferência do uso da API de relatórios</li><li>Contabilização de feeds de dados e Data Warehouse</li><li>Migração de projetos e componentes</li><li>Integração do usuário do Planning</li></ul> <p>Para obter mais informações, consulte [Customer Journey Analytics Introdução](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## Primeiro, escolha o caminho de migração

Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. [Escolha o método que é melhor para sua organização](/help/getting-started/cja-migration/cja-migration-path.md).

O caminho de migração escolhido depende do ambiente Adobe Analytics atual da sua organização e das metas de longo prazo.
