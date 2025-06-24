---
title: Notas de versão atuais do Customer Journey Analytics
description: Exibir as notas de versão mais recentes do Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 42%

---

# Notas de versão atuais do Adobe Customer Journey Analytics (junho de 2025)

**Última atualização**: 18 de junho de 2025


Essas notas de versão abrangem o período de lançamento de terça-feira, 2 de junho de 2025 a quarta-feira, 15 de julho de 2025. As versões do Adobe Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Sendo assim, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Recursos novos ou atualizados

| Recurso | Descrição | [Início da implantação](releases.md) | [Disponibilidade geral](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **O painel esquerdo do Analysis Workspace não abre e fecha ao passar o mouse** | O painel esquerdo do Analysis Workspace é usado para adicionar componentes, painéis e visualizações ao projeto. A opção de abrir temporariamente o painel esquerdo passando o mouse sobre um dos ícones à esquerda não está mais disponível. Em vez disso, basta clicar em um desses ícones para manter o painel aberto e clicar novamente no ícone para fechá-lo. |  | terça-feira, 2 de junho de 2025 <p>(Planejado originalmente para lançamento em 29 de maio de 2025)</p> |
| **Customer Journey Analytics B2B edition** | O Customer Journey Analytics B2B edition ajuda as empresas B2B a alinhar suas equipes de marketing, vendas e produtos, fornecendo insights de conta acionáveis que impulsionam o crescimento da receita. Com a conta colocada no centro do modelo de dados, toda a análise se concentra na jornada da conta. Adicionar uma nova camada de entidades (contas, oportunidades e grupos de compras) sobre eventos pessoais e baseados em tempo cria uma imagem completa do ciclo de vida de marketing e receita B2B. [Saiba mais](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 de junho de 2025 |
| **Suporte para destinos em nuvem seguros no Report Builder** | Agora é possível exportar relatórios do Report Builder para os seguintes destinos de armazenamento na nuvem:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Anteriormente, você podia compartilhar pastas de trabalho com outros usuários por email, mas não podia exportar relatórios do Report Builder para destinos na nuvem.</p><p>Para obter mais informações, consulte [Agendar pastas de trabalho exportando para destinos na nuvem](/help/report-builder/report-builder-export.md).</p> |  | 19 de junho de 2025 (Originalmente 18 de junho de 2025) |
| **Nova experiência de visualização** | O painel de visualização, que é usado ao criar um segmento ou definir as configurações de uma visualização de dados, agora usa uma visualização de barra horizontal em vez de uma visualização de rosca. |  | 18 de junho de 2025 |
| **Caixa de diálogo do modelo de atribuição modificada** | Agora você pode definir o container e o período separadamente na caixa de diálogo do modelo de atribuição. |  | 18 de junho de 2025 |
| **Mapa de conexão** | Uma nova [interface do mapa de conexões](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#connection-map) está disponível para exibir visualmente a configuração da sua conexão. |  | 18 de junho de 2025 |
| **Adicionar e exibir comentários em projetos do Analysis Workspace** | Um novo recurso [de comentários](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) no Analysis Workspace permite que você compartilhe insights e faça perguntas no contexto de um projeto do Analysis Workspace. Isso pode simplificar as discussões sobre os dados, mantendo conversas no contexto dos dados que estão sendo discutidos. É possível <ul><li>Comentar em qualquer projeto do Analysis Workspace ao qual você tenha acesso</li><li>Comentar em um ponto específico em uma visualização ou fazer comentários gerais sobre um projeto</li><li>Marque outros usuários para notificá-los sobre seus comentários</li><li>Gerenciar comentários existentes (editar, fixar, resolver e assim por diante)</li></ul>Os administradores do Customer Journey Analytics podem [desabilitar comentários no nível da organização](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Os proprietários do projeto podem [desabilitar comentários no nível do projeto](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). | 25 de junho de 2025 | sábado, 11 de julho de 2025 <p>(Planejado originalmente para lançamento em 29 de maio de 2025)</p> |
| **Suporte para pré-renderização do Chrome** | Controla como as bibliotecas de coleção de dados se comportam quando o Chrome pré-renderiza uma página. (Link da documentação a seguir) |  | 30 de junho de 2025 |

## Correções no Customer Journey Analytics

**Alertas**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**Extensão de BI para Tableau**: AN-377488
**Componentes**: AN-376174
**Visualizações de dados**: AN-379011
**Exportar locais**: AN-382191
**Exportação de tabela completa**: AN-375646; AN-376986; AN-380355; AN-381310
**Tela do Jornada**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Relatórios**: AN-372615; AN-378578;


## Avisos importantes para admins do Customer Journey Analytics

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| N/A | | |

## Recursos relacionados

* [Notas de versão anteriores do Customer Journey Analytics de 2025](/help/release-notes/2025.md)
* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)
* [Notas de versão da Coleção de mídia de streaming](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)
* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)
* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
