# Projeto-PLC-e-SCADA
___

#### Neste trabalho pretende-se controlar e supervisionar uma célula da linha de produção flexível que existe no laboratório.
___
* ###### Tarefa 1: desenvolver uma aplicação de controlo da célula utilizando um autómato programável.
* ###### Tarefa 2: desenvolver uma aplicação de supervisão e monitorizarão da célula utilizando uma aplicação SCADA.
<br />

<br />

<br />

**A linha de produção tem o seguinte aspeto:**
![2](https://user-images.githubusercontent.com/35969631/51605293-8d283c80-1f06-11e9-8dab-bf1868a8445f.PNG)

Irá ser desenvolvida o controlo e supervisão apenas para a celula 1 recorrendo ao [**winlog**](https://www.sielcosistemi.com/en/download/public/winlog_lite.html) para desenvolvimento da aplicação de supervisão (SCADA), para o desenvolvimento da aplicação de controlo irá ser utilizado automatos  do fabricante Schneider Electric do modelo M340 com as seguintes características:
* Fonte de alimentação.
* Carta CPU (processador).
* Carta de comunicações ethernet incorporada no CPU ou em carta separada.
* Entradas e saídas (E/S), dependendo do modelo do autómato, com a seguinte configuração:
  * 1 carta de 16 saídas digitais, ligadas às luzes indicadoras.
  * 1 carta de 16 entradas digitais, ligadas aos botões de pressão.
 
 Existirá uma botoneira para controlar o processo
 
 ![4](https://user-images.githubusercontent.com/35969631/51605291-8d283c80-1f06-11e9-875c-db5802683bae.PNG)


O trabalho irá ser todo modelado em grafcet e em seguida implementado no programa [**Unity Pro Xl**](https://www.se.com/br/pt/faqs/FA291015/) dando uso a qualquer linguagem suportada pelo IEC 61131-3. 

<br />

---

**Video curto de algumas funcionalidades do processo de controlo**
[![PLC](http://img.youtube.com/vi/UpqLWS-f7dw/0.jpg)](https://www.youtube.com/watch?v=UpqLWS-f7dw)

**Video curto de algumas funcionalidades do processo de supervisão SCADA**
[![SCADA](http://img.youtube.com/vi/c-R79pKhEeU/0.jpg)](https://youtu.be/c-R79pKhEeU)

----

<br />
<br />

##### Funcionalidades
* Inicialização do sistema, verificando se há peças
* Movimento dos tapetes, sem colisão de peças
* Leitura e identificaçao de peça
  * Cada peça corresponde a um respetivo numero de processamentos e a uma determinada saida pelo tapete
* Pode ocorrer avarias na maquina
  * É tomado a devida precaução com isso, podendo a peça ficar com defeito ou é processada numa outra maquina.
  
 ##### Funcionalidades da botoneira
 * Botão verde-> inicializa a celula
 * Botão amarelo-> suspende processo
 * Botão vermelho-> Para processo, nao deixando colocar mais peças no tapete, acabando o que está a fazer
 * Botão azul-> Coloca avaria na máquina
 * Botão de emergência-> Para o processo todo imediatamente 

 ##### Funcionalidades do ambiente SCADA
* Estado da célula: PARADO, OPERACIONAL, SUSPENSO, A_PARAR, EMERGÊNCIA
* Estado dos tapetes: em movimento/rotação/parados.
* Estado das máquinas: paradas/em processamento.
* Peças:
  * Tipo de peça na máquina. Quando a peça estiver localizada no tapete adjacente à
máquina, deve ser indicado quantas operações irão ser realizadas nessa máquina.
  * Localização (tapete / máquina)
  * Movimento das peças entre tapetes.
* Número de peças processadas ou com defeito (PD).
* Data e hora atual.
* Não devem estar presentes menus (na janela do sinótico) não relacionados com a monitorização / supervisão do trabalho.
* Permitir ao operador comandar o processo utilizando botões equivalentes aos da botoneira: Verde e
Vermelho.
* Permitir ao operador definir os tempos de processamento das peças nas máquinas (TA e TB). Esta
funcionalidade tem que ser implementada através do conceito de Receita. Devem ser criadas 3
receitas:
  * Receita 1: TA=4s, TB=1s
  * Receita 2: TA=1s, TB=1s
  * Receita 3: TA=1s, TB=4s
  * As receitas devem ser geridas através da execução de código e não do Recipe Manager que está
disponível no Runtime.
  * Caso o operador não selecione uma receita, considera-se que está ativa a Receita 1.
* Assinalar situações de alarme.
* Manter um registo histórico de todas as ocorrências de alarmes. Deve ser criado:
* Uma página/log de alarmes (todos os estados).
* Indicar nas páginas de sinópticos quais os alarmes que estão ativos. Todas as situações de alarme
devem ser confirmadas pelo operador.
* Manter um registo histórico:
* Códigos de barras das peças que entraram na célula.
  * Devem ser armazenados os seguintes elementos: data / hora /código.
* Eventos relacionados com as máquinas.
  * Os eventos são o estado da máquina: parada/a processar/avariada
  * Devem ser armazenados os seguintes elementos: data / hora /máquina /evento.
* Permitir ao operador gerar um relatório de produção com os seguintes elementos:
  * Para cada máquina: quantas peças foram processadas.
  * Quantas avarias ocorreram na máquina Ma.
* Os elementos relacionados com históricos deverão ser armazenados em ficheiros de texto. 

 ##### Todas as funcionalidades estão explicadas ao pormenor no ficheiro [Guiao_Trabalho_Pratico.pdf](https://github.com/fabiouds/AUTO/blob/master/Guiao_Trabalho_Pratico.pdf) 

A troca de dados realizase através do protocolo de comunicações MODBUS/TCP.
![3](https://user-images.githubusercontent.com/35969631/51605292-8d283c80-1f06-11e9-8e4e-e4695b40e7b5.PNG)

Iremos ter à disposição um simulador de fábrica, que pdoemos testar antes de colocar no kit
![sim](https://user-images.githubusercontent.com/35969631/51605294-8dc0d300-1f06-11e9-8c1c-6938874cbbb6.PNG)
