---
title: Configurações de componente
description: Exibir as configurações principais de um componente de visualização de dados.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: da34e4c97720ec20f354a4bd67708b4d89c5bea4
workflow-type: ht
source-wordcount: '370'
ht-degree: 100%

---

# Configurações de componente

Configurações principais que um componente de visualização de dados usa.

![Configurações de componente](../assets/component-settings.png)

| Configuração | Descrição/Caso de uso |
| --- | --- |
| [!UICONTROL Tipo de componente] | Obrigatório. Permite alterar um componente de Métrica para Dimensão ou vice-versa. Alterar essa lista suspensa altera o componente para sua respectiva área de componentes incluída. |
| [!UICONTROL Nome do componente] | Obrigatório. Permite especificar o nome amigável que aparecerá no Analysis Workspace. É possível renomear um componente, dando a ele um nome específico para a visualização de dados. |
| [!UICONTROL Descrição] | Opcional, mas recomendado. Fornece informações sobre o componente para outros usuários. |
| [!UICONTROL Tags] | Opcional. Permite marcar o componente com tags personalizadas ou prontas para uso para facilitar a pesquisa/filtragem na interface do Analysis Workspace. |
| [!UICONTROL Nome do campo] | O nome do campo de esquema. |
| [!UICONTROL Tipo de conjunto de dados] | Obrigatório. Um campo não editável que mostra de qual tipo de conjunto de dados (evento, pesquisa ou perfil) o componente veio. |
| [!UICONTROL Conjunto de dados] | Um campo não editável que mostra de qual conjunto de dados o componente se originou. Este campo pode conter vários conjuntos de dados. |
| [!UICONTROL Tipo de dados de esquema] | Um campo não editável que mostra o tipo de dados do componente.  Embora você possa usar qualquer tipo de campo de esquema compatível na plataforma, nem todos os tipos de campos são compatíveis no CJA. Os seguintes tipos de dados são compatíveis: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` e `Boolean`. No momento, somente o tipo de dados `String` do esquema é permitido nos conjuntos de dados de Pesquisa. |
| [!UICONTROL ID de componente] | Obrigatório. A [API CJA](https://adobe.io/cja-apis/docs) usa esse campo para fazer referência ao componente. Cada componente em uma visualização de dados deve ser exclusivo. A Adobe gera automaticamente uma ID para cada componente; no entanto, você pode clicar no ícone editar e modificar a ID do componente. Alterar a ID do componente interrompe todos os projetos existentes do Espaço de trabalho que contêm esse componente. Embora cada componente precise de uma ID exclusiva em uma única visualização de dados, é possível usar a mesma ID do componente em outras visualizações de dados. Se você usar a mesma ID do componente em outras visualizações de dados, será possível tornar os projetos do Espaço de trabalho compatíveis entre as visualizações de dados. |
| [!UICONTROL  Caminho do esquema] | Obrigatório. Um campo não editável que mostra o caminho do esquema de onde o componente veio. |
| [!UICONTROL Ocultar componente nos relatórios] | Permite a preparação do componente fora da visualização de dados para não administradores. Os administradores ainda podem acessá-lo clicando em [!UICONTROL Mostrar todos os componentes] em um projeto do Analysis Workspace. |

Este é um vídeo sobre configurações de componentes em visualizações de dados:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
