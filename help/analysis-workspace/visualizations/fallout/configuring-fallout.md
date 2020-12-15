---
description: 'null'
title: Configurar uma visualização de fallout
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 100%

---


# Configurar uma visualização de fallout

>[!NOTE]
>
>Você está visualizando a documentação do Analysis Workspace no Customer Journey Analytics. Seu conjunto de recursos é ligeiramente diferente do [Analysis Workspace no Adobe Analytics tradicional](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html). [Saiba mais...](/help/getting-started/cja-aa.md)

Você pode especificar os pontos de contato para criar uma sequência de fallout multidimensional. Geralmente, um ponto de contato é uma página no seu site. Contudo, pontos de contato não estão limitados a páginas. Por exemplo, você pode adicionar eventos, como unidades, bem como visitantes exclusivos e visitantes que retornam. Você também pode adicionar dimensões, como uma categoria, tipo de navegador ou termo de pesquisa interno.

Você também pode adicionar segmentos em um ponto de contato. Por exemplo, você pode querer comparar segmentos, como usuários de iOS e Android. Arraste os segmentos desejados para o topo do fallout e as informações sobre os segmentos são adicionadas ao relatório de fallout. Se quiser exibir somente esses segmentos, você pode remover a linha de base de Todas as visitas.

Não há limite de número de etapas que você pode adicionar ou do número de dimensões usadas.

Você pode definir o caminho das eVars, incluindo eVars de comercialização e [listVars](https://docs.adobe.com/content/help/pt-BR/analytics/implementation/vars/page-vars/page-variables.html) (variáveis que podem ter vários valores por clique, como produtos, listVars, eVars de comercialização e apoios de listas). Por exemplo, suponha que alguém esteja pesquisando sapatos e camisetas em uma página e camisetas e meias em outra. O próximo relatório de fluxo do produto para sapatos será camisetas e meias, e NÃO camisetas.

1. Arraste uma visualização de [!UICONTROL Fallout] do menu suspenso Visualizações em uma [!UICONTROL Tabela de forma livre].

1. Arraste a dimensão de Página à Tabela de forma livre e arraste uma página de lá (neste caso, Início - JJEsquire) para o campo **[!UICONTROL Adicionar ponto de contato]** como o primeiro ponto de contato.

   ![](assets/fallout1.png)

   Passe o mouse sobre um ponto de contato para ver o fallout e outras informações sobre o nível, como o nome do ponto de contato e o número de visitantes no ponto, e ver a taxa de sucesso do ponto de contato (bem como para comparar a taxa de sucesso com outros pontos de contato).

   Os números circulados, na área em cinza da barra, apresentam o fallout entre os pontos de contato (e não o fallout geral daquele ponto). A % de pontos de contato apresenta o fallthrough bem-sucedido da etapa anterior na etapa atual do relatório de fallout.

   É possível adicionar uma única página ao relatório de fallout, ao invés de uma dimensão inteira. Clique a seta da direita &quot;>&quot; na dimensão da página para selecionar a página específica a ser adicionada no relatório de fallout.

1. Continue a adicionar pontos de contato até concluir a sequência.

   Você pode **combinar vários pontos de contato**, arrastando um ou mais pontos em um ponto de contato.

   >[!NOTE]
   >
   >Quando são vários segmentos, eles são ligados com AND, mas quando são vários itens (como itens de dimensão e métricas), são ligados com OR.

   ![](assets/multiple_obj_touchpoint.png)

1. Também é possível **restringir pontos de contato individuais à próxima ocorrência** (em vez de eventualmente) dentro do caminho. Embaixo de cada ponto de contato, há um seletor com as opções “Caminho eventual” e “Próxima ocorrência”, da seguinte forma:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caminho eventual </p> <p>(Padrão) </p> </td> 
   <td colname="col2"> <p>Visitantes contados que “eventualmente” serão direcionados para a próxima página no caminho, mas não necessariamente na próxima ocorrência. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Próxima ocorrência </p> </td> 
   <td colname="col2"> <p>Visitantes contados que serão direcionados para a próxima página no caminho na próxima ocorrência. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configurações de fallout {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Configuração | Descrição |
|--- |--- |
| Contêiner de fallout <ul><li>Visita</li><li>Visitante</li></ul> | Permite alternar entre Visita e Visitante para analisar a definição do caminho do visitante. O padrão é Visitante.  Essas configurações ajudam você a entender o envolvimento no nível dos visitantes (ao longo das visitas) ou restringir a análise a uma só visita. |
| Mostrar “Todos os visitantes” como primeiro ponto de contato | Você pode desmarcar isso se não quiser ter “Todos os visitantes” como primeiro ponto de contato. |

Quando você **clicar com o botão direito em um ponto de contato**, as seguintes opções são exibidas:

| Opção | Descrição |
|--- |--- |
| Executar tendência do ponto de contato | Veja os dados de tendência para um ponto de contato em um gráfico de linha, com alguns dados de detecção de anomalias pré-construídos. |
| Executar tendência do ponto de contato (%) | Executa a tendência da porcentagem total de fallout. |
| Executar tendência de todos os pontos de contato (%) | Executa a tendência de todas as porcentagens de pontos de contato no fallout (exceto “Todas as visitas”, se incluso), no mesmo gráfico. |
| Analisar fallthrough neste ponto de contato | Visualize o que os visitantes fizeram entre dois pontos de contato (este ponto de contato e o próximo ponto de contato), se continuaram até o próximo ponto de contato. Isso cria uma tabela de forma livre, mostrando suas dimensões. Você pode substituir dimensões e outros elementos da tabela. |
| Analisar o fallout neste ponto de contato | Veja o que as pessoas que não entraram no funil fizeram imediatamente depois da etapa selecionada. |
| Criar segmentos a partir do ponto de contato | Crie um novo segmento a partir do ponto de contato selecionado. |
