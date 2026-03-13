# Sensor HC-SR04 con Arduino

## 📋 Descripción
Este proyecto utiliza un sensor ultrasónico HC-SR04 con Arduino IDE para medir distancias.

## 📸 Diagrama de Conexión
![Diagrama de conexión](Diagrama%20de%20conexi%C3%B3n.png)

## 💻 Código Arduino

```cpp
#define TRIG 9
#define ECHO 10
#define LED 13

long duracion;
int distancia;

void setup() {
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
  pinMode(LED, OUTPUT);
  Serial.begin(9600);
}

void loop() {

  digitalWrite(TRIG, LOW);
  delayMicroseconds(2);

  digitalWrite(TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG, LOW);

  duracion = pulseIn(ECHO, HIGH);

  distancia = duracion * 0.034 / 2;

  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");

  if (distancia < 20) {
    digitalWrite(LED, HIGH);
  } else {
    digitalWrite(LED, LOW);
  }

  delay(200);
}
```

## 📁 Archivos del Proyecto
- **CÓDIGO SENSOR HC-SR04 - ARDUINO IDE**: Código Arduino para el sensor ultrasónico
- **Diagrama de conexión.png**: Esquema de conexión del sensor

## 🔧 Componentes Necesarios
- Arduino (Uno, Nano, Mega, etc.)
- Sensor Ultrasónico HC-SR04
- Cables de conexión (Jumper wires)
- Resistencias (si es necesario)
- Protoboard (opcional)
- Fuente de alimentación 5V

## 📌 Conexiones
El sensor HC-SR04 se conecta al Arduino mediante:
- **VCC**: +5V
- **GND**: GND
- **TRIG**: Pin digital (por ejemplo, pin 7)
- **ECHO**: Pin digital con entrada analógica (por ejemplo, pin 8)

## 💡 Cómo Usar
1. **Conecta los componentes** según el diagrama de conexión
2. **Carga el código Arduino** en tu placa usando Arduino IDE
3. **Abre el Monitor Serial** (Herramientas → Monitor Serial) a 9600 baudios
4. **El sensor mostrará las distancias medidas** en centímetros en tiempo real
5. **Acerca y aleja objetos** del sensor para ver cómo cambian las lecturas
6. El rango de detección es aproximadamente de 2 cm a 400 cm

## 🐛 Solución de Problemas
- Si no ves lecturas, verifica las conexiones
- Asegúrate de que los pines coincidan con el código (pin 9 y 10)
- Asegurate que la velocidad serial sea de 9600

