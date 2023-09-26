---
title: Como configurar o Report Builder no Customer Journey Analytics
description: Descreve como configurar o Report Builder no Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 49a35a256758b259dfb2133658bae617315774e4
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 89%

---

# Configuração do Report Builder

É possível acessar rapidamente o Report Builder usando o menu Suplemento do Excel.

## Requisitos

O Report Builder para o Customer Journey Analytics é compatível com os seguintes sistemas operacionais e navegadores da web.

### macOS

- macOS versão 10.x ou posterior
- Todas as versões do Excel

### Windows

- Windows 10, versão 1904 ou posterior
- Versão do Excel 2106 ou posterior

  Todos os usuários do Excel para desktop do Windows devem instalar o Microsoft Edge Webview2 para usar o suplemento. Para instalar o controlador:

   1. Vá para <https://aka.ms/webview2installer>.
   1. Selecione e baixe o instalador autônomo Evergreen.
   1. Siga o assistente de instalação.

### Web Office

- Suporta todos os navegadores e versões


## Suplemento Report Builder para o Excel

É preciso instalar o Suplemnento Report Builder para Excel caso deseje usar o Report Builder para o Customer Journey Analytics. Depois de instalar o Suplemento Report Builder para Excel, você pode acessar o Report Builder a partir de uma pasta de trabalho aberta do Excel.

### Baixe e instale o Suplemento Report Builder

Para baixar e instalar o Suplemento Report Builder

1. Inicie o Excel e abra uma nova pasta de trabalho.

1. Selecione Inserir > Obter Suplementos.

1. Na caixa de diálogo Suplementos do Office, selecione a guia Loja.

1. Procure por &quot;Report Builder&quot; e clique em Adicionar.

1. Na caixa de diálogo Termos de licença e política de privacidade, clique em Continuar.

**Se a guia Loja não for exibida**

1. No Excel, selecione Arquivo > Conta >Gerenciar configurações.

1. Marque a caixa ao lado de &quot;Habilitar experiências conectadas opcionais&quot;

1. Reinicie o Excel.

**Se sua organização bloquear o acesso à Microsoft Store**

Entre em contato com a equipe de TI ou de segurança para solicitar aprovação para o Suplemento Report Builder. Após a concessão da aprovação, na caixa de diálogo Suplementos do Office, selecione a guia Administrador Gerenciado.

![A guia Administrador Gerenciado na caixa de diálogo Suplementos do Office.](./assets/image1.png)

Depois de instalar o Suplemento Report Builder, o ícone de Report Builder é exibido na faixa de opções da guia Página inicial, do Excel.

![O ícone Report Builder no Excel](./assets/rb_app_icon.png)

## Fazer logon no Report Builder

Depois de instalar o Suplemento Report Builder for Excel na sua plataforma operacional ou navegador, siga estas etapas para fazer logon no Report Builder.

1. Abra uma pasta de trabalho do Excel.

1. Clique no ícone Report Builder para iniciar o Report Builder.

1. Na barra de ferramentas do Adobe Report Builder, clique em **Logon**.

   ![Clique no botão Report Builder login.](./assets/rb_login.png)

1. Insira as informações da conta de ID da Adobe Experience. As informações da sua conta devem corresponder às suas credenciais do Customer Journey Analytics.

   ![Seu ícone de logon e a organização.](./assets/image4.png)

Depois de fazer logon, o ícone de logon e a organização aparecerão na parte superior do painel

## Alternar organizações

Ao fazer logon pela primeira vez, você faz logon na organização padrão atribuída ao perfil.

1. Clique no nome da organização que é exibida ao fazer logon.

1. Selecione uma organização na lista de organizações disponíveis. Somente as organizações às quais você tem acesso são listadas.

   ![A lista de organizações que você pode acessar.](./assets/image5.png)

## Fazer logoff

Você pode fazer logoff do Report Builder a partir do perfil do usuário.

1. Salve as alterações em qualquer pasta de trabalho aberta.

1. Clique no ícone de avatar para exibir seu perfil de usuário.

   ![O avatar do seu perfil de usuário e o botão Sair.](./assets/image6.png)

1. Clique em **Fazer logoff**.
