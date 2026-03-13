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

# Sensor HC-SR04 con Arduino

## 📋 Descripción
Este proyecto utiliza un sensor ultrasónico HC-SR04 con Arduino IDE para medir distancias.

## 📸 Diagrama de Conexión
![Diagrama de conexión](Diagrama%20de%20conexi%C3%B3n.png)

## 📁 Archivos del Proyecto
- **CÓDIGO SENSOR HC-SR04 - ARDUINO IDE**: Código Arduino para el sensor ultrasónico
- **Diagrama de conexión.png**: Esquema de conexión del sensor

## 🔧 Componentes Necesarios
- Arduino (Uno, Nano, Mega, etc.)
- Sensor Ultrasónico HC-SR04
- Cables de conexión
- Resistencias (si es necesario)

## 📌 Conexiones
El sensor HC-SR04 se conecta al Arduino mediante:
- **VCC**: +5V
- **GND**: GND
- **TRIG**: Pin digital (por ejemplo, pin 7)
- **ECHO**: Pin digital con entrada analógica (por ejemplo, pin 8)

## 💻 Cómo Usar
1. Carga el código Arduino en tu placa
2. Abre el Monitor Serial a 9600 baudios
3. El sensor mostrará las distancias medidas

## 📚 Referencias
- [Documentación HC-SR04](https://www.arduino.cc/)
- [Arduino IDE](https://www.arduino.cc/en/software)
