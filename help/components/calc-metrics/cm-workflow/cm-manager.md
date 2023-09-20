---
description: O Gerenciador de métricas calculadas permite cuidar de suas métricas de várias maneiras, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciador de métricas calculadas
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: c6b9252f9b938f4659ead7ed5c90cec133e1bd74
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 15%

---

# Gerenciador de métricas calculadas

A página Métrica calculada oferece várias formas de cuidar de métricas, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O Gerenciador de métricas calculadas mostra todos os seus filtros e os compartilhados com você. Usuários de nível administrativo podem ver todas as métricas personalizadas da organização. Essa visão geral apresenta a interface do usuário e os recursos do Gerenciador de métricas calculadas.

![](assets/calc-metric-manager.png)

## Acessar o gerenciador de métricas calculadas

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Métricas calculadas**].

## Ações disponíveis no Gerenciador de métricas calculadas

No Gerenciador de métricas calculadas, é possível:

* [Filtrar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Marcar métricas calculadas como favoritos](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Aprovar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Marcar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportar uma métrica calculada para um arquivo CSV.

* [Copiar métricas calculada](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Excluir métricas calculadas

## Configurar colunas

Você pode configurar as informações exibidas para cada métrica calculada no Gerenciador de métricas calculadas, configurando as colunas exibidas.

Para configurar as colunas visíveis no Gerenciador de métricas calculadas:

1. No Customer Journey Analytics, selecione a variável **[!UICONTROL Componentes]** e selecione **[!UICONTROL Métricas calculadas]**.

1. No Gerenciador de métricas calculadas, selecione **Personalizar colunas** ícone ![Ícone Personalizar colunas](assets/customize-columns-icon.png), em seguida, selecione as colunas que deseja exibir no Gerenciador de métricas calculadas.

   As seguintes colunas estão disponíveis:

   | Título da coluna | Descrição |
   |---|---|
   | Favoritos | Exibe ícones de estrela ao lado de cada métrica calculada, permitindo marcar métricas calculadas como favoritos. Para obter mais informações, consulte [Marcar métricas calculadas como favoritos](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Título e descrição | Esses valores são fornecidos no Criador de métrica calculada. Para editar o título e a descrição, selecione o link de título para abrir o Criador de métrica calculada. |
   | Conjunto de relatórios | Indica em qual conjunto de relatórios a métrica foi salva pela última vez. |
   | Proprietário | Indica o proprietário da métrica personalizada. Como um usuário não administrativo, você pode ver somente as métricas que possui ou que foram compartilhadas com você. |
   | Tags | Mostra as tags aplicadas à métrica, por você ou por pessoas que compartilharam a métrica calculada com você. |
   | Compartilhado com | Lista indivíduos ou grupos (somente administrador) ou Todos (somente administrador) com os quais você compartilhou a métrica calculada. <p>Quando uma métrica calculada está sendo compartilhada, um ícone de compartilhamento é exibido ao lado do nome da métrica calculada.</p> |
   | Data de modificação | Indica a data em que a métrica personalizada foi modificada pela última vez. |
   | Usado em | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra em qual dos seguintes tipos de componentes a métrica calculada está sendo usada no momento:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li></ul> Por exemplo, se os componentes estiverem sendo usados em 40 projetos e 2 métricas calculadas, esta coluna mostrará [!UICONTROL **Métricas calculadas (2), Projetos (40)**]. <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API ou do Report Builder.</p><p>Você pode usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |
   | Última utilização | **Nota:** Essa funcionalidade está na fase de Teste limitado da versão e pode ainda não estar disponível em seu ambiente. Essa nota será removida quando a funcionalidade estiver com disponibilidade geral. Para obter informações sobre o processo de lançamento do Customer Journey Analytics, consulte [Versões de recursos do Customer Journey Analytics](/help/release-notes/releases.md).<p>Mostra a data em que a métrica calculada foi usada pela última vez em qualquer um dos seguintes tipos de componentes:</p> <ul><li>Alertas</li><li>Métricas calculadas </li><li>Projetos</li><li>Projetos programados</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Essas informações não incluem o uso da API ou do Report Builder.</p><p>Você pode usar o [Dicionário de dados](/help/components/data-dictionary/data-dictionary-overview.md) junto com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}
