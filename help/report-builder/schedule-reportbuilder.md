---
title: Como programar pastas de trabalho usando o Report Builder no Customer Journey Analytics
description: Descreve como usar o recurso de agendamento no Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 4c48aa3413ff3c2d3b29e7fc1ca4c73a80c0972d
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---


# Agendar pastas de trabalho

Depois de salvar sua pasta de trabalho e concluir sua análise, é possível compartilhar facilmente sua pasta de trabalho com outras pessoas em sua equipe usando o recurso de agendamento. O recurso Agendar permite criar um agendamento que atualiza automaticamente os dados na pasta de trabalho e envia por email o arquivo .xlsx da pasta de trabalho do Excel como um anexo para o público-alvo especificado em uma data e hora específicas. Configurar um agendamento fornece atualizações regulares aos recipients automaticamente. Você também pode usar o recurso de agendamento para enviar a pasta de trabalho uma vez sem agendar atualizações automáticas.

Você pode criar várias programações para uma única pasta de trabalho. Por exemplo, você pode enviar uma pasta de trabalho para sua equipe diariamente e enviar a pasta de trabalho para seu gerente uma vez por semana criando duas programações diferentes.

O recurso Agendar também permite que você configure a proteção por senha para uma pasta de trabalho e edite pastas de trabalho previamente agendadas.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Agendar uma pasta de trabalho

Use o botão Schedule task no hub Report Builder para criar rapidamente uma programação para que você possa distribuir automaticamente um arquivo Excel de pasta de trabalho (.xlsx) para um indivíduo ou grupo.

1. Clique no botão Schedule no hub Report Builder.

   ![](./assets/schedule-button.png){width="55%"}

1. Clique em Agendar pasta de trabalho ou no botão de mais no canto superior esquerdo para criar uma nova pasta de trabalho agendada.

   ![descrição alt](./assets/schedule-workbook.png){width="55%"}

   O painel de agendamento exibe algumas informações predefinidas sobre a pasta de trabalho, como o nome da pasta de trabalho e a última data em que a pasta de trabalho foi modificada.

   ![descrição alt](./assets/schedule-pane.png){width="55%"}

1. (Opcional) Insira um nome de arquivo.

   O nome do arquivo da pasta de trabalho é padronizado com o nome da pasta de trabalho, mas você pode alterá-lo se desejar. Se estiver enviando a mesma pasta de trabalho para vários públicos-alvo e quiser nomeá-la como algo um pouco mais amigável para um determinado público-alvo, é possível alterar o nome.

1. (Opcional) Selecione **Anexar carimbo de data/hora ao nome do arquivo**.

   Você pode anexar um carimbo de data e hora ao nome do arquivo para identificar a data em que a pasta de trabalho foi atualizada. Isso é útil para ver rapidamente qual versão de uma pasta de trabalho foi enviada em uma data específica. O **Visualização do nome do arquivo** mostra como o nome do arquivo da pasta de trabalho será exibido no email quando a pasta de trabalho for distribuída. O formato do carimbo de data e hora é AAAA-MM-DD.

1. (Opcional) Selecione **compactação .zip** para compactar o arquivo e configurar a proteção por senha no arquivo.

   Ao fazer essa seleção, você será solicitado a digitar uma senha para abrir o arquivo. Isso é útil se você tiver dúvidas sobre a segurança de dados e deseja proteger a pasta de trabalho por senha. A proteção do arquivo com uma senha requer que você selecione **compactação .zip**. A senha deve ter pelo menos 8 caracteres e conter um número e um caractere especial.

   ![descrição alt](./assets/zip-compression.png){width="55%"}

1. Enter **Recipients**. Você pode inserir o nome de uma pessoa reconhecida em sua organização ou pode inserir um endereço de email de uma pessoa dentro ou fora da organização.

1. Insira o **Assunto** do email e uma descrição para seus recipients. O assunto assume o padrão do nome do arquivo da pasta de trabalho, mas você pode modificar o assunto, se necessário. Você pode adicionar detalhes na seção de descrição.

   ![descrição alt](./assets/recipients-subject.png){width="55%"}

