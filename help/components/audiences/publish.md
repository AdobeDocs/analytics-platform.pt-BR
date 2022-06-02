---
title: Criar e publicar públicos no Perfil do cliente em tempo real
description: Saiba como publicar públicos-alvo do Customer Journey Analytics
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# Criar e publicar públicos

Este tópico discute como publicar públicos-alvo descobertos no Customer Journey Analytics (CJA) para [Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR) no Adobe Experience Platform para direcionamento e personalização de clientes.

## Criar público-alvo

1. Para criar públicos-alvo, você tem três maneiras de começar:

   | Método de criação | Detalhes |
   | --- | --- |
   | De **[!UICONTROL Componentes] > [!UICONTROL Públicos-alvo]** | A página Audiences Manager é aberta. Clique em **[!UICONTROL Criar público-alvo]** e [!UICONTROL Construtor de público-alvo] é aberto. |
   | A partir de uma tabela de forma livre | Clique com o botão direito do mouse em um item na tabela de Forma livre e selecione **[!UICONTROL Criar um público-alvo a partir da seleção]**. O uso desse método preenche o filtro previamente com a dimensão ou o item de dimensão selecionado na tabela. |
   | Na interface do usuário de edição de filtro | Marque a caixa que diz **[!UICONTROL Criar um público-alvo com base neste filtro]**. O uso desse método preenche o filtro previamente. |

   {style=&quot;table-layout:auto&quot;}

1. Configure o público.

   | Configuração | Descrição |
   | --- | --- |
   | [!UICONTROL Nome] | O nome do público-alvo. |
   | [!UICONTROL Tags] | Quaisquer tags que você deseja atribuir ao público-alvo para fins organizacionais. Você pode usar uma tag pré-existente ou inserir uma nova. |
   | [!UICONTROL Descrição] | Adicione uma boa descrição do público-alvo para diferenciá-lo dos outros. |
   | [!UICONTROL Frequência de atualização] | A frequência na qual você deseja atualizar o público-alvo.<ul><li>Você pode optar por criar um público-alvo único (padrão) que não precise de atualização, o que seria útil para campanhas únicas específicas, por exemplo.</li><li>Você pode selecionar outros intervalos de atualização. Para a frequência de 4 horas, há um limite de 150 públicos-alvo, pois essa taxa de atualização exige muito processamento. Para outros intervalos, não há número máximo de públicos-alvo.</li></ul> |
   | Data de expiração | Quando o público-alvo parará de ser atualizado. O padrão é 1 ano a partir da data de criação. |
   | Atualizar janela de retrospectiva | Especifica até que ponto você deseja voltar na janela de dados ao criar esse público-alvo. O máximo. é de 90 dias. Públicos que expiram são tratados de forma semelhante aos relatórios agendados que expiram - o administrador recebe um email por mês antes de o agendamento expirar. |
   | [!UICONTROL Intervalo de datas único] | Intervalo de datas quando você deseja que o público-alvo único seja publicado. |
   | [!UICONTROL Filtro] | Os filtros são a principal entrada para o público. Você pode adicionar até 20 filtros. Esses filtros podem ser unidos com `And` ou `Or` operadores. |

   {style=&quot;table-layout:auto&quot;}

1. Interpretar a visualização de dados.

   A visualização do público-alvo é exibida no painel direito.

   | Configuração de visualização | Descrição |
   | --- | --- |
   | Janela de visualização de dados | O intervalo de datas do público-alvo. |
   | Total de pessoas no público | Um número de resumo que pode chegar a 100 milhões. |
   | Limite de tamanho do público | Mostra o quão longe está do limite de 100 milhões de pessoas. |
   | Retorno estimado do público |  |
   | Estimativa de retorno | Um número de resumo... |
   | Visualizar métricas |  |

   {style=&quot;table-layout:auto&quot;}


