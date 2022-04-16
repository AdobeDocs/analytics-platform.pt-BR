---
title: Visualizar as notas de versão atuais do Customer Journey Analytics
description: Notas de versão mais recentes do CJA
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# Notas de versão do Customer Journey Analytics atual (CJA) (abril de 2022)

>[!NOTE]
>
>Esta página contém informações de pré-lançamento que estão sujeitas a alterações.

**Última atualização**: 13 de abril de 2022

## Recursos principais

| Recurso | Descrição | [Data Alvo](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Substrings de Dimension | Fornece vários métodos para extrair a parte desejada de uma string para uso como itens de dimensão. Esse recurso também permite tratar uma dimensão de string como uma matriz se a string contiver valores delimitados. [Saiba mais](../data-views/component-settings/substring.md) | 20 de abril de 2022 |
| Preparação de dados para o Analytics Source Connector | O [Conector de origem do Analytics](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=pt-BR) agora está integrado ao [Preparação de dados](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) recursos fornecidos pela Adobe Experience Platform. Os clientes do Adobe Real-time Customer Data Platform (RTCDP), CJA e Adobe Journey Optimizer (AJO) agora podem estender o grupo de campos do Analytics com grupos de campos adicionais. Eles também podem aproveitar mais de 100 operadores de Preparação de dados para enriquecer os dados do Analytics durante a assimilação no Adobe Experience Platform (AEP). Os clientes da RTCDP agora podem ativar vários conjuntos de relatórios habilitados para Preparação de dados para o Perfil.<p>Os clientes do CJA que assimilam vários conjuntos de relatórios por meio do Conector de origem do Analytics agora têm uma maneira de desfazer conflitos entre as diferenças de coluna entre os conjuntos de relatórios. Por exemplo, se &quot;Termo de pesquisa&quot; for armazenado em `eVar1` em um conjunto de relatórios e em `eVar2` em outro conjunto de relatórios, usando Preparação de dados, é possível estender o grupo de campos do Analytics com uma nova coluna que mescla os valores das duas eVars. | 25 de abril de 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Atualizações de documentação do Customer Journey Analytics](/help/release-notes/doc-changes.md)
