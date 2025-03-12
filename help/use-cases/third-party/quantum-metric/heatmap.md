---
title: Usar mapas de calor de métrica quântica com o Customer Journey Analytics
description: Entenda melhor o engajamento no nível da página e otimize as páginas com base no comportamento do consumidor usando os dados do mapa de calor da Métrica quântica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Usar mapas de calor de métrica quântica com o Customer Journey Analytics

Vincular o mapeamento de calor da métrica quântica aos dados do CJA permite entender melhor o envolvimento no nível da página e otimizar as páginas com base no comportamento do consumidor. O Workspace pode ser usado para entender os fluxos de usuários consumidores e ver quais caminhos os consumidores seguem de uma página para outra. Em seguida, clique em URLs de página com hiperlink para visualizar o mapa de calor de como os usuários se envolvem com o conteúdo.

A tabela retornará todas as sessões nesse segmento, e você pode clicar em qualquer uma delas para explorar mais em QM.  Saiba mais sobre a repetição de sessão de Métrica quântica em https://www.quantummetric.com/platform/session-replay

## Pré-requisitos

Esse caso de uso exige que você colete a ID de sessão da Métrica Quantum ao lado do restante da implementação. Consulte [Coletar IDs de sessão de Métrica Quântica no Customer Journey Analytics](collect-session-id.md) para saber como modificar sua implementação.

Você deve ter direito ao pacote **UX Ops** da Métrica Quantum para acessar os recursos de mapa de calor da Métrica Quantum.

## Crie uma tabela de forma livre no Workspace e a configure para que os valores de ID da sessão sejam vinculados diretamente à Métrica quântica.

1. Faça logon em [experience.adobe.com](https://experience.adobe.com).
1. Navegue até Customer Journey Analytics e selecione **[!UICONTROL Workspace]** no menu superior.
1. Selecione um projeto existente ou crie um projeto.
1. Crie uma [Tabela de forma livre](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Arraste a dimensão URL da página para a tela do Workspace.
1. Clique com o botão direito do mouse no cabeçalho da coluna de dimensão e selecione **[!UICONTROL Criar hiperlinks para todos os itens de dimensão]**.
1. Selecione **[!UICONTROL Criar uma URL personalizada]**.
1. Cole a seguinte estrutura de URL:

   ```
   $value?qm-visible=true
   ```

1. Clique em **[!UICONTROL Criar]**.

1. Clique em Criar e teste um dos links para ver se ele abre no URL com a extensão QM aberta. Observação: ele será aberto em uma guia separada, para que você não perca seu trabalho.


## Visualização de mapas de calor clicando nos links dentro do Customer Journey Analytics

Depois de encontrar uma página para a qual deseja explorar o mapeamento de calor, você pode aplicá-la ao painel no qual o URL está. A tabela retornará um URL que permitirá explorar os mapas de calor da página em questão, a profundidade de rolagem e as zonas principais para interação.  Saiba mais sobre os Heatmaps de métrica quântica em https://www.quantummetric.com/platform/interaction-heatmaps


