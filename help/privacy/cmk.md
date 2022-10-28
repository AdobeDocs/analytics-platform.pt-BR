---
title: Chaves gerenciadas pelo cliente
description: Saiba como configurar chaves gerenciadas pelo cliente para CJA.
hide: true
hidefromtoc: true
source-git-commit: 90521aa7326486b9016321d35191a73ef891a0bc
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# Chaves gerenciadas pelo cliente

>[!NOTE]
>
>Essa funcionalidade estará disponível em novembro de 2022.

O Customer Journey Analytics (CJA) fornece a opção para [Escudo da Saúde](https://www.adobe.com/trust/compliance/hipaa-ready.html) e clientes do Privacy &amp; Security Shield para utilizar uma Chave gerenciada pelo cliente do Azure (CMK) para ser aplicada aos dados do CJA.  Observe que esse processo é separado de [Configuração do Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>As Chaves Gerenciadas pelo Cliente estão disponíveis no momento apenas para organizações que compraram a [Proteção de saúde ou Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) oferta complementar.

## Configurar CMK para CJA

Siga estas etapas para configurar o CMK para CJA:

1. Certifique-se de ter direito ao Adobe CJA CMK, verificando com a equipe de conta do Adobe.
1. Certifique-se de que, no Azure, você seja um administrador com uma função privilegiada, como Administrador de aplicativos, Administrador de aplicativos na nuvem ou Administrador global. [Saiba mais pela Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Crie um novo Cofre de Chaves do Azure para ser usado somente com o CJA. [Saiba mais pela Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Conceda acesso ao aplicativo do Adobe Azure para sua chave no cofre de chaves. Esta é a ID do aplicativo Adobe: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Saiba mais pela Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Crie um tíquete de Atendimento ao cliente do Adobe solicitando a configuração do CMK. Inclua o URI do Azure no seu tíquete. O URI pode ser encontrado no campo Identificador de Chave da Chave do Azure.
1. O Atendimento ao cliente do Adobe confirmará a conclusão do aplicativo CMK em seus dados CJA.
