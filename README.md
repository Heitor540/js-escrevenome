# 1° preogramação de Arduino

#include <Servo.h> // Inclui a biblioteca Servo

// Cria um objeto servo
Servo meuServo;

// Define o pino ao qual o potenciômetro está conectado
const int potenciometroPin = A0;

// Variáveis para armazenar a leitura do potenciômetro e o ângulo do servo
int leituraPotenciometro;
int anguloServo;

void setup() {
  // Inicializa o servo no pino 9
  meuServo.attach(9);
}

void loop() {
  // Lê o valor do potenciômetro (0 a 1023)
  leituraPotenciometro = analogRead(potenciometroPin);
  
  // Mapeia o valor lido para um intervalo de ângulo de 0 a 180 graus
  anguloServo = map(leituraPotenciometro, 0, 1023, 0, 180);
  
  // Define a posição do servo
  meuServo.write(anguloServo);
  
  // Aguarda um curto período para permitir que o servo mova para a nova posição
  delay(15);
}
