---
title: Como programar pastas de trabalho usando o Report Builder no Customer Journey Analytics
description: Saiba como usar o recurso de agendamento no Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 7429d8f9-1e8f-4fbd-8b04-cbe7adbff3e2
source-git-commit: d40638272263a389421adfe224649e2b905c652b
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 90%

---

# Programar pastas de trabalho

Depois de salvar a pasta de trabalho e concluir a análise, é possível compartilhar facilmente a pasta de trabalho com outras pessoas em sua equipe usando o recurso de programação. O recurso Programação permite criar um uma programação que atualiza automaticamente os dados na pasta de trabalho e envia por email o arquivo .xlsx da pasta de trabalho do Excel como um anexo para o público-alvo especificado em uma data e hora específicas. Configurar uma programação fornece atualizações regulares aos recipients automaticamente. Você também pode usar o recurso de programação para enviar a pasta de trabalho uma vez sem programar atualizações automáticas.

Você pode criar várias programações para uma única pasta de trabalho. Por exemplo, você pode enviar uma pasta de trabalho para sua equipe diariamente e enviar a pasta de trabalho para seu gerente uma vez por semana criando duas programações diferentes.

O recurso Programação também permite que você configure a proteção por senha para uma pasta de trabalho e edite pastas de trabalho previamente programadas.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Agendar uma pasta de trabalho

Use o botão Programar tarefa no hub do Report Builder para criar com rapidez uma programação para que você possa distribuir automaticamente um arquivo Excel de pasta de trabalho (.xlsx) para um indivíduo ou grupo.

1. Clique no botão Programação no hub do Report Builder.

   ![](./assets/schedule-button.png){width="55%"}

1. Clique em Programar pasta de trabalho ou no botão de mais no canto superior esquerdo para criar uma nova pasta de trabalho programada.

   ![Descrição alt](./assets/schedule-workbook.png){width="55%"}

   O painel de programação exibe algumas informações predefinidas sobre a pasta de trabalho, como o nome da pasta de trabalho e a última data em que a pasta de trabalho foi modificada.

   ![Descrição alt](./assets/schedule-pane.png){width="55%"}

1. (Opcional) Insira um nome de arquivo.

   O nome do arquivo da pasta de trabalho é padronizado com o nome da pasta de trabalho, mas você pode alterá-lo se quiser. Se estiver enviando a mesma pasta de trabalho para vários públicos-alvo e quiser nomeá-la de forma um pouco mais intuitiva para um determinado público-alvo, é possível alterar o nome.

1. (Opcional) Selecione **Anexar carimbo de data/hora ao nome do arquivo**.

   Você pode anexar um carimbo de data e hora ao nome do arquivo para identificar a data em que a pasta de trabalho foi atualizada. Isso é útil para ver rapidamente qual versão de uma pasta de trabalho foi enviada em uma data específica. A **Visualização do nome do arquivo** mostra como o nome do arquivo da pasta de trabalho será exibido no email quando a pasta de trabalho for distribuída. O formato do carimbo de data e hora é AAAA-MM-DD.

1. (Opcional) Selecione **Compactação .zip** para compactar o arquivo e configurar a proteção por senha no arquivo.

   Ao fazer essa seleção, você deverá digitar uma senha para abrir o arquivo. Isso é útil se você tiver dúvidas sobre a segurança de dados e quiser proteger a pasta de trabalho por senha. A proteção do arquivo com uma senha exige que você selecione **Compactação .zip**. A senha deve ter pelo menos 8 caracteres e conter um número e um caractere especial.

   ![Descrição alt](./assets/zip-compression.png){width="55%"}

1. Insira os **Recipients**. Você pode inserir o nome de uma pessoa reconhecida em sua organização ou pode inserir um endereço de email de uma pessoa dentro ou fora da organização.

1. Insira o **Assunto** do email e uma descrição para seus recipients. O assunto assume o padrão do nome do arquivo da pasta de trabalho, mas você pode modificar o assunto, se necessário. Você pode adicionar detalhes na seção de descrição.

   ![Descrição alt](./assets/recipients-subject.png){width="55%"}

