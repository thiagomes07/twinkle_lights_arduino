# Blink com Delay Aleatório

Este é um exemplo modificado do código Blink da Arduino, onde o LED pisca com um intervalo de tempo aleatório entre 50ms e 500ms.

## Código

```cpp
/*
  Blink

  Liga um LED por um segundo e, em seguida, o desliga por um segundo, repetidamente.

  A maioria dos Arduinos possui um LED embutido que você pode controlar. No UNO, MEGA e ZERO,
  ele está conectado ao pino digital 13; no MKR1000, ao pino 6. O LED_BUILTIN é configurado
  para o pino correto do LED, independentemente da placa utilizada.
  Se você quiser saber a que pino o LED embutido está conectado no seu modelo de Arduino,
  verifique as Especificações Técnicas da sua placa em:
  https://www.arduino.cc/en/Main/Products

  modificado em 8 de maio de 2014
  por Scott Fitzgerald
  modificado em 2 de setembro de 2016
  por Arturo Guadalupi
  modificado em 8 de setembro de 2016
  por Colby Newman

  Este código de exemplo é de domínio público.

  https://www.arduino.cc/en/Tutorial/BuiltInExamples/Blink
*/

// A função setup é executada uma vez quando você aperta o botão de reset ou energiza a placa
void setup() {
  // Inicializa o pino digital LED_BUILTIN como saída.
  pinMode(LED_BUILTIN, OUTPUT);
}

// A função loop é executada repetidamente para sempre
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);  // Liga o LED (HIGH é o nível de voltagem)
  
  // Gera um tempo de delay aleatório entre 50ms e 500ms
  int tempoDelay = random(50, 501);  // random(50, 501) gera um valor entre 50 e 500
  
  delay(tempoDelay);  // Aguarda o tempo gerado
  
  digitalWrite(LED_BUILTIN, LOW);   // Desliga o LED (LOW é o nível de voltagem baixo)
  
  // Gera outro tempo de delay aleatório
  tempoDelay = random(50, 501);  
  
  delay(tempoDelay);  // Aguarda o tempo gerado
}
```