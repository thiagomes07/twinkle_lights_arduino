# Controle de 3 LEDs Externos com Delay Aleatório

Este é um exemplo modificado do código Blink da Arduino, onde **três LEDs externos** piscam de forma independente com **delays aleatórios** entre 50ms e 500ms. Cada LED é controlado por uma função separada para facilitar a modularidade do código.

## Esquema de Conexão

Conecte cada LED aos pinos digitais correspondentes, utilizando resistores para limitar a corrente:

- **LED 1**: Pino 13 → Anodo do LED 1 → Resistor (220Ω) → GND  
- **LED 2**: Pino 12 → Anodo do LED 2 → Resistor (220Ω) → GND  
- **LED 3**: Pino 11 → Anodo do LED 3 → Resistor (220Ω) → GND  

## Código

```cpp
/*
  Controle de 3 LEDs Externos com Delay Aleatório

  Este código acende e apaga três LEDs conectados aos pinos digitais 13, 12 e 11
  do Arduino. Cada LED é controlado por uma função separada, e acende e apaga de forma independente, 
  com um tempo aleatório entre 50 e 500 milissegundos.

  Conecte cada LED aos pinos correspondentes (13, 12 e 11) com resistores para limitar a corrente.

  Este código é baseado no exemplo Blink da Arduino e está em domínio público.
*/

const int led1 = 13;  // LED conectado ao pino 13
const int led2 = 12;  // LED conectado ao pino 12
const int led3 = 11;  // LED conectado ao pino 11

// A função setup é executada uma vez ao iniciar a placa
void setup() {
  pinMode(led1, OUTPUT);  // Configura o pino do LED 1 como saída
  pinMode(led2, OUTPUT);  // Configura o pino do LED 2 como saída
  pinMode(led3, OUTPUT);  // Configura o pino do LED 3 como saída
}

// A função loop é executada continuamente
void loop() {
  controlarLED(led1);  // Controla o LED 1
  controlarLED(led2);  // Controla o LED 2
  controlarLED(led3);  // Controla o LED 3
}

// Função para controlar um LED com delays aleatórios
void controlarLED(int pinoLED) {
  digitalWrite(pinoLED, HIGH);  // Liga o LED
  delay(random(50, 501));       // Espera por um tempo aleatório
  digitalWrite(pinoLED, LOW);   // Desliga o LED
  delay(random(50, 501));       // Espera por outro tempo aleatório
}
```