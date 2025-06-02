# Controlling Droid
This project allows you to control a real-world robot using Arduino and basic DC motors. The bot can move forward, backward, and turn left/right based on commands in the code.

## Features

- Control two DC motors using L298N motor driver
- Pre-programmed movement logic
- Clean, commented Arduino code
- Ready for physical prototyping

## Hardware Requirements

- Arduino Uno (or Nano/Mega)
- L298N Motor Driver Module
- 2x DC Motors (6V–12V)
- Power Supply (battery or wall)
- Jumper wires
- Breadboard (optional)


## // Real-life Bot Control Using L298N Motor Driver and Arduino
// Author: peppybug
// License: MIT

// === Motor A (Left Motor) ===
const int IN1 = 9;
const int IN2 = 10;

// === Motor B (Right Motor) ===
const int IN3 = 11;
const int IN4 = 12;

void setup() {
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
}

void loop() {
  moveForward();
  delay(2000);

  moveBackward();
  delay(2000);

  turnLeft();
  delay(1000);

  turnRight();
  delay(1000);

  stopBot();
  delay(2000);
}

// === Movement Functions ===
void moveForward() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
}

void moveBackward() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
}

void turnLeft() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, HIGH);
  digitalWrite(IN3, HIGH);
  digitalWrite(IN4, LOW);
}

void turnRight() {
  digitalWrite(IN1, HIGH);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, HIGH);
}

void stopBot() {
  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);
  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);
}

