---
title: Introdução à migração para o Customer Journey Analytics
description: Planeje a migração do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: 21d77f06595993172460b724dc7991cb9a5a02a8
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 8%

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
Essa página representa a Etapa 1 da migração, conforme mostrado na tabela a seguir. Conclua todas as etapas desta tabela para migrar do Adobe Analytics para o Customer Journey Analytics.

| Tarefa | Detalhes |
|---------|----------|
| **Etapa 1: [Introdução à migração](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Saiba mais sobre os benefícios da migração para o Adobe Analytics e o processo de migração básico. |
| **Etapa 2: [Escolha o método de migração](/help/getting-started/cja-migration/cja-migration-method.md)** | Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. Escolha o método que é melhor para sua organização, levando em consideração o ambiente Adobe Analytics atual da organização e suas metas de longo prazo. |
| **Etapa 3: [Enviar dados para o Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | O processo de envio de dados para o Adobe Experience Platform difere, dependendo do método de migração escolhido na Etapa 1. |
| **Etapa 4: [Mapear dados para o esquema XDM](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [Esquemas XDM](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) são usados no Adobe Experience Platform para descrever a estrutura dos dados de forma consistente e reutilizável. Ao definir os dados de forma consistente em todos os sistemas, fica mais fácil manter o significado e, portanto, obter valor dos dados.<p>A maioria dos métodos de migração exige a criação de um novo esquema XDM ou o mapeamento do esquema existente do Adobe Analytics para o XDM usando o mapeamento do fluxo de dados.</p> |
| **Etapa 5: [Reter dados históricos](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | A maioria das organizações precisa manter seus dados históricos do Adobe Analytics por um determinado período. Várias opções estão disponíveis para fazer isso. |
| **Etapa 6: [Planejar a integração do usuário](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Você deve dar aos seus usuários tempo suficiente (de 3 a 6 meses) para se familiarizar com as principais diferenças do Analysis Workspace no Customer Journey Analytics. |
| **Etapa 7: [Portar o uso da API de relatórios](/help/getting-started/cja-migration/cja-migration-api.md)** | A API de relatórios de Customer Journey Analytics está no mesmo formato, mas usa um endpoint diferente. Porte o uso da API de relatórios da API de relatórios do Adobe Analytics para a API de relatórios do Customer Journey Analytics. |
| **Etapa 8: [Substituir Feeds de dados e Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Decida como você usará as opções de exportação disponíveis no Customer Journey Analytics para substituir os Feeds de dados e os recursos do Data Warehouse que você estava usando no Adobe Analytics. |
| **Etapa 9: [Migrar projetos e componentes](/help/getting-started/cja-migration/cja-migration-projects.md)** | A área Migração de componentes no Adobe Analytics permite migrar projetos e seus componentes associados do Adobe Analytics para o Customer Journey Analytics. |
| **Etapa 10: [Executar tarefas de pós-migração](/help/getting-started/cja-getting-started.md)** | Após concluir a migração, é necessário executar várias tarefas, incluindo trazer outros dados para o Experience Platform, criar conexões entre conjuntos de dados da plataforma e o Customer Journey Analytics, criar visualizações de dados e aprender a criar relatórios sobre dados entre canais no Analysis Workspace. |

{style="table-layout:auto"}

## Primeiro, escolha o método de migração

Vários métodos estão disponíveis para migrar para o Customer Journey Analytics. [Escolha o método que é melhor para sua organização](/help/getting-started/cja-migration/cja-migration-method.md).

O método de migração escolhido depende do ambiente Adobe Analytics atual da sua organização e das metas de longo prazo.
