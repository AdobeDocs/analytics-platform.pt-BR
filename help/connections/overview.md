---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 7a5fa07e3bafa3da5b044ce37299196a006f1d64
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---

# Visão geral das conexões

As conexões permitem que admins de produto do Customer Journey Analytics conectem-se com diferentes fontes de dados da [!DNL Adobe Experience Platform], como conjuntos de dados de eventos, de pesquisas e de perfis. Essas conexões permitem a integração de dados de uma conexão com uma visualização de dados derivada. As conexões são a base do CJA e são criadas a partir de conjuntos de dados de origem da [!DNL Experience Platform]. O acesso a conexões também permite visualizar o gerenciador de conexões, onde é possível ver os conjuntos de dados subjacentes que compõem a conexão, bem como selecionar cuidadosamente as opções de edição e configuração.

Recomendamos restringir o acesso ao gerenciamento de conexões a um grupo de gerenciamento principal. As configurações no nível da conexão têm implicações contratuais relacionadas às alocações de volume para dados migrados para o Customer Journey Analytics.

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
