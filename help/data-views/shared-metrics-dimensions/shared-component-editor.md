---
title: Editor de componente compartilhado
description: Crie ou edite dimensões e métricas compartilhadas.
exl-id: 3f6a808a-d6ac-4a47-a5e2-63b9f17952e8
TQID: https://experienceleague.adobe.com/vHmMlOpgjLAVzEg9t-MORtrHKsbqBABVcDFkuMlo5FM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bcaa1b08-8269-4ff3-a0c2-f599783b6107id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 394
ht-degree: 0%

---

# Editor de componente compartilhado

O editor de componentes compartilhados permite criar ou editar dimensões e métricas compartilhadas. Ele compartilha muitos elementos de interface ao [criar ou editar uma visualização de dados](/help/data-views/create-dataview.md), mas essas interfaces são distintas na finalidade:

* O editor de componentes de visualização de dados permite criar e editar componentes específicos dessa visualização de dados. Não é possível editar dimensões ou métricas compartilhadas no editor de componentes da visualização de dados. Nesta interface, dimensões e métricas compartilhadas podem ser identificadas por um ![ícone de componente compartilhado](/help/assets/icons/CCLibrary.svg) ao lado do nome do componente.
* O editor de componentes compartilhados permite criar e editar dimensões e métricas compartilhadas. Não é possível editar componentes que pertencem a uma única visualização de dados no editor de componentes compartilhados.

![Captura de tela do editor de componentes](assets/component-editor.png)

A parte superior direita inclui três botões:

* **[!UICONTROL Fechar]** ou **[!UICONTROL Cancelar]**: se todas as alterações forem salvas, o botão **[!UICONTROL Fechar]** fechará o editor. Se houver alterações não salvas, o botão **[!UICONTROL Cancelar]** fechará o editor sem salvar essas alterações.
* **[!UICONTROL Salvar]**: salva todos os componentes e mantém o editor aberto.
* **[!UICONTROL Salvar e concluir]**: salva todos os componentes e fecha o editor.

A interface inclui três colunas/seções principais:

* **Seletor de campo de esquema**: localize os campos de esquema desejados e arraste-os para a área de componentes incluída.
   * **Conexão**: a conexão ativa. Altere a conexão ativa no [gerenciador de métricas e dimensões compartilhado](smd-overview.md).
   * **Lista de componentes**: você pode escolher entre selecionar [!UICONTROL Campos de esquema] (novas dimensões e métricas compartilhadas) ou [!UICONTROL Métricas e dimensões] (componentes compartilhados existentes) no menu suspenso.
   * **Pesquisa**: use a pesquisa de texto do ![ícone de Pesquisa](/help/assets/icons/Search.svg) para localizar o campo de esquema desejado ou o componente compartilhado por nome. Você também pode usar filtros ![Ícone de filtro](/help/assets/icons/Filter.svg) para restringir a lista de componentes. O filtro `Is not deprecated` está ativo por padrão.
   * **Criar campo derivado**: permite [criar um campo derivado](/help/data-views/derived-fields/derived-fields.md).
* **Componentes incluídos**: os componentes configurados para serem compartilhados. Ao criar componentes compartilhados, você pode arrastar mais de um campo de esquema para essa área para criar vários componentes simultaneamente. Ao editar componentes compartilhados, você pode selecionar vários componentes para editar, o que lista todos os componentes selecionados nesta área.
* **Configurações de componente**: ao selecionar um componente na área de componentes incluídos, todas as configurações disponíveis podem ser definidas nesta coluna. Consulte [Configurações de componente](/help/data-views/component-settings/overview.md) para obter todas as opções disponíveis para dimensões e métricas. Shift + clicar em vários elementos na área de componentes incluída permite editar quaisquer campos comuns simultaneamente.