1. Configure as opções de programação para definir a data e a hora em que deseja que a pasta de trabalho seja enviada por email para os recipients.

   Escolha a data inicial e final e os intervalos de tempo. Pode ser a data de hoje ou uma data no futuro.

   Escolha a **Frequência** no menu suspenso. Você pode definir a frequência por hora, dia, semana, mês ou ano em um dia específico. Por exemplo, você pode configurar uma programação para enviar a pasta de trabalho na primeira noite de domingo do mês, para que os recipients tenham o email na caixa de entrada logo na segunda-feira de manhã.

   ![Descrição alt](./assets/frequency.png){width="55%"}

1. Após definir a programação, clique em **Enviar de acordo com a programação**.

   ![Descrição alt](./assets/send-on-schedule.png){width="55%"}

   Você verá uma confirmação na parte inferior do hub do Report Builder e a pasta de trabalho programada será listada na guia Pastas de trabalho.

   ![Descrição alt](./assets/confirmation-toast.png){width="55%"}

## Enviar a pasta de trabalho apenas uma vez

Você também pode enviar a pasta de trabalho apenas uma vez.

1. Desmarcar **Mostrar opções de programação**

   ![Descrição alt](./assets/send-now.png){width="40%"}

1. Clique em **Enviar agora**.

## Exibir e editar pastas de trabalho programadas

Você pode exibir e gerenciar todas as pastas de trabalho programadas em um local, na guia Pastas de trabalho.

1. Na seção Programação do hub do Report Builder, clique na guia Pastas de trabalho. Use essa exibição para ver uma lista de todas as pastas de trabalho programadas.

1. Selecione uma pasta de trabalho. São exibidas várias ferramentas que permitem editar a pasta de trabalho, editar a tarefa de agendamento, pausar e reiniciar a tarefa de agendamento, baixar um relatório de tarefa agendada ou excluir a tarefa de agendamento.

   ![Captura de tela mostrando os ícones de programação da pasta de trabalho.](./assets/schedule-icons.png){width="15%"}

* (Opcional) Clique no ícone de lápis para editar a tarefa de programação da pasta de trabalho.

* (Opcional) Clique no ícone de relógio para exibir um histórico de cada tarefa agendada.

* (Opcional) Clique no ícone de pausa para pausar e reiniciar a tarefa de programação de distribuição. Isso é útil se você precisar modificar a pasta de trabalho antes que ela seja enviada. Clique no ícone de pausa novamente quando quiser reiniciar a distribuição.

* (Opcional) Clique no ícone de download para baixar uma cópia da tarefa de agendamento da pasta de trabalho.

* (Opcional) Clique na lixeira para excluir a tarefa programada.

  ![Captura de tela mostrando a lista de tarefas agendadas.](./assets/selected-workbook.png){width="20%"}

## Revisar o status das tarefas programadas

A exibição do histórico permite revisar o status de cada tarefa programada. Há uma linha separada que documenta a alteração de status para cada tarefa programada. No exemplo mostrado abaixo, a *Nova programação por hora* foi iniciada em 5 de janeiro, às 15h04. Às 15h05, ela foi atualizada com êxito e enviada aos recipients. A próxima pasta de trabalho, *Pasta de trabalho incorreta*, encontrou um erro durante o processo de atualização. Se uma pasta de trabalho tiver falha de envio, a guia Histórico ajudará a solucionar o problema, mostrando onde ocorreu o erro no processo. Nesse caso, é provavelmente devido a algum erro de bloco de dados, talvez um componente ausente, que impedia a atualização bem-sucedida da pasta de trabalho.

Uma marca de seleção verde indica que a pasta de trabalho foi enviada com êxito. Um ponto de exclamação em um triângulo vermelho indica que ocorreu um erro.

Você pode escolher quais colunas exibir na guia de histórico clicando no ícone de configuração de colunas à direita da barra de pesquisa.

![Descrição alt](./assets/history.png){width="55%"}

Você pode filtrar o histórico para ver apenas o de uma única pasta de trabalho programada, acessando a guia Pastas de trabalho, selecionando a pasta de trabalho e clicando no ícone do histórico.

Também é possível exibir o histórico de uma pasta de trabalho específica na guia Pastas de trabalho. Na guia Pastas de trabalho, selecione a pasta de trabalho e clique no ícone Histórico.

![Descrição alt](./assets/history2.png){width="55%"}

O filtro da pasta de trabalho será exibido na parte superior do histórico. Para visualizar o histórico de todas as tarefas programadas novamente, clique no x ao lado do filtro.

![Descrição alt](./assets/history3.png){width="55%"}
