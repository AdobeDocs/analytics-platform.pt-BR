---
title: Implementar a tag do carregador para a extensão do SDK da web
description: Saiba como implementar a tag do carregador para a extensão do SDK da web
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
autotag-review: '2026-05-19T08:19:22.813Z'
TQID: 'https://experienceleague.adobe.com/OYEIDQvTVX2GFMKWvCGuKqoyZcvWbcsnGSQwM-tsYl0'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2: id: eed59de6-f140-4dd2-beca-afcbb0f6a2c5
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 301
ht-degree: 100%

---

# Implementar a tag do carregador para a extensão do SDK da web {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="Implementar a tag de carregamento em seu site"
>abstract="Trabalhe com a equipe de desenvolvimento do site para instalar a tag de carregamento em cada página do site.<br><br>O tempo de conclusão desta tarefa depende muito do tempo de resposta da equipe de engenharia que implantará o código. Algumas organizações que têm equipes de engenharia altamente adaptáveis podem concluir essa etapa em dias, enquanto outras que possuem uma extensa lista de pendências podem levar um mês ou mais."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

É necessário instalar a tag no site que você deseja rastrear, o que implica colocar o código na tag do cabeçalho do modelo do seu site.

O processo a seguir descreve como obter o código que referencia a tag. Para obter informações complementares, consulte os [Guias de implementação de tags e encaminhamento de eventos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/get-started/implementation-guides) na documentação da Experience Platform.

Para obter o código que faz referência à sua tag:

1. Faça logon em experiencecloud.adobe.com com as suas credenciais do Adobe ID.

1. Na Adobe Experience Platform, acesse **[!UICONTROL Coleção de dados]** > **[!UICONTROL Tags]**.

1. Na página **[!UICONTROL Propriedades da tag]**, selecione a tag recém-criada na lista de propriedades para abri-la.

1. Selecione **[!UICONTROL Ambientes]** no painel esquerdo.

1. Na lista de ambientes, selecione o botão de instalação correto (caixa).

   Na caixa de diálogo [!UICONTROL Instruções de instalação da Web] clique no botão copiar ao lado do código de script que deve ser lido como:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![Ambiente](assets/environment.png)

1. Selecione **[!UICONTROL Fechar]**.

   Em vez do código para o ambiente de desenvolvimento, você pode ter selecionado outro ambiente (armazenamento temporário, produção) com base em onde você está no processo de implantação do SDK da Web da Adobe Experience Platform.

   Consulte [Ambientes](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=pt-BR) para obter mais informações.

{{upgrade-final-step}}
