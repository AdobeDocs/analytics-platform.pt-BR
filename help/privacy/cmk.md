---
title: Chaves gerenciadas pelo cliente
description: Saiba como configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics.
exl-id: 08ece1cb-22b7-4b8d-be76-5414a810feb6
feature: Privacy
role: Admin
source-git-commit: dfdb6bc5c190e4de98eaef86e0c8d118327640a6
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 14%

---

# Chaves gerenciadas pelo cliente

A Adobe Customer Journey Analytics oferece a opção de os clientes do [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) e do Privacy &amp; Security Shield usarem as chaves gerenciadas pelo cliente (CMK) para os dados de Customer Journey Analytics. Observe que este processo é separado da [configuração do CMK do Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys/overview). As chaves gerenciadas pelo cliente só estão disponíveis para organizações que compraram a oferta complementar [Healthcare Shield ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/pt-br/docs/events/customer-data-management-voices-recordings/governance/healthcare-shield).

## Configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics no Azure

Siga estas etapas para configurar o CMK para o Customer Journey Analytics em execução no Azure:

1. Verifique se você tem direito ao Adobe Customer Journey Analytics CMK e se sua organização usa o Adobe Experience Platform em execução no Azure. Você pode verificar esses direitos entrando em contato com a equipe de conta do Adobe.
1. Verifique se, no Azure, você é um administrador com uma função privilegiada, como Administrador de aplicativos, Administrador de aplicativos na nuvem ou Administrador global. Consulte [Funções internas do Microsoft Entra](https://learn.microsoft.com/en-us/entra/identity/role-based-access-control/permissions-reference) para obter mais informações.
1. Crie um novo Cofre de Chaves do Azure para ser usado somente com o Customer Journey Analytics. Consulte a [documentação do Cofre de Chaves do Microsoft Azure](https://learn.microsoft.com/pt-br/azure/key-vault/general/) para obter mais informações.
1. Conceda acesso ao aplicativo Adobe Azure para sua chave no cofre de chaves. Consulte [Configurar chaves gerenciadas pelo cliente para uma conta existente](https://learn.microsoft.com/pt-br/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault) para obter mais informações. A ID do aplicativo Adobe é:

   **`251e3919-1940-4296-bb8b-6b9a5e8a4805`**

1. Crie um tíquete de Atendimento ao cliente da Adobe solicitando a configuração do CMK. Inclua o URI do Azure no seu tíquete. O URI pode ser encontrado no campo **Identificador de Chave** da sua chave do Azure:

   ![Campos de Identificador de Chave mostrando o URI para https://cmkoberontest.vault.azure.net](assets/key-identifier.png)

1. O Atendimento ao cliente do Adobe confirma a conclusão do aplicativo CMK nos dados do Customer Journey Analytics.

Todos os dados usados pela Platform são criptografados em trânsito e em repouso para manter seus dados seguros, com ou sem chaves gerenciadas pelo cliente. Para obter informações sobre a criptografia do Adobe Experience Platform, consulte [Criptografia de dados no Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/encryption).

## Configurar chaves gerenciadas pelo cliente para o Customer Journey Analytics no Amazon Web Services

>[!AVAILABILITY]
>
>Esta seção se aplica às implementações do Experience Platform executadas no Amazon Web Services (AWS). O Experience Platform em execução no AWS está atualmente disponível para um número limitado de clientes. Para saber mais sobre a infraestrutura de Experience Platform compatível, consulte a [visão geral de várias nuvens do Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/landing/multi-cloud).

Se sua organização usar o Adobe Experience Platform em execução no Amazon Web Services, o CMK já estará configurado para você. Nenhuma configuração adicional é necessária.
