---
title: Como definir configurações para o Report Builder no Customer Journey Analytics
description: Descreve como definir as configurações de modo offline, idioma, data de início e solução de problemas.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 31%

---

# Configurações do Report Builder

Use o painel **Configurações** para definir as configurações no nível do aplicativo, como o idioma exibido pela interface ou se deseja, ou não, trabalhar no modo off-line. As configurações são aplicadas imediatamente e são definidas para todas as sessões futuras até serem alteradas.

Para alterar as configurações do Report Builder

1. Selecione o ícone **Configurações**.

1. Faça alterações em [habilitar ou desabilitar o modo offline](#off-line-mode), [selecionar um idioma](#language) ou [habilitar a solução de problemas](#troubleshooting).

1. Selecione **[!UICONTROL Aplicar]**.

   ![Painel de intervalo de datas do Report Builder mostrando o botão Cancelar e Aplicar.](./assets/report-builder-settings.png){zoomable="yes"}

## Modo offline

Ao criar e editar um bloco de dados no modo off-line, os dados não são recuperados. Em vez disso, os dados de simulação são usados para que você possa trabalhar rapidamente sem esperar a execução da solicitação. Quando você voltar a ficar online, selecione ![Atualizar](/help/assets/icons/Refresh.svg) **[!UICONTROL Atualizar bloco de dados]** ou ![AtualizarDocumento](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Atualizar todos os blocos de dados]** para atualizar os blocos de dados com dados reais.

Para habilitar o modo off-line

1. Selecione ![Configuração](/help/assets/icons/Setting.svg).

1. Ativar/desativar **[!UICONTROL modo offline]**.

1. Insira um número inteiro positivo no **[!UICONTROL Exibir dados de métrica]** como campo.

1. Selecione **[!UICONTROL Aplicar]**.


## Idioma

Você pode escolher o idioma para a interface do Report Builder. Todos os idiomas suportados pelo Customer Journey Analytics estão disponíveis.

Para selecionar o idioma usado na interface do Report Builder:

1. Selecione um idioma no menu suspenso **[!UICONTROL Idioma]**.

1. Selecione **Aplicar.**

## Solução de problemas

A configuração **[!UICONTROL Logs de solução de problemas]** registra todos os dados do cliente/servidor em um arquivo local. Use essa opção para ajudar a resolver tíquetes de suporte.

Para habilitar logs de solução de problemas, verifique **[!UICONTROL Registrar solicitação do Report Builder no arquivo local]**.
