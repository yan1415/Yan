# Trabalho de LIA 
projeto escolhido foi Sistema de Alarme com Sensor de Movimento
# Componentes:
1-Arduino Uno

1-sensor de movimento PIR

1-buzina

1-LED

2-resistores.


# Descrição:
O sensor PIR (Passive Infrared) detecta movimento no ambiente.
Quando o sensor detecta movimento, o Arduino aciona a buzina e os LEDs.

# Utilidades:
alarme de segurança de uma casa, pode ser modificado para mandar mensagens de texto para contados pré-selecionados dentre outras utilidades.

# Montagem 
![WhatsApp Image 2025-02-03 at 22 09 26](https://github.com/user-attachments/assets/371536e5-05a4-4f3e-976c-79c05edfc33f)

# Montagem TINKERCAD
![Tremendous Snicket-Wolt](https://github.com/user-attachments/assets/5de36cc9-23c3-4564-b298-8673a94c201d)

# Diagrama de montagem
[Tremendous Snicket-Wolt.pdf](https://github.com/user-attachments/files/18650322/Tremendous.Snicket-Wolt.pdf)

# Fiação
Sensor de movimento PIR no pin 2

Buzina no pin 3

LED no pin 4


# Código:
// Definição dos pinos
const int pinoPIR = 2;       // Pino do sensor de movimento PIR
const int pinoBuzina = 3;    // Pino da buzina
const int pinoLED = 4;       // Pino do LED

void setup() {
  pinMode(pinoPIR, INPUT);       // Configura o pino do PIR como entrada
  pinMode(pinoBuzina, OUTPUT);   // Configura o pino da buzina como saída
  pinMode(pinoLED, OUTPUT);      // Configura o pino do LED como saída
  Serial.begin(9600);            // Inicializa a comunicação serial para depuração
}

void loop() {
  int movimento = digitalRead(pinoPIR); // Lê o estado do sensor PIR

  if (movimento == HIGH) {              // Se o movimento for detectado
    digitalWrite(pinoBuzina, HIGH);     // Liga a buzina
    digitalWrite(pinoLED, HIGH);        // Liga o LED
    Serial.println("Movimento detectado!");
  } else {
    digitalWrite(pinoBuzina, LOW);      // Desliga a buzina
    digitalWrite(pinoLED, LOW);         // Desliga o LED
  }

  delay(100); // Pequeno atraso para estabilidade do sensor
}

