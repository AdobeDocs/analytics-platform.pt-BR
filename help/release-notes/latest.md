---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a6ce6409eb7a4d853d5390cd62f4a9506ee6282a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 39%

---

# Notas de versão do Customer Journey Analytics atual (CJA) (janeiro de 2023)

**Última atualização**: 23 de janeiro de 2023

As versões do Customer Journey Analytics operam em um [modelo de entrega contínua](releases.md) que permite uma abordagem escalável e em fases para a implantação de recursos. Devido a isso, essas notas de versão são atualizadas várias vezes por mês. Verifique-as regularmente.

## Principais recursos e atualizações

| Recurso | Descrição | [Início da implantação](/help/release-notes/releases.md) | [Disponibilidade geral](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Atualização para públicos-alvo do CJA** | Depois de criar um público-alvo, [O Adobe cria um segmento de Experience Platform streaming para cada novo público-alvo do CJA](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). | N/D | 23 de janeiro de 2023 |
| **Pastas no Espaço de trabalho** | As pastas ajudam a organizar e categorizar seus projetos para obter uma melhor recuperação e acesso. Além disso, um **[!UICONTROL Empresa]** permite que os administradores criem e compartilhem conteúdo com todos os usuários do Workspace. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=pt-BR) | N/D | 11 de janeiro de 2023 |
| **Página de destino padrão** | O [nova landing page](/help/getting-started/landing.md) que foi introduzido anteriormente em 2022 se tornará a experiência padrão para todos os usuários no **11 de janeiro de 2023**. A landing page herdada será substituída e todos terão de usar a nova experiência. | N/D | 11 de janeiro de 2023 |
| **Página do Gerenciador de projetos obsoleta** | Com o lançamento da nova landing page, descontinuamos o **[!UICONTROL Gerenciador de projetos]** conforme listado em **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Componentes]**. A nova landing page tem todas as funcionalidades da antiga página do Gerenciador de projetos e muito mais. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | N/D | 11 de janeiro de 2023 |
| **Agendar pastas de trabalho no Report Builder** | No Customer Journey Analytics, você pode criar agendamentos para enviar pastas de trabalho em intervalos regulares. Agora os recipients podem receber as atualizações mais recentes de suas pastas de trabalho regularmente. [Saiba mais](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | N/D | 11 de janeiro de 2023 |
| **Salvar novos projetos automaticamente** | O Analysis Workspace agora salva automaticamente os projetos recém-criados. Se, por qualquer motivo, você perder inesperadamente o acesso a um projeto recém-criado antes de salvá-lo manualmente, uma versão de recuperação do projeto agora estará disponível. Anteriormente, os projetos eram salvos automaticamente somente depois de terem sido salvos manualmente inicialmente. [Saiba mais](/help/analysis-workspace/build-workspace-project/save-projects.md) | N/D | 11 de janeiro de 2023 |
| **Preferências do usuário aprimoradas** | Agora você pode configurar preferências adicionais no nível do usuário (em [!UICONTROL Componentes] > [!UICONTROL Preferências]). Ao definir a preferência do usuário, suas seleções se estendem por projetos, tabelas e visualizações. A página Preferências agora contém as novas guias a seguir, cada uma contendo muitas novas opções de configuração:<ul><li>Tabela de forma livre</li><li>Visualizações>/li></ul>. Além disso, agora há mais preferências disponíveis na variável **[!UICONTROL Geral]** e **[!UICONTROL Projeto]** guias.<p>Anteriormente, muitas dessas preferências eram configuráveis somente para projetos, tabelas e visualizações individuais. [Saiba mais](/help/analysis-workspace/user-preferences.md) | N/D | 11 de janeiro de 2023 |

{style=&quot;table-layout:auto&quot;}

## Correções

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Avisos importantes para administradores do CJA

| Aviso | Aviso adicionado ou atualizado | Descrição |
| --- | --- | --- |
| **Melhoria no mapeamento de IP para geolocalização** | 29 de setembro de 2022 | O fornecedor de pesquisas de IP da Adobe, Digital Element, está atualizando para um novo conjunto de dados aprimorado (NetAcuity Pulse) de mapeamento de IP para geolocalização. A Adobe Analytics adiou a adoção desse novo conjunto de dados para **11 de janeiro de 2023**. O novo banco de dados será mais preciso que as versões anteriores. Alguns mapeamentos de IP para geolocalização serão alterados/melhorados quando o novo banco de dados for adotado.<p> Os dados do CJA fornecidos por meio do [!UICONTROL Conector de origem do Analytics] também aproveitarão automaticamente os novos mapeamentos. |

{style=&quot;table-layout:auto&quot;}


## Recursos relacionados

* [Notas de versão anteriores do CJA para 2022](/help/release-notes/2022.md)

* [Notas de versão do Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=pt-BR)

* [Notas de versão do Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=pt-BR)

* [Notas de versão da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR)

* [Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
