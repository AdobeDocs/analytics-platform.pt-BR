---
description: Saiba como especificar os pontos de contato para criar uma sequência de fallout multidimensional.
title: Configurar uma visualização de fallout
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
source-git-commit: ab30cd4e884dbf92d4148e8f81a638a8ea0b63f3
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 68%

---

# Configurar uma visualização de fallout

Você pode especificar os pontos de contato para criar uma sequência de fallout multidimensional. Geralmente, um ponto de contato é uma página no seu site. Contudo, pontos de contato não estão limitados a páginas. Por exemplo, você pode adicionar eventos, como unidades, bem como pessoas únicas e visitas de retorno. Você também pode adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interno.

Você também pode adicionar filtros em um ponto de contato. Por exemplo, você pode querer comparar filtros, como usuários de iOS e Android. Arraste os filtros desejados para o topo do fallout e as informações sobre os filtros são adicionadas ao relatório de fallout. Se quiser exibir somente esses filtros, é possível remover a linha de base Todas as visitas.

Não há limite de número de etapas que você pode adicionar ou do número de dimensões usadas.

É possível definir o caminho das eVars, incluindo eVars de merchandising e [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=pt-BR) (variáveis que podem ter vários valores por evento, como produtos, listVars, eVars de merchandising e propriedades de lista). Por exemplo, suponha que alguém esteja pesquisando sapatos e camisetas em uma página e camisetas e meias em outra. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

1. Arraste uma visualização de [!UICONTROL Fallout] do menu suspenso Visualizações em uma [!UICONTROL Tabela de forma livre].

1. Arraste a dimensão de Página à Tabela de forma livre e arraste uma página de lá (neste caso, Início - JJEsquire) para o campo **[!UICONTROL Adicionar ponto de contato]** como o primeiro ponto de contato.

   ![A lista suspensa Todas as visitas mostrando o JJEsquire arrastado para o campo Adicionar ponto de contato.](assets/fallout1.png)

   Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre o nível, como o nome do ponto de contato e a contagem de pessoas no ponto, e ver a taxa de sucesso do ponto de contato (bem como comparar a taxa de sucesso com outros pontos de contato).

   Os números circulados, na área em cinza da barra, apresentam o fallout entre os pontos de contato (e não o fallout geral daquele ponto). A % de pontos de contato apresenta o fallthrough bem-sucedido da etapa anterior na etapa atual do relatório de fallout.

   É possível adicionar uma única página ao relatório de fallout, ao invés de uma dimensão inteira. Clique a seta da direita &quot;>&quot; na dimensão da página para selecionar a página específica a ser adicionada no relatório de fallout.

1. Continue a adicionar pontos de contato até concluir a sequência.

   Você pode **combinar vários pontos de contato**, arrastando um ou mais pontos em um ponto de contato.

   >[!NOTE]
   >
   >Quando são vários filtros, eles são ligados com AND. No caso de vários itens (como itens de dimensão e métricas), são ligados com OR.

   ![A página: CamerRoll ou Página: Pontos de contato da câmera destacados.](assets/multiple_obj_touchpoint.png)

1. Também é possível **restringir pontos de contato individuais ao próximo evento** (em vez de &quot;eventualmente&quot;) dentro do caminho. Embaixo de cada ponto de contato, há um seletor com as opções “Caminho eventual” e “Próxima ocorrência”, da seguinte forma:

   ![A exibição Todas as visitas mostrando a opção Caminho eventual foi realçada. ](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caminho eventual </p> <p>(Padrão) </p> </td> 
   <td colname="col2"> <p>São contados os visitantes que serão "eventualmente" direcionados à próxima página do caminho, mas não necessariamente ao próximo evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Próxima ocorrência </p> </td> 
   <td colname="col2"> <p>São contados os visitantes que chegarão à próxima página do caminho no próximo evento. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configurações de fallout {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Configuração | Descrição |
|--- |--- |
| Contêiner de fallout <ul><li>Visita</li><li>Visitante</li></ul> | Permite alternar entre Visita e Visitante para analisar a definição do caminho da pessoa. O padrão é Visitante.  Essas configurações ajudam você a entender o envolvimento da pessoa no nível da pessoa (em várias visitas) ou restringir a análise a uma única visita. |

Quando você **clicar com o botão direito em um ponto de contato**, as seguintes opções são exibidas:

| Opção | Descrição |
|--- |--- |
| Executar tendência do ponto de contato | Veja os dados de tendência para um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-construídos. |
| Executar tendência do ponto de contato (%) | Executa a tendência da porcentagem total de fallout. |
| Executar tendência de todos os pontos de contato (%) | Executa a tendência de todas as porcentagens de pontos de contato no fallout (exceto “Todas as visitas”, se incluso), no mesmo gráfico. |
| Analisar fallthrough neste ponto de contato | Visualize o que as pessoas fizeram entre dois pontos de contato (este ponto de contato e o próximo ponto de contato), se continuaram até o próximo ponto de contato. Isso cria uma tabela de forma livre, mostrando suas dimensões. Você pode substituir dimensões e outros elementos da tabela. |
| Analisar o fallout neste ponto de contato | Veja o que as pessoas que não entraram no funil fizeram imediatamente depois da etapa selecionada. |
| Criar filtro desde o ponto de contato | Criar um novo filtro a partir do ponto de contato selecionado. |
