---
title: Como configurar o Report Builder no Customer Journey Analytics
description: Descreve como configurar o Report Builder no CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: e76f6cbb8ecf2032a8211d1c6bd18a79c2a6f5d2
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 1%

---


# Configuração de Report Builder

Você pode acessar rapidamente o Report Builder usando o menu Suplemento do Excel.

## Requisitos

O Report Builder for Customer Journey Analytics é compatível com os seguintes sistemas operacionais e navegadores da Web.

### macOS

- macOS versão 10.x ou posterior
- Todas as versões do Excel

### Windows

- Windows 10, versão 1904 ou posterior
- Versão do Excel 2106 ou posterior

   Todos os usuários do Windows Desktop Excel devem instalar o Microsoft Edge Webview2 para usar o suplemento. Para instalar a controladora:

   1. Vá para <http://aka.ms/webview2installer>.
   1. Selecione e baixe o instalador independente Evergreen.
   1. Siga os prompts de instalação.

### Escritório da Web

- Suporta todos os navegadores e versões


## Complemento do Excel do Report Builder

Você deve instalar o Report Builder Excel Add-in para usar o Report Builder for Customer Journey Analytics. Depois de instalar o Report Builder Excel Add-in, você pode acessar o Report Builder em uma pasta de trabalho aberta do Excel.

### Baixe e instale o Report Builder Add-in

Para baixar e instalar o Report Builder Add-in

1. Inicie o Excel e abra uma nova pasta de trabalho.

1. Selecione Inserir > Obter suplementos.

1. Na caixa de diálogo Suplementos do Office, selecione a guia Loja.

1. Procure por &quot;Report Builder&quot; e clique em Adicionar.

1. Na caixa de diálogo Termos de licença e política de privacidade , clique em Continuar.

**Se a guia Loja não for exibida**

1. No Excel, selecione Arquivo > Conta > Gerenciar configurações.

1. Marque a caixa ao lado de &quot;Ativar experiências conectadas opcionais&quot;

1. Reinicie o Excel.

**Se sua organização bloquear o acesso à Microsoft Store**

Entre em contato com a equipe de TI ou de segurança para solicitar aprovação para o Report Builder Add-in. Após a concessão da aprovação, na caixa de diálogo Suplementos do Office, selecione a guia Administrador gerenciado .

![](./assets/image1.png)

Depois de instalar o Report Builder Add-in, o ícone de Report Builder é exibido na faixa do Excel na guia Início.

![](./assets/rb_app_icon.png)

## Faça logon no Report Builder

Depois de instalar o Report Builder for Excel Add-in para sua plataforma operacional ou navegador, siga estas etapas para fazer logon no Report Builder.

1. Abra uma pasta de trabalho do Excel.

1. Clique no ícone Report Builder para iniciar o Report Builder.

1. Na barra de ferramentas do Adobe Report Builder, clique em **Login**.

   ![](./assets/rb_login.png)

1. Insira as informações da conta da Adobe Experience ID. As informações da sua conta devem corresponder às suas credenciais de Customer Journey Analytics.

   ![](./assets/image4.png)

Depois de fazer logon, o ícone de logon e a organização aparecerão na parte superior do painel

## Alternar organizações

Ao fazer logon pela primeira vez, você faz logon na organização padrão atribuída ao perfil.

1. Clique no nome da organização que é exibida ao fazer logon.

1. Selecione uma organização na lista de organizações disponíveis. Somente as organizações às quais você tem acesso são listadas.

   ![](./assets/image5.png)

## Fazer logoff

Você pode fazer logoff no Report Builder a partir do perfil do usuário.

1. Salve as alterações em qualquer pasta de trabalho aberta.

1. Clique no ícone de avatar para exibir seu perfil de usuário.

   ![](./assets/image6.png)

1. Clique em **Sair**.
