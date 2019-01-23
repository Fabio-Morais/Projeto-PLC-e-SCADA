# AUTO
___

#### Neste trabalho pretende-se controlar e supervisionar uma célula da linha de produção flexível que existe no laboratório.
___
* ###### Tarefa 1: desenvolver uma aplicação de controlo da célula utilizando um autómato programável.
* ###### Tarefa 2: desenvolver uma aplicação de supervisão e monitorizarão da célula utilizando uma aplicação SCADA.

---

**A linha de produção tem o seguinte aspeto:**
![2](https://user-images.githubusercontent.com/35969631/51605293-8d283c80-1f06-11e9-8dab-bf1868a8445f.PNG)

Irá ser desenvolvida o controlo e supervisão apenas para a celula 1 recorrendo ao [**winlog**](https://www.sielcosistemi.com/en/download/public/winlog_lite.html) para desenvolvimento da aplicação de supervisão (SCADA), para o desenvolvimento da aplicação de controlo irá ser utilizado automatos  do fabricante Schneider Electric do modelo M340 com as seguintes características:
* Fonte de alimentação.
* Carta CPU (processador).
* Carta de comunicações ethernet incorporada no CPU ou em carta separada.
* Entradas e saídas (E/S), dependendo do modelo do autómato, com a seguinte configuração:
  * 1 carta de 16 saídas digitais, ligadas às luzes indicadoras.
  * 1 carta de 16 entradas digitais, ligadas aos botões de pressão.
 

O trabalho irá ser todo modelado em grafcet e em seguida implementado no programa [**Unity Pro Xl**](https://www.se.com/br/pt/faqs/FA291015/) dando uso a qualquer linguagem suportada pelo IEC 61131-3. 


![4](https://user-images.githubusercontent.com/35969631/51605291-8d283c80-1f06-11e9-875c-db5802683bae.PNG)
![3](https://user-images.githubusercontent.com/35969631/51605292-8d283c80-1f06-11e9-8e4e-e4695b40e7b5.PNG)
![sim](https://user-images.githubusercontent.com/35969631/51605294-8dc0d300-1f06-11e9-8c1c-6938874cbbb6.PNG)
![1](https://user-images.githubusercontent.com/35969631/51605295-8dc0d300-1f06-11e9-8f31-ec7135ecd7fd.PNG)
