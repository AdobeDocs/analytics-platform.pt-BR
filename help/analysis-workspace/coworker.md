---
title: Analisar e construir projetos do Workspace com o parceiro de trabalho
description: Use a experiência no produto para o Colaborador resumir o projeto aberto, encontrar insights e criar painéis, tabelas e segmentos a partir de prompts em linguagem natural.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 88e67c92fc170b340149c9ab73ad5eea2122da2b
workflow-type: tm+mt
source-wordcount: '1960'
ht-degree: 1%
---
# Usar a experiência no produto para o Colaborador

>[!AVAILABILITY]
>
>A funcionalidade descrita nesta seção está na fase de teste limitado da versão e pode não estar disponível ainda em seu ambiente. Além disso, o Co-worker usa IA gerativa, que pode produzir resultados imprecisos ou inesperados. Revise as respostas do colaborador e as alterações feitas em seu projeto antes de agir com elas ou compartilhar o projeto.

A experiência no produto para o Colaborador está disponível em um painel de chat no lado direito do Analysis Workspace. O Colaborador usa o projeto aberto como contexto, para que você possa fazer perguntas sobre a análise ou solicitar que o Colaborador crie o projeto sem precisar explicar o que ele contém.

## Entender o colega de trabalho no Workspace

### Pré-requisitos