1. Configure as opções de agendamento para definir a data e a hora em que deseja que a pasta de trabalho seja enviada por email para os recipients.

   Escolha a data inicial e final e os intervalos de tempo. Esta pode ser a data de hoje ou uma data no futuro.

   Escolha a **Frequência** no menu suspenso. Você pode definir a frequência para ser por hora, dia, semana, mês ou ano em um dia específico. Por exemplo, você pode configurar um agendamento para enviar a pasta de trabalho na primeira noite de domingo do mês, para que os recipients tenham o email na caixa de entrada primeiro na segunda-feira de manhã.

   ![descrição alt](./assets/frequency.png){width="55%"}

1. Após definir o agendamento, clique em **Enviar de acordo com a programação**.

   ![descrição alt](./assets/send-on-schedule.png){width="55%"}

   Você verá um brinde de confirmação na parte inferior do hub do Report Builder e a pasta de trabalho agendada será listada na guia Pastas de trabalho .

   ![descrição alt](./assets/confirmation-toast.png){width="55%"}

## Enviar a pasta de trabalho apenas uma vez

Você também pode enviar a pasta de trabalho apenas uma vez.

1. Desmarcar **Mostrar opções de agendamento**

   ![descrição alt](./assets/send-now.png){width="40%"}

1. Clique em **Enviar agora**.

## Exibir e editar pastas de trabalho agendadas

Você pode exibir e gerenciar todas as pastas de trabalho programadas em um local, na guia Pastas de trabalho .

1. Na seção Programação do hub Report Builder, clique na guia Pastas de trabalho . Use essa exibição para ver uma lista de todas as pastas de trabalho programadas.

1. Selecione uma pasta de trabalho. Várias ferramentas são exibidas e permitem editar a pasta de trabalho, alterar a programação, pausar e reiniciar a programação ou excluir a programação.

   ![descrição alt](./assets/edit-icons.png){width="55%"}

* (Opcional) Clique no ícone de lápis para editar a programação da pasta de trabalho.

* (Opcional) Clique no ícone de relógio para exibir um histórico de cada tarefa agendada.

* (Opcional) Clique no ícone de pausa para pausar e reiniciar o agendamento de distribuição. Isso é útil se você precisar modificar a pasta de trabalho antes que ela seja enviada. Clique no ícone de pausa novamente quando quiser reiniciar a distribuição.

* (Opcional) Clique na lixeira para excluir o cronograma.

## Revisar o status das tarefas agendadas

A exibição do histórico permite revisar o status de cada tarefa agendada. Há uma linha separada que documenta a alteração de status para cada tarefa agendada. No exemplo mostrado abaixo, a variável *Nova programação por hora* foi iniciado em 5 de janeiro, às 15:04. Às 15:05, ele foi atualizado com êxito e enviado aos recipients. A próxima pasta de trabalho, *Pasta de trabalho incorreta*, encontrou um erro durante o processo de atualização. Se uma pasta de trabalho não tiver enviado, a guia Histórico ajudará a solucionar o problema, mostrando onde ocorreu o erro no processo. Nesse caso, é provavelmente devido a algum erro de bloco de dados, talvez um componente ausente, que impedia a atualização bem-sucedida da pasta de trabalho.

Uma marca de seleção verde indica que a pasta de trabalho foi enviada com êxito. Um ponto de exclamação em um triângulo vermelho indica que ocorreu um erro.

Você pode escolher quais colunas exibir na guia histórico clicando no ícone de configuração de colunas à direita da barra de pesquisa.

![descrição alt](./assets/history.png){width="55%"}

Você pode filtrar o histórico para ver apenas o de uma única pasta de trabalho agendada, acessando a guia Pastas de trabalho, selecionando a pasta de trabalho e clicando no ícone do histórico.

Também é possível exibir o histórico de uma pasta de trabalho específica na guia Pastas de trabalho . Na guia Pastas de trabalho , selecione a pasta de trabalho e clique no ícone Histórico .

![descrição alt](./assets/history2.png){width="55%"}

O filtro da pasta de trabalho será exibido na parte superior do histórico. Para visualizar o histórico de todas as tarefas agendadas novamente, clique no x ao lado do filtro.

![descrição alt](./assets/history3.png){width="55%"}



