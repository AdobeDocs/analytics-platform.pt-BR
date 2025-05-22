---
title: Projete o seu esquema para uso com o Customer Journey Analytics
description: Saiba mais sobre o caminho recomendado ao atualizar do Adobe Analytics para o Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

---

# Projete o seu esquema para uso com o Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Projetar um esquema"
>abstract="Discuta sobre os requisitos da coleção de dados em sua organização e determine como deseja criar um esquema para uso na Adobe Experience Platform. Essa etapa aparece porque você deseja usar o processo recomendado de utilização de um esquema personalizado para sua organização. Executar corretamente essa etapa é essencial, pois ter um esquema ao qual todas as equipes em sua organização se alinham facilita muito a assimilação de dados.<br><br>O tempo estimado para alinhar todas as partes relevantes em sua organização a um esquema unificado é de 1 a 2 meses. Esse intervalo de tempo depende muito do número de equipes que é necessário coordenar e do número de dimensões e métricas às quais elas devem se alinhar."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

A Adobe recomenda criar um esquema personalizado do Experience Data Model (XDM) para usar com o SDK da web ao atualizar do Adobe Analytics para o Customer Journey Analytics. Alternativamente, você pode usar o esquema padrão do Adobe Analytics, que usa o grupo de campos Adobe Analytics ExperienceEvent.

Um esquema personalizado do XDM permite um esquema agilizado feito sob medida para suprir as necessidades da sua organização e dos aplicativos específicos da Platform que você usa. Diferentemente do esquema padrão do Adobe Analytics, que usa o grupo de campos Adobe Analytics ExperienceEvent, quando alterações forem necessárias em um esquema personalizado do XDM, não será necessário percorrer milhares de campos não usados para localizar o campo que requer atualização.

Para mais informações sobre essas opções de esquema, consulte [Escolha o seu esquema para o Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Revise as seções a seguir ao começar a projetar o esquema do XDM.

## Evite restrições do Adobe Analytics no esquema do XDM

A arquitetura subjacente do Customer Journey Analytics oferece muito mais flexibilidade que a do Adobe Analytics. A criação de um novo esquema do XDM é uma maneira essencial de aproveitar essa flexibilidade. Ao atualizar para o Customer Journey Analytics, evite transportar restrições desnecessárias do Adobe Analytics para o esquema.

>[!NOTE]
>
>As informações a seguir ainda não estão completas. Elas estarão completas em breve.

| Arquitetura de dados do Adobe Analytics | Arquitetura do esquema do XDM |
|---------|----------|
| Métricas individuais são adicionadas à arquitetura de dados do Analytics.<br/>Por exemplo, no Adobe Analytics, há uma eVar diferente para cada evento. | Crie métricas individuais na visualização de dados em vez de no esquema do XDM. Isso proporciona mais flexibilidade, caso você precise fazer alterações posteriormente.<br/>Por exemplo, no Customer Journey Analytics, há apenas um evento no esquema, e os eventos são criados na visualização de dados. |
| Propriedades e eVars são necessários para criar variáveis personalizadas. |  |

## Identifique a equipe de dados e outras partes interessadas em toda a organização

>[!NOTE]
>
>Essas informações ainda não estão disponíveis. Elas estarão disponíveis em breve.

## Considere outros aplicativos da Adobe Experience Platform usados na sua organização

>[!NOTE]
>
>Essas informações ainda não estão disponíveis. Elas estarão disponíveis em breve.
