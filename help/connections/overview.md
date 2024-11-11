---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 2f78905c2a1e94174a52269becc15474baf59f71
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 69%

---

# Visão geral das conexões

As conexões permitem que admins de produto do Customer Journey Analytics conectem-se com diferentes fontes de dados da [!DNL Adobe Experience Platform], como conjuntos de dados de eventos, de pesquisas e de perfis. Essas conexões permitem a integração de dados de uma conexão com uma visualização de dados derivada. As conexões são a base do CJA e são criadas a partir de conjuntos de dados de origem da [!DNL Experience Platform]. O acesso a conexões também permite visualizar o gerenciador de conexões, onde é possível ver os conjuntos de dados subjacentes que compõem a conexão, bem como selecionar cuidadosamente as opções de edição e configuração.

Recomendamos restringir o acesso ao gerenciamento de conexões a um grupo de gerenciamento principal. As configurações no nível da conexão têm implicações contratuais relacionadas às alocações de volume para dados migrados para o Customer Journey Analytics.

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Permissões necessárias

Para criar uma conexão Customer Journey Analytics, você precisa das seguintes permissões. Para obter detalhes adicionais sobre permissões, consulte a documentação do [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html) e das [Permissões do Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home).

### No Adobe Admin Console:

* Customer Journey Analytics: Administrador de produto
* Adobe Experience Platform: adicionado ao Perfil de produto chamado *AEP-Padrão-Todos-Usuários*

### Nas Permissões Do Adobe Experience Platform:

* Modelagem de dados: Exibir esquemas, Gerenciar esquemas
* Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
* Assimilação de dados: Gerenciar fontes
* Identity Management: Exibir namespaces de identidade
* Sandboxes: sandboxes usadas em conexões Customer Journey Analytics relacionadas

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados do [!DNL Experience Platform] em uma única conexão.
