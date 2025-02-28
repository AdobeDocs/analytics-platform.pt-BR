---
title: Configurar o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 596e54a559bac69214e1de3ea37da6177f110b7a
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---

# Configurar o Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{{release-limited-testing}}

A configuração do Content Analytics consiste nas seguintes etapas:

![Configuração do Content Analytics](../assets/aca-configuration.svg)

1. Use o assistente de [configuração guiada](guided.md) do Content Analytics para orientá-lo por todas as etapas necessárias para definir os pré-requisitos de uma configuração do Content Analytics. Você pode salvar suas configurações e retornar mais tarde.
1. Quando estiver familiarizado com os valores de configuração, você poderá implementá-los. Essa implementação cria todos os artefatos necessários com base no que você configurou no assistente. Os seguintes artefatos são criados, atualizados ou selecionados:
   * Análise de Jornada personalizada
      * Uma [visualização de dados](/help/data-views/data-views.md) está selecionada.
      * Uma [conexão](/help/connections/overview.md) está selecionada, derivada automaticamente da exibição de dados selecionada.
   * Experience Platform
      * A sandbox é selecionada, derivada automaticamente da conexão. Os fluxos de trabalho e serviços necessários são ativados na sandbox.
      * Os esquemas do Content Analytics são selecionados na sandbox. Se não estiverem disponíveis, os esquemas necessários serão criados.
      * Conjuntos de dados do Content Analytics selecionados na sandbox. Se não estiverem disponíveis, os conjuntos de dados necessários serão criados.
   * Coleta de dados
      * Uma sequência de dados é criada e um serviço do Experience Platform é configurado na sequência de dados para transmitir dados para o conjunto de dados do evento de experiência do Content Analytics.
      * Uma propriedade Tag é criada com a extensão Adobe Content Analytics configurada para a sandbox correta, a sequência de dados e outras opções de configuração no assistente de configuração.
1. Somente quando você publica manualmente a propriedade Tag, o Content Analytics é efetivamente implantado e ativado.
1. Você só pode fazer algumas alterações limitadas em uma configuração implementada usando o assistente de [configuração guiada](guided.md). Por exemplo, altere a [visualização de dados](/help/data-views/data-views.md).
1. Você pode fazer outras alterações em uma configuração implementada por meio da [extensão do Adobe Content Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) na propriedade de Marca associada.
1. Somente quando você republica manualmente a propriedade Tag, as modificações de configuração das etapas 4 e 5 são efetivamente implantadas e ativadas.


Antes de configurar o Content Analytics, verifique se os seguintes pré-requisitos foram atendidos:


>[!PREREQUISITES]
>
>* Você incluiu na lista de permissões o Agente do usuário e o endereço IP do serviço de recursos usado no Content Analytics. A cadeia de caracteres do Agente do Usuário é `AdobeFeaturization/1.0`.
>* Você tem uma função de Administrador de produto do Customer Journey Analytics, com as permissões adicionais para gerenciar conexões e coleções de dados. As permissões necessárias do Experience Platform são:
>  
>   | Categoria | Permissão | Descrição |
>   |---|---|---|
>   | [!UICONTROL Coleta de dados] | Exibir fluxos de dados | Acesso somente leitura a sequências de dados. |
>   | [!UICONTROL Coleta de dados] | Gerenciar fluxos de dados | Acesso para ler, criar, editar e excluir sequências de dados. |
>   | [!UICONTROL Modelagem de dados] | [!UICONTROL Exibir Esquemas] | Acesso somente leitura a esquemas e recursos relacionados. |
>   | [!UICONTROL Modelagem de dados] | [!UICONTROL Gerenciar esquemas] | Acesso para ler, criar, editar e excluir esquemas e recursos relacionados. |
>   | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Exibir Conjuntos de Dados] | Acesso somente leitura para conjuntos de dados e esquemas. |
>   | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Gerenciar conjuntos de dados] | Acesso para ler, criar, editar e excluir conjuntos de dados. Acesso somente leitura para esquemas. |
>   | [!UICONTROL Assimilação de dados] | [!UICONTROL Gerenciar fontes] | Acesso para ler, criar, editar e desativar fontes. |
>   | [!UICONTROL Identity Management] | [!UICONTROL Exibir Namespaces De Identidade] | Acesso somente leitura para namespaces de identidade. |
>
>* Você considerou cuidadosamente as seguintes opções de configuração importantes:
>
>   * Seu site é adequado para relatórios de experiência? O relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
>   * O conteúdo do site é orientado somente por URLs.
>   * As páginas do site podem ser reproduzidas usando o URL da página, e você entende quais parâmetros opcionais de URL geram experiências.
>* Você tem uma compreensão clara de quais páginas deseja capturar a análise e os insights do engajamento de conteúdo.
>* Você tem uma compreensão clara sobre quais (tipos de) ativos deseja capturar a análise e os insights do envolvimento de conteúdo.
>


>[!MORELIKETHIS]
>
>* [Configuração guiada](guided.md)
>* [Configuração manual](manual.md)
>* [Controle de acesso](/help/technotes/access-control.md)
>


