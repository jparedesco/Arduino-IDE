# Sensor HC-SR04 con Arduino

## 📋 Descripción
Este proyecto utiliza un sensor ultrasónico HC-SR04 con Arduino IDE para medir distancias.

## 📸 Diagrama de Conexión
![Diagrama de conexión](Diagrama%20de%20conexi%C3%B3n.png)

## 💻 Código Arduino

```cpp
// Definir pines
const int trigPin = 7;
const int echoPin = 8;

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  // Enviar pulso
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Leer tiempo de respuesta
  long duration = pulseIn(echoPin, HIGH);
  
  // Calcular distancia (velocidad del sonido: 343 m/s)
  float distance = duration * 0.0343 / 2;

  // Mostrar resultado
  Serial.print("Distancia: ");
  Serial.print(distance);
  Serial.println(" cm");

  delay(1000);
}
