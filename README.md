# Projeto IoT com Arduino (Documentação parcialmente completa)

---

Participação:
- Ruan
- Gabriel
- João

---

## 1. Objetivo (Parcial)

Dar início ao desenvolvimento de um projeto usando **Arduino** e **Internet das Coisas (IoT)**.

Nesta fase serão feitas as seguintes atividades:

- Identificar e preparar os **componentes do projeto**
- Realizar a **ligação física da placa Arduino e dos módulos**
- Fazer a **configuração da rede** (LAN, DHCP e reserva de IP)
- Realizar **testes de comunicação entre o computador e o Arduino**
- Criar os **primeiros códigos utilizando comunicação Serial e Ethernet**

---

## 2. Equipamento

- Ethernet Shield W5100 – módulo para conectar o Arduino à rede via cabo
- Placas e Módulos
Arduino UNO R3 – placa principal do projeto (microcontrolador ATmega328P)

 ![](IMG_20260311_144403666.jpg)

 ## Cabos e Conexões

- **Cabo USB Tipo B** – utilizado para programar e conectar o Arduino ao computador  
- **Cabo de rede (Ethernet)** – usado para conectar o Arduino ou computador à rede  
- **Roteador Wi-Fi** – equipamento com portas **LAN e WAN** para fornecer acesso à rede e internet

---

## 3. Programação Inicial (codigos iniciais)

- loop() – executa repetidamente
- setup() – executa 1 vez ao iniciar

```

// Gerar um endereço físico (MAC ADDRES) para esta placa
// htpp://ssl.crox.net/arduinomac
byte mac[6] = { 0x90, 0xA2, 0xDA, 0xA0, 0x17, 0x8A };

// Instalar (criar) um servidor
EthernetServer server(80);  //80 é a porta http

void setup() {
  Serial.begin(9600);
  // As linhas abaixo iniciam o servidor e atribui automaticamente um IP para o Arduino
  Ethernet.begin(mac);  //atriui o endereço MAC ao shield Ethernet
  server.begin();       //inicia o servidor

  // As linhas abaixo exibe o IP da placa Arduino
  Serial.println("Arduino Ethernet Shield:");
  Serial.print("IP: ");
  Serial.println(Ethernet.localIP());  //identifica o IP
  Serial.print("Máscara: ");
  Serial.print(Ethernet.subnetMask());  //identifica a máscara de rede
  Serial.print("Gateway: ");
  Serial.print(Ethernet.gatewayIP());  //identifica o gateway
  Serial.print("DNS: ");
  Serial.print(Ethernet.dnsServerIP());  //identifica o DNS
}

void loop() {
}

```

---

## 4. Primeiro teste

Teste no Computador Arduino IDE

- IP Arduino
- Máscara
- Gateway

 ![](IMG_20260313_143654986.jpg)


 teste na Visão do Arduino

 ![](IMG_20260311_144539360.jpg)

 ---
 
