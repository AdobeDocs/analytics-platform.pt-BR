---
description: Use legendas inteligentes para gerar insights em linguagem natural e exibir tendências rapidamente nas visualizações.
title: Legendas inteligentes
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 6a193f2fd179809afac6808f3fb958c020f53a8d
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 5%

---

# Legendas inteligentes

As legendas inteligentes usam aprendizado de máquina avançado e IA generativa para fornecer insights valiosos de linguagem natural para visualizações do Workspace. A versão inicial fornece insights gerados automaticamente para a visualização de [Linha](line.md). Outras visualizações se seguirão.

As legendas inteligentes são voltadas para:

* Analistas que precisam de narrativas para compartilhar com outros usuários. Os analistas precisam desses insights para fornecer contexto aos usuários.
* Usuários empresariais que desejam descobrir os principais pontos de partida rapidamente.

As legendas estão disponíveis para todos os usuários de Customer Journey Analytics e não exigem permissões especiais.

## Iniciar legendas inteligentes {#launch}

Para iniciar legendas geradas automaticamente em uma visualização de linha, clique no ícone **[!UICONTROL Legendas inteligentes]** na parte superior direita da visualização.

![Janela Análise do Launch mostrando as legendas inteligentes para a tendência de Exibições de produtos. ](assets/intell-caps-1.png)

Os insights de linguagem natural estão sendo gerados agora.

Lembre-se

* Você precisa de no mínimo 3 pontos de dados para gerar legendas com êxito. Caso contrário, você poderá receber um erro como **[!UICONTROL Dados insuficientes para analisar]**.

* As legendas são geradas sempre que os dados subjacentes selecionados são alterados na tabela que habilita a visualização.

* Se houver várias métricas na tabela, as legendas serão geradas apenas para a primeira métrica ou para a métrica selecionada no momento pelo usuário.

* Se você salvar o projeto em um ponto específico e recarregá-lo posteriormente, as legendas serão atualizadas automaticamente com novos dados. O mesmo se aplica a projetos agendados e arquivos de PDF exportados de um projeto.

Este é um exemplo de como as legendas inteligentes podem ser:

![Legendas inteligentes para visualização de Linha, incluindo Sazonalidade, Mín, Máx, Pico e Recusar.](assets/captions.png)

## Ações

Você pode executar as seguintes ações em legendas inteligentes:

### Copiar para a área de transferência {#copy}

Você pode copiar as legendas para uma área de transferência e colá-las em um PowerPoint ou outras ferramentas. Selecione ![Copiar legendas para a área de transferência](/help/assets/icons/Copy.svg) na parte superior direita da caixa de diálogo de legendas.

### Editar exibição {#edit}

É possível editar a exibição de legendas, como ocultar ou reexibir uma categoria específica de insights.

1. Selecione ![Editar exibição de legendas inteligentes](/help/assets/icons/EditInLight.svg) na caixa de diálogo Legendas inteligentes.

1. Alterne entre ![Visibility](/help/assets/icons/Visibility.svg) para exibir um insight específico (como **[!UICONTROL Min]**) ou ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) para ocultar um insight específico (como **[!UICONTROL Spike]**).

   ![Editar legendas inteligentes](assets/edit-intelligent-captions.png)

1. Selecione **[!UICONTROL Aplicar]**.


### Fornecer feedback

Você pode fornecer feedback sobre as legendas inteligentes geradas.

1. Selecione ![Mais ações](/help/assets/icons/More.svg) na caixa de diálogo Legendas inteligentes.

1. Selecione ![Boa resposta](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Boa resposta]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Resposta incorreta]** ou ![Sinalizador](/help/assets/icons/Flag.svg) **[!UICONTROL Relatório]**.

1. Na caixa de diálogo **[!UICONTROL Obrigado por seus comentários]**, forneça seus comentários e selecione **[!UICONTROL Enviar]** para enviar os comentários.

### Exportar {#export}

É possível exportar legendas inteligentes como parte de um PDF, desde que o projeto seja salvo com as legendas inteligentes geradas.

### Ativar/desativar {#toggle}

Se você preferir não mostrar legendas inteligentes, é possível desativar o recurso.

1. Vá para [Preferências de visualização](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Desmarque **[!UICONTROL Mostrar legendas inteligentes]**.

   ![Opções de visualização de linha que mostram a opção de desmarcar Mostrar legendas inteligentes.](assets/toggle-captions.png)

1. Selecione **[!UICONTROL Salvar]** para salvar a preferência.


## Legendas inteligentes em cartões de pontuação móveis

As legendas inteligentes também estão disponíveis nos [cartões de pontuação móveis](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) do Customer Journey Analytics.

## Acesso ao recurso

Os parâmetros a seguir controlam o acesso a legendas inteligentes:

* **Acesso à solução**: o recurso Legendas inteligentes está disponível no Customer Journey Analytics, mas não no Adobe Analytics.

* **Acesso contratual**: se você não puder usar legendas inteligentes, entre em contato com o administrador da sua organização ou com o Representante de Conta do Adobe. Antes de usar o Intelligent em sua organização, você deve concordar com determinados termos legais relacionados à GenAI.

* **Permissões**: no [!UICONTROL Adobe Admin Console], a permissão [!UICONTROL Ferramentas de Relatório] **[!UICONTROL Legendas inteligentes]** determina o acesso. Um [administrador de perfil de produto](https://helpx.adobe.com/br/enterprise/using/manage-product-profiles.html) precisa seguir estas etapas no [!UICONTROL Admin Console]:
   1. Navegue até **[!UICONTROL Admin Console]** > **[!UICONTROL Produtos e serviços]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Perfis de Produtos]**.
   1. Selecione o título do perfil de produto para o qual você deseja fornecer acesso às legendas inteligentes.
   1. No perfil de produto específico, selecione **[!UICONTROL Permissões]**.
   1. Selecione ![Editar](/help/assets/icons/Edit.svg) para editar as **[!UICONTROL Ferramentas de Relatório]**.
   1. Selecione ![AddCircle](/help/assets/icons/AddCircle.svg) para adicionar **Legendas inteligentes** a **[!UICONTROL itens de permissão incluídos]**.

      ![Adicionar permissão](./assets/intelligent-captions-permissions.png)

   1. Selecione **[!UICONTROL Salvar]** para salvar as permissões.

Consulte [Controle de acesso](/help/technotes/access-control.md#access-control) para obter mais informações.
