# Catástrofe da Contagem Regressiva

Este projeto utiliza um Arduino para criar uma contagem regressiva de 9 a 0 em um display de LED, com um efeito sonoro dramático que aumenta em frequência até o final da contagem.

![Project Image](https://github.com/Wil-tord/Cat-strofe-da-Contagem-Regressiva/blob/main/arduino%20project.jpeg)

[![Watch the video](https://img.youtube.com/vi/bada4GP8S5w/maxresdefault.jpg)](https://youtu.be/bada4GP8S5w)


## Características
- Contagem regressiva de 9 a 0 em loop
- Efeito sonoro dramático

| Component    | Quantity |
|--------------|----------|
| Arduino Uno  | 1        |
| LED Display  | 1        |
| Buzzer       | 1        |


## Componentes Necessários
- Arduino Uno
- Display de 7 segmentos
- Buzzer ativo
- Resistores (entre 300 - 400 ohms) * 8
- Protoboard, Mini-protoboard e fios de conexão

## Como Usar
1. Monte o circuito conforme o diagrama fornecido.
2. Carregue o código no Arduino.
3. Ligue o sistema e veja a contagem regressiva com o efeito sonoro dramático.

## Código
```cpp
int DP = 3;
int C = 4;
int D = 5;
int E = 6;
int B = 7;
int A = 8;
int F = 9;
int G = 10;
int buzzer = 11; // Define the buzzer pin
int delayTime = 1000;

void setup() {
  // Set up the LED segments as outputs
  pinMode(DP, OUTPUT);
  pinMode(C, OUTPUT);
  pinMode(D, OUTPUT);
  pinMode(E, OUTPUT);
  pinMode(B, OUTPUT);
  pinMode(A, OUTPUT);
  pinMode(F, OUTPUT);
  pinMode(G, OUTPUT);

  pinMode(buzzer, OUTPUT); // Set up the buzzer as output
}

void loop() {
  // Number 9
  displayNumber(9);
  delay(delayTime);

  // Number 8
  displayNumber(8);
  delay(delayTime);

  // Number 7
  displayNumber(7);
  delay(delayTime);

  // Number 6
  displayNumber(6);
  delay(delayTime);

  // Number 5
  displayNumber(5);
  delay(delayTime);

  // Number 4
  displayNumber(4);
  delay(delayTime);

  // Number 3
  displayNumber(3);
  delay(delayTime);

  // Number 2
  displayNumber(2);
  delay(delayTime);

  // Number 1
  displayNumber(1);
  delay(delayTime);

  // Number 0
  displayNumber(0);

  // Play a sound with increasing frequency
  playIncreasingFrequencySound();
  
  delay(delayTime);
}

void displayNumber(int number) {
  // Turn off all segments
  digitalWrite(DP, LOW);
  digitalWrite(C, LOW);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(B, LOW);
  digitalWrite(A, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, LOW);

  // Turn on segments for the given number
  switch (number) {
    case 0:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, HIGH);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, HIGH);
      digitalWrite(G, LOW);
      break;
    case 1:
      digitalWrite(C, HIGH);
      digitalWrite(B, HIGH);
      break;
    case 2:
      digitalWrite(C, LOW);
      digitalWrite(D, HIGH);
      digitalWrite(E, HIGH);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, LOW);
      digitalWrite(G, HIGH);
      break;
    case 3:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, LOW);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, LOW);
      digitalWrite(G, HIGH);
      break;
    case 4:
      digitalWrite(C, HIGH);
      digitalWrite(D, LOW);
      digitalWrite(E, LOW);
      digitalWrite(B, HIGH);
      digitalWrite(A, LOW);
      digitalWrite(F, HIGH);
      digitalWrite(G, HIGH);
      break;
    case 5:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, LOW);
      digitalWrite(B, LOW);
      digitalWrite(A, HIGH);
      digitalWrite(F, HIGH);
      digitalWrite(G, HIGH);
      break;
    case 6:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, HIGH);
      digitalWrite(B, LOW);
      digitalWrite(A, HIGH);
      digitalWrite(F, HIGH);
      digitalWrite(G, HIGH);
      break;
    case 7:
      digitalWrite(C, HIGH);
      digitalWrite(D, LOW);
      digitalWrite(E, LOW);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, LOW);
      digitalWrite(G, LOW);
      break;
    case 8:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, HIGH);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, HIGH);
      digitalWrite(G, HIGH);
      break;
    case 9:
      digitalWrite(C, HIGH);
      digitalWrite(D, HIGH);
      digitalWrite(E, LOW);
      digitalWrite(B, HIGH);
      digitalWrite(A, HIGH);
      digitalWrite(F, HIGH);
      digitalWrite(G, HIGH);
      break;
  }
}

void playIncreasingFrequencySound() {
  // Start with a lower frequency and gradually increase
  int startFrequency = 500; // Starting frequency in Hz
  int endFrequency = 2000; // Ending frequency in Hz
  int step = 10; // Frequency step

  for (int freq = startFrequency; freq <= endFrequency; freq += step) {
    tone(buzzer, freq);
    delay(20); // Short delay to create the effect of increasing frequency
  }

  noTone(buzzer); // Stop the tone
}
```


Make sure the image URL in the acknowledgment part is correct, and the URL includes the `?t=23400` to specify the start time at 6 and a half hours. Copy and paste this updated Markdown into your README file, and it should display correctly.

