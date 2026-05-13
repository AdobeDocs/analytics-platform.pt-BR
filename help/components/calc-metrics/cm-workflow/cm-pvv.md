---
description: Saiba como criar uma métrica calculada simples.
title: Criar Uma Métrica Calculada Simples
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
TQID: https://experienceleague.adobe.com/hbiAmMoSUMm2Ggf5Vkxm484SzYETtgRRZAuaWvlS884
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 10%

---

# Criar uma métrica calculada simples

As informações a seguir explicam como criar uma métrica simples de *Exibições de página por visita*.

1. Comece a criar uma métrica, conforme descrito em [Criar métricas](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. Nomeie a métrica `Page Views per Session` ou algo semelhante.
1. Forneça à métrica uma **[!UICONTROL Descrição]** simples para mostrar para que a métrica é usada.
1. Selecione o **[!UICONTROL Formato]** correto. Para este exemplo, escolha **[!UICONTROL Decimal]**.
1. Decida quantas casas decimais você deseja que o relatório mostre.
1. No menu suspenso **[!UICONTROL Mostrar tendência ascendente como]**, selecione ▲ **[!UICONTROL Bom (Verde)]**.
1. Adicione uma **[!UICONTROL tag]** para organizar suas métricas.
1. Para esta métrica calculada, arraste primeiro as **[!UICONTROL Exibições de página]** dos componentes de **[!UICONTROL Métricas]** para a seção **[!UICONTROL Definição]** da tela.
1. Em seguida, arraste **[!UICONTROL Sessões]** dos componentes de **[!UICONTROL Métricas]** e solte a métrica abaixo de **[!UICONTROL Exibições de página]** (aguarde até que a linha azul apareça antes de soltar a métrica).
1. Selecione o operador dividir ![Dividir](/help/assets/icons/Divide.svg). (Dividir é o operador padrão.)
1. Você pode ver uma **[!UICONTROL Visualização]** da métrica enquanto está criando a métrica.
1. **[!UICONTROL Compatibilidade de produto]** mostra se a métrica calculada é compatível em todo o Customer Journey Analytics (excluindo a experimentação).

   ![Métrica calculada simples](assets/simple-calculated-metric.png)
1. Selecione **[!UICONTROL Salvar]**.

   Observe que a fórmula **[!UICONTROL Resumo]** é atualizada sempre que você faz uma alteração na definição da métrica.

1. (Opcional) Para compartilhar, aprovar, adicionar ou remover marcas de formatação, renomear ou excluir uma métrica, você pode acessar o [Gerenciador de métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-manager.md).

