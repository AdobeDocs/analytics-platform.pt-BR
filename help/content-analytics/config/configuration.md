---
title: Configurar o Content Analytics
description: Uma visão geral de como configurar o Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# Configurar o Content Analytics

>[!WARNING]
>
>Este artigo é um rascunho não oficial preliminar de uma versão final futura e faz parte da documentação do Content Analytics. Todo o conteúdo está sujeito a alterações e nenhuma obrigação legal pode ser derivada da versão atual deste artigo.
>

{{release-limited-testing}}


Para configurar o Content Analytics para sua organização, use a [configuração guiada](guided.md) do Content Analytics. O assistente de configuração o orienta por todas as etapas necessárias para definir os pré-requisitos para uma configuração automática do Content Analytics.

Após uma implementação bem-sucedida, você pode fazer algumas alterações usando o assistente de configuração guiado. Entretanto, [alterações manuais](manual.md) podem ser necessárias.

## Pré-requisitos

Antes de configurar o Content Analytics, verifique se os seguintes pré-requisitos foram atendidos:

* Você incluiu na lista de permissões o Agente do usuário e o endereço IP do serviço de recursos usado no Content Analytics. A cadeia de caracteres do Agente do Usuário é `AdobeFeaturization/1.0`.
* Você tem uma função de Administrador de produto do Customer Journey Analytics, com as permissões adicionais para gerenciar conexões e coleções de dados. As permissões necessárias do Experience Platform são:

  | Categoria | Permissão | Descrição |
  |---|---|---|
  | [!UICONTROL Coleta de dados] | Exibir fluxos de dados | Acesso somente leitura a sequências de dados. |
  | [!UICONTROL Coleta de dados] | Gerenciar fluxos de dados | Acesso para ler, criar, editar e excluir sequências de dados. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Exibir Esquemas] | Acesso somente leitura a esquemas e recursos relacionados. |
  | [!UICONTROL Modelagem de dados] | [!UICONTROL Gerenciar esquemas] | Acesso para ler, criar, editar e excluir esquemas e recursos relacionados. |
  | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Exibir Conjuntos de Dados] | Acesso somente leitura para conjuntos de dados e esquemas. |
  | [!UICONTROL Gerenciamento de dados] | [!UICONTROL Gerenciar conjuntos de dados] | Acesso para ler, criar, editar e excluir conjuntos de dados. Acesso somente leitura para esquemas. |
  | [!UICONTROL Assimilação de dados] | [!UICONTROL Gerenciar fontes] | Acesso para ler, criar, editar e desativar fontes. |
  | [!UICONTROL Identity Management] | [!UICONTROL Exibir Namespaces De Identidade] | Acesso somente leitura para namespaces de identidade. |

* Você considerou cuidadosamente as seguintes opções de configuração importantes:

   * Seu site é adequado para relatórios de experiência? O relatório de experiência adequado só é possível quando as seguintes condições são atendidas:
      * O conteúdo do site é orientado somente por URLs.
      * As páginas do site podem ser reproduzidas usando o URL da página, e você entende quais parâmetros opcionais de URL geram experiências.
   * Você tem uma compreensão clara de quais páginas deseja capturar a análise e os insights do engajamento de conteúdo.
   * Você tem uma compreensão clara sobre quais (tipos de) ativos deseja capturar a análise e os insights do envolvimento de conteúdo.


>>
[!MORELIKETHIS]
>>
* [Configuração guiada](guided.md)
* [Configuração manual](manual.md)
* [Controle de acesso](/help/technotes/access-control.md)
>


