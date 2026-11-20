
# ARDUINO & ESP32

## Cuaderno de prácticas y documentación técnica

## 1. Presentación

En este cuaderno voy a guardar las actividades que realizamos en clase de Arduino.

Aquí explicaré lo que he aprendido, los pasos que he seguido, los códigos utilizados y los resultados de cada práctica.

También añadiré capturas de pantalla, imágenes, vídeos, esquemas de los circuitos y los errores que he encontrado durante las actividades.

## 2. Índice general

### Actividades

- [A0 — Preparación del entorno](#a0)
- [A1 — Blink + Semáforo](#a1)
- [A2 — LED + Button](#a2)
- [A3 — LED RGB](#a3)
- [A4 — LED Bar](#a4)
- [A5 — Serial IO](#a5)
- [A6 — WiFi](#a6)

---

## A0
### Preparación del entorno


# 2. Investigación sobre Arduino

## 2.1. ¿Qué es Arduino?

Es una plataforma de creación de código abierto que permite crear diferentes tipos de microordenadores de una sola placa base. Está basada en hardware y software libre y fácil de usar para los creadores y desarrolladores.

Hay muchos dispositivos que se pueden conectar a Arduino, incluidos sensores, luces, actuadores, pantallas, altavoces y otros componentes.

---

## 2.2. ¿Cuáles son sus características más importantes?

Las características más importantes de Arduino son:

- **Fácil de programar:** Arduino utiliza un entorno de programación llamado Arduino IDE, que funciona en Windows, macOS y Linux.

- **Hardware y software libre:** Sus diseños y herramientas son de código abierto, lo que permite estudiar, modificar y compartir proyectos.

- **Microcontrolador:** Es el componente principal de la placa y se encarga de ejecutar las instrucciones del programa. El tipo de microcontrolador depende del modelo de Arduino.

- **Pines de entrada y salida:** Permiten conectar sensores, botones, luces y motores. Dispone de pines digitales y entradas analógicas.

- **Alimentación:** Algunas placas, como Arduino UNO R3, pueden funcionar mediante USB de 5 V o una fuente externa recomendada de 7 a 12 V.

- **Versatilidad:** Se puede utilizar para crear muchos proyectos diferentes, como robots, alarmas o sistemas de iluminación automática.

---

## 2.3. ¿Cuál es el origen de Arduino?

Arduino nació en el año 2005 en el Instituto de Diseño Interactivo de Ivrea, en Italia.

Este proyecto surgió porque los estudiantes necesitaban una herramienta económica y fácil de utilizar para aprender electrónica y programación en las aulas.

Con el tiempo, Arduino se hizo muy popular y empezó a utilizarse en escuelas, universidades y proyectos de robótica.

---

## 2.4. ¿Qué modelos de Arduino hay?

Los modelos más conocidos de Arduino son Arduino UNO R3, Arduino Mega 2560 y Arduino Leonardo. Cada modelo tiene diferentes características, como el número de pines, la memoria y el microcontrolador que utiliza.

### Tabla comparativa de los modelos de Arduino

| Características | Arduino UNO R3 | Arduino Mega 2560 | Arduino Leonardo |
|---|---|---|---|
| Microcontrolador | ATmega328P | ATmega2560 | ATmega32U4 |
| Voltaje de funcionamiento | 5 V | 5 V | 5 V |
| Voltaje de entrada recomendado | 7–12 V | 7–12 V | 7–12 V |
| Pines digitales | 14 | 54 | 20 |
| Entradas analógicas | 6 | 16 | 12 |
| Memoria Flash | 32 KB | 256 KB | 32 KB |
| Memoria SRAM | 2 KB | 8 KB | 2,5 KB |
| Reloj | 16 MHz | 16 MHz | 16 MHz |

---

## 2.5. ¿Para qué sirve Arduino?

Arduino sirve para crear proyectos electrónicos y controlar diferentes dispositivos mediante programación.

Gracias a los **sensores**, puede recibir información del entorno, como la temperatura, la luz o el movimiento. Después, el **microcontrolador** procesa esa información y, mediante los **actuadores**, puede realizar acciones, como encender una luz o mover un motor.

Arduino se utiliza en diferentes ámbitos:

- **Proyectos personales:** creación de robots, luces decorativas y sistemas de automatización.

- **Educación y prototipos:** permite aprender programación y electrónica y probar nuevas ideas.

- **Industria y negocios:** se utiliza para desarrollar prototipos de sistemas de control, monitorizar procesos y recoger datos mediante sensores.

**Ejemplo:** Arduino puede detectar cuando una habitación está oscura y encender automáticamente una luz.

---

## 2.6. ¿Qué lenguaje utiliza Arduino?

Arduino utiliza un lenguaje de programación basado en **C/C++**, que es relativamente fácil de aprender gracias a sus funciones y bibliotecas.

Este lenguaje permite escribir instrucciones para controlar sensores, luces, motores y otros componentes electrónicos.

---

## 2.7. ¿Qué es Arduino IDE?

Arduino IDE (Entorno de Desarrollo Integrado) es un software gratuito y de código abierto que permite escribir, compilar y cargar programas en las placas Arduino. También ofrece herramientas para detectar errores y depurar programas compatibles.

Está compuesto por diferentes herramientas:

- **Editor de código:** permite escribir y modificar el código fuente.

- **Compilador:** convierte el código escrito en C/C++ en instrucciones que puede ejecutar el microcontrolador.

- **Herramienta de carga:** permite enviar el programa compilado a la placa Arduino mediante USB.

- **Depurador:** ayuda a detectar y corregir errores durante la ejecución, en placas compatibles.

Arduino IDE es compatible con Windows, macOS y Linux.

---

### 3. Instalación de Arduino IDE

#### 3.1. Descarga de Arduino IDE

Para descargar Arduino IDE, he entrado en la página oficial de Arduino:

https://www.arduino.cc/en/software

He seleccionado la versión para Windows y he descargado el programa.

La versión que he utilizado es **Arduino IDE 2.3.11**.

#### 3.2. Instalación en el equipo

Después de descargar Arduino IDE, he seguido estos pasos:

1. Abrir el archivo descargado.
2. Seguir las instrucciones de instalación.
3. Aceptar los permisos necesarios.
4. Completar la instalación.
5. Abrir Arduino IDE para comprobar que funciona.

He instalado el programa en la partición **D:** del ordenador del aula.

Arduino IDE nos permite escribir código, comprobar errores y cargar los programas en la placa ESP32.

**Captura — Arduino IDE instalado**

<p align="center">
  <img src="https://github.com/user-attachments/assets/ff8fbfa5-7478-49f7-97a0-a16dc99ab273" width="500" alt="Arduino IDE" />
</p>

---

### 4. Puesta a punto de Arduino IDE

#### 4.1. Comprobación del controlador CH343

En el enunciado se menciona el controlador CH343, que sirve para comunicar determinadas placas ESP32 con el ordenador mediante USB.

En mi caso, he utilizado la placa **Freenove ESP32-WROVER**.

Para comprobar la conexión USB:

1. He conectado la placa al ordenador mediante USB.
2. He abierto el Administrador de dispositivos de Windows.
3. He comprobado el apartado de puertos COM.
4. He identificado el puerto correspondiente a mi placa.

Mi placa se ha reconocido mediante el puerto **COM3**.

Esto me ha permitido comunicar Arduino IDE con el ESP32 y cargar los programas.

**Captura — Comprobación del puerto USB**

<img width="481" height="406" alt="image" src="https://github.com/user-attachments/assets/e267a7f7-f7f2-484f-bdcc-a7ec841f78ff" />

---

#### 4.2. Configuración del entorno de Arduino

Para poder programar mi placa ESP32, he instalado el paquete correspondiente en Arduino IDE.

He seguido estos pasos:

1. Abrir Arduino IDE.
2. Entrar en `File > Preferences`.
3. Buscar `Additional Boards Manager URLs`.
4. Añadir el siguiente enlace:

`https://espressif.github.io/arduino-esp32/package_esp32_index.json`

5. Guardar los cambios.
6. Abrir `Boards Manager`.
7. Buscar `esp32`.
8. Instalar `esp32 by Espressif Systems`.
9. Esperar a que termine la instalación.

Este paquete permite programar diferentes placas ESP32 desde Arduino IDE.

**Captura — Instalación de ESP32**

<img width="517" height="430" alt="image" src="https://github.com/user-attachments/assets/63660ce0-3470-4eab-aaef-b0527036e0c2" />

---

#### 4.3. Selección de la placa ESP32

Después de instalar el paquete ESP32, he seleccionado la placa que estoy utilizando.

He seguido estos pasos:

1. Abrir Arduino IDE.
2. Entrar en `Tools > Board`.
3. Buscar las placas ESP32.
4. Seleccionar `ESP32 Wrover Module`.

**Mi placa:** Freenove ESP32-WROVER.

**Modelo seleccionado:** ESP32 Wrover Module.

Es importante seleccionar correctamente la placa para poder cargar los programas sin errores.

**Captura — Selección de ESP32 Wrover Module**

*<img width="570" height="450" alt="image" src="https://github.com/user-attachments/assets/ff06c4c8-57a7-4e02-bb81-bcddacad1028" />
*

---

#### 4.4. Comprobación del puerto USB

Después de configurar la placa, he comprobado que Arduino IDE reconoce el puerto USB.

He seguido estos pasos:

1. Conectar el ESP32 al ordenador.
2. Abrir Arduino IDE.
3. Entrar en `Tools > Port`.
4. Seleccionar `COM3`.

En mi caso, he utilizado el puerto **COM3** para comunicar el ordenador con el ESP32.

**Captura — Puerto COM3**

*<img width="287" height="225" alt="image" src="https://github.com/user-attachments/assets/6ffbaefc-023c-44b5-a7e8-3bd06c907289" />
*

---

#### 4.5. Verificación del funcionamiento

Por último, he comprobado que Arduino IDE funciona correctamente y que puedo cargar programas en mi placa ESP32.

He seguido estos pasos:

1. Abrir Arduino IDE.
2. Seleccionar `ESP32 Wrover Module`.
3. Seleccionar el puerto `COM3`.
4. Abrir el programa de prueba.
5. Pulsar `Verify` para comprobar el código.
6. Pulsar `Upload` para cargarlo en el ESP32.
7. Esperar a que termine la carga.

En mi caso, el programa se ha compilado y cargado correctamente.

Arduino IDE ha mostrado los siguientes mensajes:

- `Done compiling`
- `Done uploading`
- `Hard resetting via RTS pin`

Esto significa que el programa se ha compilado y enviado correctamente a la placa ESP32.

**Captura — Programa cargado correctamente**

*<img width="759" height="416" alt="image" src="https://github.com/user-attachments/assets/0c5f0357-e5ca-45c4-819f-3a3f71beaa99" />
*

---

[↑ Volver al índice](#2-índice-general)

---

## A1
### Blink y Semáforo

### 1. Capítulo 0 — Blink

#### 1.1. Objetivo

#### 1.2. Lista de componentes

#### 1.3. Configuración de Arduino IDE

##### 1.3.1. Selección del modo de carga

##### 1.3.2. Selección del puerto serie

##### 1.3.3. Compilación y carga del programa

#### 1.4. Control y solución de incidencias técnicas

#### 1.5. Preguntas

##### 1.5.1. Información sobre el LED azul que parpadea

##### 1.5.2. ¿Qué son void setup() y void loop()?

##### 1.5.3. ¿Qué significa la línea #define LED_BUITIN 2?

##### 1.5.4. ¿Qué significa delay(1000);?

##### 1.5.5. Funciones utilizadas en el script

### 2. Práctica 1 — LED

#### 2.1. Objetivo

#### 2.2. Componentes necesarios

#### 2.3. Diseño del circuito

#### 2.4. Montaje en la protoboard

#### 2.5. Código Blink

#### 2.6. Preguntas

##### 2.6.1. ¿Qué ocurre al conectar el jumper del pin 2 a 5V?

##### 2.6.2. ¿Qué ocurre al conectar los jumpers a los polos de la pila?

#### 2.7. Evidencias del montaje

### 3. Práctica 2 — Semáforo

#### 3.1. Objetivo

#### 3.2. Componentes necesarios

#### 3.3. Diseño del circuito en Draw.io

#### 3.4. Conexiones de la protoboard

#### 3.5. Código Arduino del semáforo

#### 3.6. Montaje del circuito

#### 3.7. Comprobación del funcionamiento

#### 3.8. Vídeo personal de la práctica

En este vídeo muestro el funcionamiento del semáforo que he montado con la placa ESP32. Los tres LED se encienden uno detrás de otro.

https://github.com/user-attachments/assets/42677446-6aaa-4988-a1eb-3cb9592470c9



#### 3.9. Evidencias

<img width="1719" height="3056" alt="1000168107" src="https://github.com/user-attachments/assets/92316690-c512-4f63-bd02-4c9fce3bbe46" />


<img width="3056" height="3056" alt="1000168116" src="https://github.com/user-attachments/assets/ebd81404-f170-4290-bc85-d187399888bf" />


<img width="3056" height="3056" alt="1000166728" src="https://github.com/user-attachments/assets/e3119db0-c2ac-45f8-9bbb-2f37d0631ae6" />


<img width="1922" height="3047" alt="1000168124" src="https://github.com/user-attachments/assets/d054bfb7-1382-4d4d-b23f-661d281955ce" />


### 4. Webgrafía

[↑ Volver al índice](#2-índice-general)

---

## A2
### LED + Button

#### Objetivo

#### Apartados del cuaderno

[↑ Volver al índice](#2-índice-general)

---

## A3
### LED RGB

---

## A4
### LED Bar

---

## A5
### Serial IO

---

## A6
### WiFi

---

## Conceptos importantes

## Registro de incidencias

## Bibliografía y recursos
