---
title: Chaves gerenciadas pelo cliente
description: Saiba como configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 57%

---

# Chaves gerenciadas pelo cliente

A Adobe Customer Journey Analytics oferece a opção de [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e os clientes do Privacy &amp; Security Shield para utilizar uma Chave gerenciada pelo cliente do Azure (CMK) para ser aplicada aos dados de Customer Journey Analytics.  Observe que esse processo é separado da [Configuração do CMK da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=pt-BR).

>[!NOTE]
>
>As Chaves gerenciadas pelo cliente estão disponíveis no momento apenas para organizações que compraram a oferta complementar [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/customer-data-management-voices-events/events/governance/healthcare-shield.html?lang=pt-BR).

## Configurar CMK para Customer Journey Analytics

Siga estas etapas para configurar o CMK para o Customer Journey Analytics:

1. Verifique se você tem direito ao Adobe Customer Journey Analytics CMK junto à equipe de conta do Adobe.
1. Verifique se, no Azure, você é um administrador com uma função privilegiada, como Administrador de aplicativos, Administrador de aplicativos na nuvem ou Administrador global. [Saiba mais pela Microsoft](https://learn.microsoft.com/pt-br/azure/active-directory/roles/permissions-reference)
1. Crie um novo Cofre de Chaves do Azure para ser usado somente com o Customer Journey Analytics. [Saiba mais pela Microsoft](https://learn.microsoft.com/pt-br/azure/key-vault/general/)
1. Conceda acesso ao aplicativo Adobe Azure para sua chave no cofre de chaves. Esta é a ID da aplicação da Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Saiba mais pela Microsoft](https://learn.microsoft.com/pt-br/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Crie um tíquete de Atendimento ao cliente da Adobe solicitando a configuração do CMK. Inclua o URI do Azure no seu tíquete. O URI pode ser encontrado no campo **Identificador de Chave** da sua Chave do Azure.

   ![Campos de identificador de chave que mostram o URI para https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. O Atendimento ao cliente do Adobe confirmará a conclusão do aplicativo CMK nos dados do Customer Journey Analytics.

Todos os dados utilizados pela Platform são criptografados em trânsito e em repouso para manter seus dados protegidos, com ou sem CMK. Para mais informações sobre a criptografia da Adobe Experience Platform, [saiba mais](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=pt-BR).
