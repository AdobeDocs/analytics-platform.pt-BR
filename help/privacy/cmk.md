---
title: Teclas gerenciadas pelo cliente
description: Saiba como configurar as teclas gerenciadas pelo cliente para o Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
TQID: https://experienceleague.adobe.com/5V0LlfmD8CqPp4Sfr43txnke84eJN-pHUaACK7vE1N8
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 561
ht-degree: 87%

---

# Teclas gerenciadas pelo cliente

O Adobe Customer Journey Analytics oferece a opção de os clientes do [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e do Privacy &amp; Security Shield usarem as chaves gerenciadas pelo cliente (CMK) para dados do Customer Journey Analytics. Observe que esse processo é separado da [Configuração de CMK da Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). As chaves gerenciadas pelo cliente estão disponíveis apenas para organizações que adquiriram a oferta complementar do [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/pt-br/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics no Azure

Siga estas etapas para configurar a CMK para o Customer Journey Analytics em execução no Azure:

1. Verifique se você tem direito de usar a CMK do Adobe Customer Journey Analytics e se a sua organização usa a Adobe Experience Platform no Azure. Para verificar esses direitos, entre em contato com a sua equipe de conta da Adobe.
1. Verifique se, no Azure, você é um administrador com uma função privilegiada, como Administrador de aplicativos, Administrador de aplicativos na nuvem ou Administrador global. Consulte [Funções integradas do Microsoft Entra](https://learn.microsoft.com/pt-br/entra/identity/role-based-access-control/permissions-reference) para mais informações.
1. Crie um novo cofre de chaves do Azure para ser usado somente com o Customer Journey Analytics. Consulte a [documentação do cofre de chaves do Microsoft Azure](https://learn.microsoft.com/pt-br/azure/key-vault/general/) para mais informações.
1. Conceda acesso ao aplicativo Adobe Azure para sua chave no cofre de chaves. Você pode fazer isso usando um dos seguintes métodos:
   * Conceder permissões por meio do consentimento de autorização através da seguinte URL: [https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&amp;redirect_uri=https://experience.adobe.com&amp;scope=user.read](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&client_id=251e3919-1940-4296-bb8b-6b9a5e8a4805&redirect_uri=https://experience.adobe.com&scope=user.read)

   * Siga as instruções em [Configurar chaves gerenciadas pelo cliente para uma conta existente](https://learn.microsoft.com/pt-br/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault). O ID do aplicativo da Adobe é:

     **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Crie um tíquete de Atendimento ao cliente da Adobe solicitando a configuração do CMK. Inclua o URI do Azure no seu tíquete. O URI pode ser encontrado no campo **Identificador de chave** da sua chave do Azure:

   ![Campos de identificador de chave, mostrando o URI de https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. O atendimento ao cliente da Adobe confirmará a conclusão da aplicação de CMK aos seus dados do Customer Journey Analytics.

Todos os dados utilizados pela Platform são criptografados em trânsito e em repouso para manter os seus dados protegidos, com ou sem CMK. Para mais informações sobre a criptografia da Adobe Experience Platform, consulte [Criptografia de dados na Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics no Amazon Web Services

>[!AVAILABILITY]
>
>Esta seção aplica-se às implementações da Experience Platform executadas no Amazon Web Services (AWS). A Experience Platform em execução no AWS está disponível atualmente para um número limitado de clientes. Para saber mais sobre a infraestrutura da Experience Platform compatível, consulte a [Visão geral da nuvem múltipla da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/landing/multi-cloud).

Se a sua organização usar a Adobe Experience Platform executada no Amazon Web Services, a CMK já estará configurado para você. Nenhuma configuração adicional é necessária.
