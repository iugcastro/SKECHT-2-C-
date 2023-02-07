# IMPRESSORA 3D - ARDUINO
#include <Stepper.h>

const int stepsPerRevolution = 200;  // definir o número de passos por revolução do motor de passo

// Criar objetos stepper para controlar o movimento do extrusor e da cama quente
Stepper extruderStepper(stepsPerRevolution, 8, 10, 9, 11);
Stepper bedStepper(stepsPerRevolution, 4, 6, 5, 7);

void setup() {
  // Inicializar os pinos dos motores
  extruderStepper.begin(60);
  bedStepper.begin(60);
}

void loop() {
  // Mover o extrusor para cima
  extruderStepper.step(stepsPerRevolution);
  delay(500);

  // Mover a cama quente para baixo
  bedStepper.step(-stepsPerRevolution);
  delay(500);
}
