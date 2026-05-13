---
description: Explica como criar uma métrica que mostra quais Canais de marketing auxiliam na criação de pedidos.
title: Criar Uma Métrica Calculada Mais Complexa
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# Criar uma métrica calculada mais complexa

Este artigo explica um exemplo mais complexo de uma métrica calculada. Essas métricas calculadas mostram quais Canais de marketing auxiliam na criação de pedidos. Esse tipo de métrica calculada pode ser adaptado a qualquer dimensão ou evento bem-sucedido.

1. Comece a criar uma métrica calculada, conforme descrito em [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

1. No Criador de métricas calculadas, nomeie a métrica `Assisted Online Orders` ou algo semelhante.

1. Selecione a métrica **[!UICONTROL Pedidos online]** dos componentes de **[!UICONTROL Métricas]** e arraste a métrica para a área **[!UICONTROL Definição]**.

   1. Selecione ![Configuração](/help/assets/icons/Setting.svg) para a métrica.
   1. Clique em **[!UICONTROL Usar modelo de atribuição não padrão]**.
   1. Ajuste o modelo de atribuição no **[!UICONTROL Modelo de atribuição de coluna]**.
      1. Selecione **[!UICONTROL Personalizado]** para **[!UICONTROL Modelo]**. Defina **[!UICONTROL Iniciante]** para `0`, **[!UICONTROL Reprodutor]** para `100` e **[!UICONTROL Mais próximo]** para `0`.
      1. Selecione **[!UICONTROL Visitante]** para **[!UICONTROL Contêiner]**.
      1. Selecione **[!UICONTROL 30 Dias]** para **[!UICONTROL Janela de pesquisa]**.

      1. Selecione **[!UICONTROL Aplicar]**.

      ![Modelo de atribuição de coluna](assets/complex-calculated-metric.png)

1. Selecione **[!UICONTROL Salvar]** para salvar a métrica calculada.

Para usar a métrica calculada:

1. No Analysis Workspace, crie uma tabela de forma livre com a dimensão **[!UICONTROL Canal de marketing]**, **[!UICONTROL Pedidos online]** e sua nova métrica **[!UICONTROL Pedidos online assistidos]**.

   ![Pedidos Online Assistidos por Canal de Marketing](assets/marketing-channel-assists.png)

1. (Opcional) Compartilhe a métrica com outros usuários em sua organização, conforme descrito em [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md).

Essa é uma maneira fácil de saber quais Canais de marketing auxiliaram na criação de pedidos. Como alternativa, em uma tabela de forma livre, você pode selecionar qualquer métrica e, no menu de contexto, ajustar o modelo de atribuição diretamente da tabela.