* **O Colaborador está habilitado para sua organização**: a experiência no produto para o Colaborador está desabilitada por padrão. Um administrador do Customer Journey Analytics deve habilitá-lo para a organização antes que os usuários possam acessá-lo.

  Se você não conseguir acessar o Coworker no Workspace, entre em contato com o administrador. Para obter mais informações, consulte [Preferências da Organização IMS](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

* **Acesso à visualização de dados**: o colaborador usa suas permissões de visualização de dados e Analysis Workspace existentes. Ele não pode acessar dados ou componentes aos quais você ainda não tem acesso.

<!--
FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Coworker]** permission determines access to Coworker. A [product profile administrator](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) must add this permission to your product profile. For more information, see [Access control](/help/technotes/access-control.md#access-control).

-->

### Escolha entre o Colaborador no Workspace e o aplicativo Colaborador

A experiência no produto para o Colaborador tem muitos dos mesmos recursos que o [aplicativo do CX Enterprise Coworker](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat), incluindo as habilidades às quais você tem acesso. No entanto, há diferenças importantes que determinam quando você pode usar um sobre o outro:

| | Experiência no produto para o Colaborador | Aplicativo de colaborador |
| --- | --- | --- |
| **Quando usar** | Você deseja criar um projeto que planeja manter, compartilhar com outros usuários ou atualizar ao longo do tempo. | Você quer uma resposta rápida. Você pode optar por transformar a análise em um projeto do Workspace posteriormente, se necessário. |
| **Contexto** | Foco no projeto<p>Usa o projeto Workspace aberto como ponto de partida. Você pode consultar e criar em painéis, tabelas e componentes que já estão no projeto.</p> | Foco na visualização de dados<p>Usa as visualizações de dados às quais você tem acesso ou aquelas que você definiu como uma preferência na memória do Co-worker. Você descreve o que deseja analisar no seu prompt.</p> |
| **Usuário típico** | Analistas que criam e validam análises no Workspace. | Usuários empresariais que desejam respostas sem precisar acessar ou aprender sobre o Workspace. |
| **Saída** | O colaborador adiciona painéis, tabelas e componentes diretamente ao projeto do Workspace. <p>Quando apropriado, ele também responde no bate-papo.</p> | Respostas e análises são fornecidas na conversa, com a opção de abrir no Analysis Workspace. |

### O que você pode fazer com o Colaborador

#### Fazer perguntas sobre o projeto aberto

Você pode fazer perguntas para o Colaborador como:

* Resuma o projeto.
* Encontre insights e sinalize anomalias nos dados.
* Execute uma análise da causa raiz em um painel.
* Explique como fazer algo no Analysis Workspace, por exemplo, como adicionar um gráfico de linhas ou como colorir células de tabela com base em seus valores.
* Explicar um componente, como uma métrica ou dimensão.

Para obter mais informações, consulte [Fazer perguntas sobre um projeto](#ask-questions-about-a-project).

#### Criar e editar o projeto aberto

Você pode pedir ao Colaborador para fazer coisas como:

* Crie um painel de Forma livre com as dimensões, as métricas e o intervalo de datas especificados.
* Adicione painéis ao projeto. O Colaborador adiciona novos painéis sem substituir seus painéis existentes.
* Detalhar uma tabela ou adicionar colunas de comparação.
* Alterar o intervalo de datas ou o tipo de visualização de um painel, como alterar uma tabela para um gráfico de linhas.
* Renomeie um painel.
* Aplique um segmento existente por nome, crie um segmento a partir de uma descrição em linguagem simples ou copie um segmento e altere sua lógica.
* Crie intervalos de datas e métricas calculadas simples.
* Adicione descrições ou uma visualização de Texto que contenha insights para o projeto.
* Crie um projeto com vários painéis ou copie um projeto e adapte-o para um público ou região diferente.
* Salve o projeto.

Para obter mais informações, consulte [Atualizar um projeto](#update-a-project).

### Quando um colega atualiza o projeto ou as respostas no bate-papo

O colaborador decide se quer responder no painel de chat ou alterar o projeto com base no que você pergunta. Para obter mais informações, consulte [Atualizar um projeto](#update-a-project) e [Fazer perguntas sobre um projeto](#ask-questions-about-a-project).

Você também pode ser explícito sobre o que deseja que o Colaborador faça. Por exemplo, você pode usar frases como _no chat_ ou _diga-me_ para obter uma resposta no painel de chat ou frases como _adicionar ao projeto_ ou _nesta tabela_ para atualizar o projeto.

## Usar o Colaborador com seus projetos

O colaborador pode visualizar cada painel e tabela no projeto aberto. Você pode pedir ao Colaborador para responder perguntas sobre o projeto ou para ajudá-lo a atualizá-lo.

>[!TIP]
>
>Você pode interromper o Colaborador ou atualizar o projeto a qualquer momento:
>
>* **Direcione ou pare uma tarefa**: enquanto o Colaborador estiver trabalhando, pressione **Shift+Enter** para orientá-la ou pressione **Esc** para interrompê-la.
>
>* **Fazer atualizações em um projeto no Workspace**: se você editar o projeto enquanto o Coworker estiver trabalhando, o Coworker reconhecerá as suas alterações.

### Atualizar um projeto

Quando você pede ao Colaborador para criar ou editar algo no projeto, o Colaborador atualiza o projeto de acordo. Isso inclui solicitações que começam com palavras como _adicionar_, _criar_, _editar_, _detalhar_, _alterar_ e _comparar_. Por exemplo, você pode pedir ao Coworker para adicionar painéis e tabelas, analisar dados ou criar segmentos.

1. No Customer Journey Analytics, abra um projeto existente do Workspace ou crie um novo projeto.

1. Selecione o ícone **Colaborador** ![Pedir ao Colaborador](/help/assets/icons/coworker.svg) no canto superior direito do cabeçalho para abrir o painel de chat do Colaborador.

1. No painel de bate-papo, descreva o que você deseja que o Coworker faça.

   A tabela a seguir lista prompts de exemplo.

   | Aviso | O que o colega faz |
   | --- | --- |
   | _Mostrar sessões por página do mês passado_ | Adiciona um novo painel de Forma livre com a dimensão, a métrica e o intervalo de datas especificados. Os painéis existentes não são substituídos. |
   | _Separar esta tabela por dispositivo_ | Adiciona o detalhamento à tabela que você mencionou. |
   | _Adicionar uma comparação com o mês passado nesta tabela_ | Adiciona uma coluna de comparação à tabela à qual você fez referência. |
   | _Alterar o intervalo de datas deste painel para o último mês_ | Atualiza o intervalo de datas do painel. |
   | _Alterar esta tabela para um gráfico de linhas_ | Altera o tipo de visualização do painel. |
   | _Renomear este painel para desempenho móvel_ | Renomeia o painel. |
   | _Aplicar o segmento Usuários móveis a este painel_ | Aplica o segmento existente ao painel. O colaborador não sabe a definição do segmento, portanto, verifique se o segmento contém o que você espera. |
   | _Criar um segmento para visitantes do Canadá_ | Cria o segmento e o adiciona ao projeto. O segmento aparece na lista de componentes depois de atualizar a página. |
   | _Copie o segmento de visitantes do Canadá e altere-o para visitantes do México_ | Cria uma cópia do segmento com a lógica atualizada e a adiciona ao projeto. |
   | _Criar um intervalo de datas para as últimas 6 semanas_ | Cria o intervalo de datas. O intervalo de datas aparece na lista de componentes sem uma atualização. |
   | _Criar uma métrica calculada para a receita por sessão_ | Cria a métrica calculada. O colega de trabalho pode criar métricas calculadas simples. |
   | _Adicione uma descrição a este painel que explique a queda nas visitas_ | Adiciona a descrição ao painel. |
   | _Adicionar uma visualização de texto com os principais insights_ | Adiciona uma visualização de Texto que contém os insights ao projeto. |
   | _Crie um projeto com painéis para tráfego, conversão e receita_ | Cria um projeto com um painel para cada área descrita. |
   | _Copiar este projeto e adaptá-lo à região EMEA_ | Cria uma cópia do projeto e a adapta à região especificada. |
   | _Salvar o projeto_ | Salva o projeto. |
   | _Desfazer o detalhamento adicionado_ | Desfaz a alteração especificada. |
   | _Excluir os painéis antigos_ | Lista os painéis que planeja excluir e aguarda sua confirmação antes de excluí-los. |

1. Revise as alterações feitas pelo Colaborador no projeto. Para obter mais informações, consulte [Verificar resultados do Colaborador](#verify-coworker-results).

### Fazer perguntas sobre um projeto

Quando você faz perguntas sobre um projeto, o Colaborador responde no painel de bate-papo. Isso inclui solicitações como _explicar_, _resumir_, _discutir_ e _conte-me mais_. Os resultados da análise de causa raiz e habilidades semelhantes também permanecem no painel de bate-papo até que você peça ao Colaborador para adicioná-los ao projeto.

1. No Customer Journey Analytics, abra um projeto existente do Workspace ou crie um novo projeto.

1. Selecione o ícone **Colaborador** ![Pedir ao Colaborador](/help/assets/icons/coworker.svg) no canto superior direito do cabeçalho para abrir o painel de chat do Colaborador.

1. No painel de bate-papo, descreva o que você deseja que o Coworker faça.

   A tabela a seguir lista prompts de exemplo.

   | Aviso | O que o colega faz |
   | --- | --- |
   | _Resumir este projeto_ | Fornece um resumo no painel de chat e oferece para adicioná-lo ao projeto como uma visualização de Texto. |
   | _Encontrar insights neste projeto_ | Fornece insights no painel de chat e oferece para adicionar as descobertas ao projeto. |
   | _Sinalizar quaisquer anomalias neste painel_ | Descreve as anomalias no painel de chat. Se você pedir ao Colaborador para mostrar anomalias em uma visualização, as anomalias podem não aparecer. Consulte [Limitações atuais](#current-limitations). |
   | _Faça uma análise da causa raiz ao soltar em visitas móveis_ | Fornece a análise no painel de chat e oferece para adicionar as descobertas ao projeto. |
   | _Como colorir células com base em seus valores?_ | Explica as etapas no painel de chat. |
   | _Explicar a métrica Taxa de rejeição_ | Explica o componente no painel de chat. A explicação não vem do [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md). A compatibilidade com as definições do Dicionário de dados está planejada para uma versão futura. |

1. Revise a resposta fornecida pelo Colaborador. Para obter mais informações, consulte [Verificar resultados do Colaborador](#verify-coworker-results).

## Verificar resultados do colaborador

O colega ajuda a verificar a precisão dos resultados. Lembre-se dos itens a seguir ao analisá-los:

* **O Coworker mostra seu trabalho**: os segmentos, as métricas e os filtros que o Coworker usa para responder uma pergunta são adicionados ao projeto para que você possa verificá-los.

* **Questões de esclarecimento**: quando uma solicitação é vaga ou corresponde a mais de um componente, o Colaborador faz uma pergunta esclarecedora ou sugere opções entre as quais escolher. Por exemplo, se mais de uma métrica corresponder ao nome usado, o Colaborador sugere as métricas correspondentes.

* **Observações de qualidade de dados**: o Colaborador inclui observações de qualidade de dados em suas respostas. Por exemplo, se você comparar um mês que acabou de começar com um mês completo, o Coworker informa que a comparação é baseada em dados parciais.

## Limitações atuais

A experiência no produto para o Colaborador tem as seguintes limitações:

* **Definições de segmento**: quando você faz referência a um segmento por nome, o Colaborador não sabe a definição do segmento. O colega de trabalho pode inferir o que o segmento contém com base em seu nome. Verifique a definição do segmento antes de confiar nos resultados.

* **Dicionário de Dados**: o colega não está conectado ao [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md). Ele não pode usar as definições no Dicionário de dados para explicar métricas e dimensões.

* **Componentes aprovados**: o parceiro de trabalho não dá preferência aos componentes aprovados em relação aos componentes semelhantes.

* **Copiando painéis**: o Colaborador não pode copiar ou duplicar um painel.

* **Novos segmentos na lista de componentes**: os segmentos criados pelo Colaborador não aparecem na lista de componentes no painel esquerdo até que você atualize a página. Intervalos de datas criados pelo Colaborador são exibidos sem atualização.

* **Detecção de anomalias**: quando você pede ao Colaborador para mostrar anomalias em uma visualização, elas podem não aparecer.

* **Histórico da conversa**: as conversas são salvas para cada usuário, não com o projeto. Outros usuários que abrem o projeto não podem ver sua conversa com Colaborador. Para compartilhar o contexto com outros usuários, adicione-o às descrições dos painéis no projeto.

* **Várias guias do navegador**: se você abrir a mesma conversa em mais de uma guia do navegador, o Coworker poderá perder a noção em que está trabalhando.

* **Idiomas diferentes do inglês**: em visualizações de dados que usam um idioma diferente do inglês, o Coworker pode usar uma combinação de inglês e o idioma de visualização de dados em suas respostas.


