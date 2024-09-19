---
description: O Gerenciador de métricas calculadas permite cuidar de suas métricas de várias maneiras, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.
title: Gerenciador de métricas calculadas
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: e994a53934ae25802fb16e912d0fdee32d5ea524
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 12%

---

# Gerenciador de métricas calculadas

A página Métrica calculada oferece várias formas de cuidar de métricas, como compartilhar, filtrar, marcar, aprovar, copiar, excluir e marcar como favoritos.

O Gerenciador de métricas calculadas mostra todos os seus filtros e os compartilhados com você. Usuários de nível administrativo podem ver todas as métricas personalizadas da organização. Essa visão geral apresenta a interface do usuário e os recursos do Gerenciador de métricas calculadas.

![Janela de métricas calculadas mostrando os filtros disponíveis.](assets/calc-metric-manager.png)

## Acessar o gerenciador de métricas calculadas

1. No Customer Journey Analytics, selecione [!UICONTROL **Componentes**] > [!UICONTROL **Métricas calculadas**].

## Ações disponíveis no Gerenciador de métricas calculadas

No Gerenciador de métricas calculadas, é possível:

* [Filtrar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Marcar métricas calculadas como favoritas](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Aprovar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Marcar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Compartilhar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportar uma métrica calculada para um arquivo CSV.

* [Copiar métricas calculadas](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Excluir métricas calculadas

## Configurar colunas

Você pode configurar as informações exibidas para cada métrica calculada no Gerenciador de métricas calculadas, configurando as colunas exibidas.

Para configurar as colunas visíveis no Gerenciador de métricas calculadas:

1. No Customer Journey Analytics, selecione a guia **[!UICONTROL Componentes]** e selecione **[!UICONTROL Métricas calculadas]**.

1. No gerenciador de métricas calculadas, selecione o ícone **Personalizar colunas** ![Ícone Personalizar colunas](assets/customize-columns-icon.png) e selecione as colunas que deseja exibir no gerenciador de métricas calculadas.

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
   | Usado em | Mostra onde as métricas calculadas estão sendo usadas atualmente e quantas vezes elas estão sendo usadas em cada área. <p>Por exemplo, se a métrica calculada estiver sendo usada em 40 projetos e 2 alertas, o valor dessa coluna será exibido como [!UICONTROL **42 componentes**]. <p>Selecione o valor desta coluna para ver o detalhamento de onde as métricas calculadas estão sendo usadas (por exemplo, [!UICONTROL **Projetos (40)**], [!UICONTROL **Scorecards para dispositivos móveis (2)**]). Além disso, é possível visualizar a lista de itens em que as métricas calculadas estão sendo usadas. Por exemplo, para ver a lista de projetos em que estão sendo usados, selecione o link [!UICONTROL **Projetos (40)**].</p><p>Cada uma das áreas a seguir mostra o número de instâncias de métricas calculadas que estão sendo usadas nessa área:</p> <ul><li>[!UICONTROL **Projetos**]<p>Contém métricas calculadas que foram [criadas no construtor de métricas calculadas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) e que estão disponíveis para todos os projetos.</p></li><li>[!UICONTROL **Componentes ad hoc**]<p>Contém métricas calculadas que foram [criadas como métricas calculadas rápidas](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) e que estão disponíveis somente em um único projeto.</p></li><li>[!UICONTROL **Projetos programados**]</li><li>[!UICONTROL **Scorecards para dispositivos móveis**]</li><li>[!UICONTROL **Anotações**]</li><li>[!UICONTROL **Report Builder**]<p>Selecionar essa opção baixa um arquivo CSV com as seguintes colunas de dados:</p><ul><li>Nome do Report Builder</li><li>Último acesso</li><li>ID de usuário IMS acessada pela última vez</li><li>Nome do usuário acessado por último</li></ul><p>Ao visualizar informações sobre o Report Builder, as informações de uso estarão disponíveis a partir de setembro de 2024.</p></li></ul><p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização, onde é usado e se precisa ser excluído ou modificado.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações estão disponíveis somente para administradores do sistema.</li><li>A coluna [!UICONTROL **Usado em**] não é exibida por padrão. [Configure as colunas](#configure-columns) para exibi-las.</li><li>Se uma métrica calculada incluir outra métrica calculada em sua definição, o uso dessa métrica calculada não será mostrado na coluna [!UICONTROL **Usado em**]. Se uma métrica calculada for incluída na definição de outro tipo de componente (como um filtro), o uso será mostrado na coluna [!UICONTROL **Usado em**].</li><li>Essas informações não incluem o uso da API ou da Data Warehouse.</li><li>Se não houver dados nesta coluna para um determinado componente, mas ela tiver uma data [!UICONTROL **Última utilização**], o componente pode ter sido usado em uma análise sem ser salvo.</li><li>As informações de uso disponíveis são a partir de setembro de 2023.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização.</p> |
   | Última utilização | Mostra a data em que a métrica calculada foi usada pela última vez em qualquer um dos seguintes tipos de componentes: <ul><li>Métricas calculadas</li><li>Projetos</li><li>Projetos programados</li></ul> <p>Essas informações podem ajudar você a determinar se um componente é valioso para os usuários em sua organização ou se deve ser excluído.</p><p>Considere o seguinte ao visualizar esta coluna:</p><ul><li>Essas informações não incluem o uso da API, Report Builder ou Data Warehouse.</li><li>Para alguns componentes, essa coluna pode não conter dados se o componente tiver sido usado pela última vez antes de setembro de 2023.</li><li>Essas informações estão disponíveis somente para administradores do sistema.</li></ul><p>Você pode usar o [Dicionário de Dados](/help/components/data-dictionary/data-dictionary-overview.md) juntamente com essas informações para ajudá-lo a acompanhar e entender melhor como os componentes estão sendo usados em sua organização. |

   {style="table-layout:auto"}
