---
title: Como definir configurações para o Report Builder no Customer Journey Analytics
description: Descreve como definir as configurações de modo offline, idioma, data de início e solução de problemas.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 87%

---

# Configurações do Report Builder

Use o painel **Configurações** para definir as configurações no nível do aplicativo, como o idioma exibido pela interface ou se deseja, ou não, trabalhar no modo off-line. As configurações são aplicadas imediatamente e são definidas para todas as sessões futuras até serem alteradas.

Para alterar as configurações do Report Builder

1. Clique no ícone de **Configurações**.

1. Faça alterações para Ativar o modo offline, selecione um Idioma ou ative as configurações do log de Solução de problemas.

1. Clique em **Aplicar**.

   ![Painel Intervalo de datas do Report Builder mostrando o botão Cancelar e Aplicar.](./assets/image38.png)

## Modo offline

Ao criar e editar um bloco de dados no modo off-line, os dados não são recuperados. Em vez disso, os dados de simulação são usados para que você possa criar e editar rapidamente um bloco de dados sem esperar a execução da solicitação. Quando você voltar a ficar online, o comando *Atualizar bloco de dados* ou o comando *Atualizar todos os blocos de dados* atualiza os blocos de dados criados com os dados reais.

Para ativar o modo off-line

1. Clique no ícone de **Configurações**.

1. Selecionar **Ativar modo off-line**.

1. Insira um número inteiro positivo no **Exibir dados de métrica como** campo.

1. Clique em **Aplicar**.

## Idioma

Você pode escolher o idioma para a interface do Report Builder. Todos os idiomas suportados pelo Adobe Analytics estão disponíveis.

Para selecionar o idioma usado na interface do Report Builder

1. Clique em Configurações.

1. Selecione um idioma no menu suspenso **Idioma**.

   ![painel Intervalo de datas do Report Builder mostrando a lista Idioma com inglês selecionado.](./assets/image39.png)

1. Clique em **Aplicar.**

## Solução de problemas

Use a configuração Solução de problemas para registrar todos os dados do cliente/servidor em um arquivo local. Use essa opção para ajudar a resolver tíquetes de suporte.

Para ativar a opção Solução de problemas, selecione **Registrar solicitação do Report Builder no arquivo local**.
