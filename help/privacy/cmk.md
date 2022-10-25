---
title: Chaves gerenciadas pelo cliente
description: Saiba como configurar chaves gerenciadas pelo cliente para CJA.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
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

Siga estas etapas para configurar o CMK para CJA:

1. Certifique-se de ter direito ao CMK verificando com a equipe da conta do Adobe.
1. Crie um novo Cofre de Chaves do Azure para ser usado somente com o CJA.
1. Vincule seu Valor da Chave do Azure ao Aplicativo CMK do Azure CJA (link a seguir).
1. Crie um tíquete de Atendimento ao cliente do Adobe solicitando a configuração do CMK. Inclua o URI do Azure no seu tíquete.
1. O Atendimento ao cliente do Adobe confirmará a conclusão do aplicativo CMK em seus dados CJA.
