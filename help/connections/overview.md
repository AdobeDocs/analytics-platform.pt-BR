---
title: Visão geral das conexões do Customer Journey Analytics
description: Saiba mais sobre conexões no Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
exl-id: 012371d7-aaef-4018-95ee-5c52083e9d8f
role: Admin
source-git-commit: 14cdc7bd8817dbf1d7a9950fa6ff62aedff82640
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 39%

---

# Visão geral das conexões

As conexões permitem que os administradores de produtos do Customer Journey Analytics estabeleçam conexões com diferentes fontes de dados da AEP, como conjuntos de dados de evento, pesquisa e perfil. Essas conexões permitem a integração de dados de uma Conexão com uma Visualização de dados derivada. Recomendamos restringir o acesso ao gerenciamento de Conexões a um grupo de gerenciamento principal. As configurações no nível da conexão têm implicações contratuais relacionadas às alocações de volume para dados trazidos para o Customer Journey Analytics.
As conexões são a base do CJA e são criadas a partir de conjuntos de dados de origem da AEP. O Acesso a Conexões também oferece a capacidade de exibir o Gerenciador de conexões, que permite visualizar os conjuntos de dados subjacentes que compõem a conexão, bem como fazer seleções críticas de edição e configuração.

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
