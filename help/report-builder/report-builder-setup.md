---
title: Como configurar o Report Builder no Customer Journey Analytics
description: Descreve como configurar o Report Builder no Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 99aedc28-05d5-4fc1-8c32-6e5d1d3b0f84
solution: Customer Journey Analytics
source-git-commit: 065cf61d80ceb3c921ea666ba299e56fb044335b
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 26%

---

# Configuração do Report Builder

Este artigo descreve os requisitos para usar o Report Builder para Customer Journey Analytics no Microsoft Excel. E como instalar e configurar o suplemento.

## Requisitos

O Report Builder para Customer Journey Analytics é compatível com os seguintes sistemas operacionais e navegadores da Web.

### macOS

- macOS versão 10.x ou posterior
- Todas as versões do Excel

### Windows

- Windows 10, versão 1904 ou posterior
- Versão do Excel 2106 ou posterior

  Todos os usuários do Excel para desktop do Windows devem instalar o Microsoft Edge Webview2 para usar o suplemento. Para instalar:

   1. Vá para <https://developer.microsoft.com/en-us/microsoft-edge/webview2/>.
   1. Selecione e baixe a versão apropriada do **[!UICONTROL Instalador autônomo Evergreen]** para sua plataforma.
   1. Execute o instalador e siga os prompts de instalação.

### Web Office

- Suporta todos os navegadores e versões.


## Suplemento do Report Builder Excel

Instale o complemento Report Builder Excel para usar o Report Builder para Customer Journey Analytics. Depois de instalar o complemento Report Builder Excel, você pode acessar o Report Builder de uma pasta de trabalho aberta do Excel.

### Baixe e instale o Suplemento Report Builder

Para baixar e instalar o Suplemento Report Builder

1. Inicie o Excel e abra uma nova pasta de trabalho.

1. Selecione **[!UICONTROL Inserir]** > **[!UICONTROL Suplementos]** > **[!UICONTROL Obter Suplementos]** no menu principal.

1. Na caixa de diálogo Suplementos do Office, selecione a guia **[!UICONTROL Loja]**.

1. Pesquise por `Report Builder` e selecione **[!UICONTROL Adicionar]**.

1. Na caixa de diálogo Termos de licença e política de privacidade, selecione **[!UICONTROL Continuar]**.

Se a guia **[!UICONTROL Loja]** não for exibida:

1. No Excel, selecione **[!UICONTROL Arquivo]** > **[!UICONTROL Conta]** > **[!UICONTROL Gerenciar Configurações]** no menu principal.

1. Marque a caixa ao lado de **[!UICONTROL Habilitar experiências conectadas opcionais]**.

1. Reinicie o Excel.

Se sua organização bloquear o acesso à Microsoft Store:

- Entre em contato com a equipe de TI ou de segurança para solicitar aprovação para o suplemento do Report Builder. Após a concessão da aprovação, na caixa de diálogo **[!UICONTROL Suplementos]** do Office, selecione a guia **[!UICONTROL Administrador Gerenciado]**.

  ![A guia Administrador Gerenciado na caixa de diálogo Suplementos do Office.](./assets/image1.png){zoomable="yes"}

Depois de instalar o suplemento do Report Builder, o ícone ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** é exibido na faixa de opções do Excel, na guia **[!UICONTROL Página Inicial]**.

![O ícone do Report Builder no Excel](./assets/rb_app_icon.png){zoomable="yes"}


## Fazer logon no Report Builder

Após instalar o suplemento Report Builder for Excel para sua plataforma operacional ou navegador, siga estas etapas para fazer logon no Report Builder.

1. Abra uma pasta de trabalho do Excel.

1. Selecione ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** para iniciar o Report Builder.

1. Na barra de ferramentas do Adobe Report Builder, selecione **[!UICONTROL Logon]**.

   ![Clique no botão de logon do Report Builder.](./assets/rb_login.png){zoomable="yes"}

1. Insira as informações da sua conta do Adobe. As informações da sua conta devem corresponder às suas credenciais do Customer Journey Analytics.

   ![Seu ícone e organização de logon.](./assets/image4.png){zoomable="yes"}

Depois de fazer logon, o ícone de logon e a organização aparecerão na parte superior do painel


## Alternar organizações

Ao fazer logon pela primeira vez, você faz logon na organização padrão atribuída ao perfil ou na organização selecionada como parte do fluxo de logon.

1. Selecione o nome da organização que é exibido ao fazer logon.

1. Selecione uma organização na lista de organizações disponíveis. Somente as organizações às quais você tem acesso são listadas.

   ![A lista de organizações que você pode acessar.](./assets/image5.png){zoomable="yes"}

## Fazer logoff

Para sair do Report Builder:

1. Salve as alterações em qualquer pasta de trabalho aberta.

1. Selecione o ícone de avatar para exibir seu perfil de usuário.

   ![O avatar do seu perfil de usuário e o botão Sair.](./assets/image6.png){zoomable="yes"}

1. Selecione **[!UICONTROL Sair]**.
