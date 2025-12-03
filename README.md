# 🚗 Sistema de Estacionamento Automático com Arduino

## 👩‍💻 Integrantes do grupo

* Gabriela silva
* Kauany Santos


---

## 📘 Descrição do projeto

Este projeto simula um *sistema de controle de vagas em estacionamento* utilizando *Arduino UNO*, sensores ultrassônicos, servos, LEDs, buzzer e um display LCD.
O sistema detecta a entrada e saída de veículos automaticamente, atualizando o número de vagas disponíveis no display.

---

## 🧩 Componentes utilizados

* 1x *Arduino UNO R3*
* 2x *Sensores Ultrassônicos HC-SR04*
* 2x *Servos Motores SG90*
* 1x *Display LCD 16x2 (com módulo I2C)*
* 2x *LEDs* (um verde e um vermelho)
* 2x *Resistores de 220Ω*
* 1x *Buzzer*
* 1x *Protoboard*
* Jumpers (fios macho-macho)

---

## ⚙️ Funcionamento do sistema

* Os sensores ultrassônicos detectam a *presença de carros* nas entradas e saídas.
* Quando um carro entra, o *servo abre o portão, o **buzzer* emite um som e o número de vagas é *reduzido*.
* Quando o carro sai, o servo também se movimenta e o número de vagas é *aumentado*.
* O *display LCD* mostra em tempo real a quantidade de vagas disponíveis.
* Os *LEDs* indicam o status:

  * *Verde:* vaga disponível.
  * *Vermelho:* estacionamento cheio.

---

## 🔌 Conexões (rotas dos fios)

### 🟦 Arduino UNO

| Componente         | Pino Arduino            | Pino Componente                 | Descrição                     |
| ------------------ | ----------------------- | ------------------------------- | ----------------------------- |
| LCD (I2C)          | SDA (A4) / SCL (A5)     | SDA / SCL                       | Comunicação I2C               |
| Sensor 1 (entrada) | Trig → D8 / Echo → D9   | —                               | Detecta entrada de veículo    |
| Sensor 2 (saída)   | Trig → D10 / Echo → D11 | —                               | Detecta saída de veículo      |
| Servo 1 (entrada)  | D6                      | Sinal servo 1                   | Controla a cancela de entrada |
| Servo 2 (saída)    | D5                      | Sinal servo 2                   | Controla a cancela de saída   |
| LED Verde          | D3                      | —                               | Indica vagas disponíveis      |
| LED Vermelho       | D4                      | —                               | Indica estacionamento cheio   |
| Buzzer             | D2                      | —                               | Emite alerta sonoro           |
| GND                | —                       | Todos os GND dos componentes    | Terra comum                   |
| 5V                 | —                       | Alimenta sensores, servos e LCD | Fonte de energia              |

### ⚡ Alimentação e Protoboard

* O *pino 5V do Arduino* alimenta o *positivo da protoboard*.
* O *GND do Arduino* conecta ao *negativo da protoboard*.
* Todos os componentes compartilham o mesmo *GND*.

---

## 🧠 Lógica do código (arquivo circuits.c++)
1. Inicializa os pinos e define as variáveis de controle de vagas.
2. Lê as distâncias dos sensores ultrassônicos.
3. Se o sensor de *entrada* detectar um carro, aciona o *servo da cancela* e decrementa o contador.
4. Se o sensor de *saída* detectar um carro, abre o *servo de saída* e incrementa o contador.
5. O número de vagas é exibido no *display LCD*.
6. LEDs e buzzer são ativados conforme a quantidade de vagas disponíveis.

---

## 🧾 Exemplo de funcionamento no LCD


Vagas = 10
Bem-vindo!


Quando o estacionamento fica cheio:


Vagas = 0
Estacionamento cheio!


---

## 💡 Dicas para testar no Tinkercad

1. Clique em *Iniciar Simulação*.
2. Aproxime um objeto do *sensor de entrada* (simulando um carro).
3. Observe o *servo* abrir e o número de vagas no *LCD* diminuir.
4. Aproxime o objeto do *sensor de saída* e veja o contador aumentar.
5. O *LED vermelho* acende quando não há mais vagas disponíveis.

---

## 🛠️ Possíveis melhorias

* Adicionar *sensor de presença por vaga individual*.
* Inserir *módulo Wi-Fi (ESP8266)* para enviar os dados a um site.
* Criar *interface web* mostrando o número de vagas em tempo real.

---

## 📸 Imagem do circuito

![Circuito montado](Captura%20de%20tela%20de%202025-10-15%2015-27-23.png)

---

## 🧑‍🏫 Conclusão

Este projeto foi desenvolvido para demonstrar, de forma prática, como sensores e atuadores podem automatizar processos do dia a dia.
O sistema de estacionamento automático integra conceitos de *eletrônica, lógica de programação e IoT básica, sendo uma excelente aplicação educacional do **Arduino UNO*.

---

*Desenvolvido por:*
* Gabriela silva
* Kauany Santos
– 2025
