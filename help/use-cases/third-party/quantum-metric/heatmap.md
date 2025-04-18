---
title: Usar mapas de calor de métrica quântica com o Customer Journey Analytics
description: Entenda melhor o engajamento no nível da página e otimize as páginas com base no comportamento do consumidor usando os dados do mapa de calor da Métrica quântica.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Usar mapas de calor de métrica quântica com o Customer Journey Analytics

Vincular o mapeamento de calor da métrica quântica aos dados do CJA permite entender melhor o envolvimento no nível da página e otimizar as páginas com base no comportamento do consumidor. O Workspace pode ser usado para entender os fluxos de usuários consumidores e ver quais caminhos os consumidores seguem de uma página para outra. Em seguida, clique em URLs de página com hiperlink para visualizar o mapa de calor de como os usuários se envolvem com o conteúdo. Ao vincular o mapeamento de calor de métrica quântica ao CJA, agora é possível associar interações no nível da página aos resultados de negócios, elevando sua análise ao próximo nível.

A tabela retornará todas as sessões nesse segmento, e você pode clicar em qualquer uma delas para explorar mais em QM.  Saiba mais sobre a repetição de sessão de Métrica quântica em https://www.quantummetric.com/platform/session-replay

## Pré-requisitos

Você deve ter direito ao pacote **UX Ops** da Métrica Quantum para acessar os recursos de mapa de calor da Métrica Quantum.

## Etapa 1: crie uma tabela de forma livre no Workspace e configure-a para que os valores de ID da sessão sejam vinculados diretamente à Métrica quântica.

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
1. Teste um dos links para ver se ele abre no URL com a extensão Métrica quântica visível. Esses links abrem em uma nova guia para que o projeto do Workspace permaneça aberto.

## Etapa 2: exibir os mapas de calor clicando nos links dentro do Customer Journey Analytics

Depois de encontrar uma página que deseja explorar o mapeamento de calor, você pode aplicá-la ao painel desejado. A tabela retorna um URL que permite explorar mapas de calor, profundidade de rolagem e zonas-chave para interação usando a Métrica quântica. Consulte [visão geral do produto Quantum Metric heatmap](https://www.quantummetric.com/platform/interaction-heatmaps) para obter mais informações. Você também pode entrar em contato com o representante de suporte ao cliente da Quantum Metric ou enviar uma solicitação por meio do [Portal de solicitação do cliente da Quantum Metric](https://community.quantummetric.com/s/public-support-page).
