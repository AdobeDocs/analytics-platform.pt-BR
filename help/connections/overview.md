---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: dc3a109f162adfe48f621ba3ece95fedead3c6e1
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 55%

---

# Visão geral das conexões

As conexões permitem que os administradores de produtos Customer Journey Analytics estabeleçam conexões com [!DNL Adobe Experience Platform] fontes de dados, como evento, pesquisa e conjuntos de dados de perfil. Essas conexões permitem a integração de dados de uma Conexão com uma visualização de dados derivada. As conexões são a base do CJA e são criadas a partir de [!DNL Experience Platform] conjuntos de dados de origem. O Acesso a Conexões também permite que você visualize o Gerenciador de conexões, onde é possível visualizar os conjuntos de dados subjacentes que compõem a conexão, bem como fazer seleções críticas de edição e configuração.

Recomendamos restringir a um grupo de gerenciamento principal o acesso ao gerenciamento de conexões. As configurações no nível da conexão têm implicações contratuais relacionadas às alocações de volume para dados trazidos para o Customer Journey Analytics.

Veja um vídeo com uma visão geral:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Permissões necessárias

Para criar uma conexão do Customer Journey Analytics, você precisa das seguintes permissões no [Adobe Admin Console](https://helpx.adobe.com/br/enterprise/admin-guide.html/enterprise/using/manage-permissions-and-roles.ug.html):

Adobe Experience Platform:
* Modelagem de dados: Exibir esquemas, Gerenciar esquemas
* Gerenciamento de dados: exibir conjuntos de dados, gerenciar conjuntos de dados
* Assimilação de dados: Gerenciar fontes
* Exibir namespaces de identidade

Customer Journey Analytics
* Acesso do administrador do produto

>[!IMPORTANT]
>
>É possível combinar vários conjuntos de dados do [!DNL Experience Platform] em uma única conexão.
