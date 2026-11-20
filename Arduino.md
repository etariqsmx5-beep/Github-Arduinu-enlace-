
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

El objetivo de esta práctica es aprender a controlar el parpadeo de un LED utilizando la placa ESP32 y Arduino IDE.

Con un programa, podemos hacer que el LED se encienda y se apague automáticamente.

#### 1.2. Lista de componentes

Para realizar esta práctica necesitamos:

- **Placa Freenove ESP32-WROVER:** permite ejecutar el programa.
- **Cable USB:** sirve para conectar la placa al ordenador, alimentarla y cargar el código.


#### 1.3. Configuración de Arduino IDE

##### 1.3.1. Selección del modo de carga

Para cargar el programa, primero he conectado la placa ESP32 al ordenador mediante un cable USB.

Después, en Arduino IDE, he seleccionado el modelo de mi placa: **ESP32 Wrover Module**.

Para enviar el código he utilizado la opción **Upload**.

##### 1.3.2. Selección del puerto serie

Después de conectar la placa al ordenador, he entrado en `Tools > Port` y he seleccionado el puerto **COM3**.

Este puerto permite la comunicación entre Arduino IDE y mi placa ESP32.

##### 1.3.3. Compilación y carga del programa

Para comprobar y cargar el programa he seguido estos pasos:

1. Abrir Arduino IDE.
2. Seleccionar la placa ESP32 Wrover Module.
3. Seleccionar el puerto COM3.
4. Abrir el programa Blink.
5. Pulsar **Verify** para comprobar si el código tiene errores.
6. Pulsar **Upload** para enviar el programa a la placa.
7. Comprobar que el programa se ha cargado correctamente.

---

#### 1.4. Control y solución de incidencias técnicas

Para evitar problemas durante las prácticas, es importante tomar algunas precauciones:

- **Desconectar el cable USB:** antes de colocar o cambiar LEDs, resistencias o cables jumper en la protoboard.
- **Revisar las conexiones:** comprobar que cada cable esté conectado en el lugar correcto.
- **Comprobar la polaridad del LED:** identificar correctamente la pata positiva (+) y la negativa (−).
- **Utilizar resistencias:** para limitar la corriente y evitar dañar los LEDs.
- **Comprobar la placa y el puerto:** verificar que hemos seleccionado el modelo ESP32 Wrover Module y el puerto COM correspondiente.

Estas precauciones nos ayudan a evitar errores de conexión y posibles daños en los componentes.

#### 1.5. Preguntas

##### 1.5.1. Información sobre el LED azul que parpadea

En el manual de Freenove se explica que el LED azul de la placa ESP32-S3 está conectado al pin GPIO2.

Con el programa Blink podemos hacer que este LED se encienda y se apague cada segundo.

En mi caso, he utilizado una placa ESP32-WROVER, que es diferente a la del manual.

##### 1.5.2. ¿Qué son void setup() y void loop()?

Son dos funciones que utilizamos cuando programamos en Arduino.

- **void setup():** se ejecuta una sola vez cuando encendemos la placa. Sirve para preparar los pines que vamos a utilizar.
- **void loop():** se repite todo el tiempo mientras la placa está encendida. Aquí ponemos las instrucciones que queremos que se repitan.

Por ejemplo, en el programa Blink, `loop()` hace que el LED se encienda y se apague continuamente.

##### 1.5.3. ¿Qué significa la línea #define LED_BUILTIN 2?

Esta línea sirve para darle un nombre al pin número 2.

```cpp
#define LED_BUILTIN 2
```

En vez de escribir el número 2 cada vez, podemos utilizar `LED_BUILTIN` en nuestro código.

Así es más fácil entender qué pin estamos utilizando.

##### 1.5.4. ¿Qué significa delay(1000);?

La función `delay()` sirve para hacer una pausa en el programa.

El número 1000 significa 1000 milisegundos, que es lo mismo que un segundo.

Por ejemplo:

- `delay(1000);` = 1 segundo.
- `delay(2000);` = 2 segundos.
- `delay(3000);` = 3 segundos.

En Blink, utilizamos esta función para dejar el LED encendido un segundo y apagado otro segundo.

##### 1.5.5. Funciones utilizadas en el script

| Función | ¿Para qué sirve? |
|---|---|
| `#define` | Para dar un nombre a un valor. |
| `void setup()` | Para preparar los pines al iniciar. |
| `void loop()` | Para repetir las instrucciones. |
| `pinMode()` | Para indicar si un pin es de entrada o salida. |
| `digitalWrite()` | Para encender o apagar el LED mediante un pin. |
| `HIGH` | Para poner el pin en nivel alto. |
| `LOW` | Para poner el pin en nivel bajo. |
| `delay()` | Para esperar un tiempo antes de continuar. |

**Referencia:** https://www.arduino.cc/reference/en/

---

### 2. Práctica 1 — LED

#### 2.1. Objetivo

En esta práctica vamos a aprender a conectar un LED a la placa ESP32 utilizando una protoboard y algunos cables.

La idea es conseguir que el LED se encienda y se apague utilizando un programa de Arduino.

#### 2.2. Componentes necesarios

Para hacer esta práctica he utilizado los siguientes materiales:

- **ESP32-WROVER:** es la placa que vamos a programar.
- **GPIO Extension Board:** nos facilita conectar los cables.
- **Protoboard:** sirve para colocar los componentes.
- **LED rojo:** es la luz que queremos encender.
- **Resistencia de 220 Ω:** sirve para proteger el LED.
- **Cables jumper:** sirven para conectar los componentes.
- **Cable USB:** conecta el ESP32 al ordenador.

#### 2.3. Diseño del circuito

Aquí añadiré el esquema del circuito que voy a hacer en Draw.io.

#### 2.4. Montaje en la protoboard

Para montar el circuito, primero desconecto la placa ESP32 del ordenador para evitar problemas al colocar los componentes.

Después sigo estos pasos:

1. Coloco el LED rojo en la protoboard.
2. Compruebo cuál es la pata positiva y cuál es la negativa.
3. Coloco una resistencia de 220 Ω.
4. Conecto el LED al pin GPIO2 utilizando la resistencia.
5. Conecto la pata negativa del LED a GND.
6. Reviso que los cables estén bien colocados.
7. Conecto otra vez la placa al ordenador mediante USB.

Una vez conectado todo, ya puedo cargar el programa en Arduino IDE.

#### 2.5. Código Blink

Para hacer que el LED parpadee, utilizamos este código:

```cpp
#define LED_BUILTIN 2

void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000);

  digitalWrite(LED_BUILTIN, LOW);
  delay(1000);
}
```

Este programa hace que el LED se encienda durante un segundo y después se apague durante otro segundo.

Como está dentro de `void loop()`, se repite continuamente.

#### 2.6. Preguntas

##### 2.6.1. ¿Qué ocurre al conectar el jumper del pin 2 a 5V?

Si conectamos el LED a la alimentación de 5 V, manteniendo la resistencia y la conexión a GND, debería quedarse encendido todo el tiempo.

Esto pasa porque ahora recibe electricidad directamente y ya no depende de las instrucciones del programa.

Por eso, en lugar de parpadear, el LED debería permanecer encendido.

**Resultado de mi prueba:** Pendiente de comprobar.

**Importante:** antes de mover los cables debemos desconectar el USB. No hay que conectar 5 V directamente a un pin GPIO del ESP32.

##### 2.6.2. ¿Qué ocurre al conectar los jumpers a los polos de la pila?

Si conectamos el LED al positivo y al negativo de una pila de 5 V, con la resistencia colocada correctamente, debería encenderse.

En este caso, el LED no necesita el programa de Arduino para encenderse, porque recibe la electricidad directamente de la pila.

Por eso, debería quedarse encendido y no parpadear.

**Resultado de mi prueba:** Pendiente de comprobar.

#### 2.7. Evidencias del montaje

Aquí añadiré las fotografías del circuito y las capturas del programa.

**Captura 1 — Materiales utilizados**

**Captura 2 — Conexión del LED**

**Captura 3 — Código Blink**

**Captura 4 — Funcionamiento del LED**

---

### 3. Práctica 2 — Semáforo

#### 3.1. Objetivo

En esta práctica vamos a construir un semáforo con tres LED utilizando la placa ESP32.

La idea es conseguir que las luces se enciendan una detrás de otra, sin que estén encendidas al mismo tiempo.

Para hacerlo vamos a utilizar una protoboard, resistencias, cables y un programa en Arduino IDE.

#### 3.2. Componentes necesarios

Para montar el semáforo he utilizado estos materiales:

| Componente | Cantidad |
|---|---|
| ESP32-WROVER | 1 |
| GPIO Extension Board | 1 |
| Protoboard | 1 |
| LED rojo | 1 |
| LED azul | 1 |
| LED verde | 1 |
| Resistencias de 220 Ω | 3 |
| Cables jumper | Varios |
| Cable USB | 1 |

**Nota:** En mi montaje he utilizado un LED azul en lugar del amarillo, aunque en la actividad se pide utilizar rojo, amarillo y verde.

#### 3.3. Diseño del circuito en Draw.io

Aquí añadiré el diseño de mi semáforo realizado en Draw.io.

#### 3.4. Conexiones de la protoboard

Para montar el semáforo he colocado los tres LED en la protoboard y los he conectado a diferentes pines de la placa ESP32.

Cada LED tiene una resistencia de 220 Ω para evitar que pase demasiada corriente.

He utilizado los siguientes pines:

- **GPIO2:** LED rojo.
- **GPIO13:** LED azul.
- **GPIO14:** LED verde.

### Tabla de conexiones

| Conexión | Rojo | Azul | Verde |
|---|---|---|---|
| Pata larga (+) | J40 | J45 | J50 |
| Pata corta (−) | J41 | J46 | J51 |
| Resistencia 220 Ω | F40–F43 | F45–F48 | F50–F53 |
| Cable GPIO en protoboard | G43 | G48 | G53 |
| Pin GPIO | GPIO2 | GPIO13 | GPIO14 |
| Cable GND en protoboard | G41 | G46 | G51 |
| Conexión a tierra | GND | GND | GND |

Estas son las posiciones que he utilizado como referencia para conectar los componentes de mi semáforo.

#### 3.5. Código Arduino del semáforo

Después de conectar los LED, he utilizado este código para controlar las luces:

```cpp
#define LED_ROJO 2
#define LED_AZUL 13
#define LED_VERDE 14

void setup() {
  pinMode(LED_ROJO, OUTPUT);
  pinMode(LED_AZUL, OUTPUT);
  pinMode(LED_VERDE, OUTPUT);
}

void loop() {
  // LED ROJO - 3 segundos
  digitalWrite(LED_ROJO, HIGH);
  digitalWrite(LED_AZUL, LOW);
  digitalWrite(LED_VERDE, LOW);
  delay(3000);

  // LED AZUL - 3 segundos
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_AZUL, HIGH);
  digitalWrite(LED_VERDE, LOW);
  delay(3000);

  // LED VERDE - 1 segundo
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_AZUL, LOW);
  digitalWrite(LED_VERDE, HIGH);
  delay(1000);

  digitalWrite(LED_VERDE, LOW);
}
```

### Captura de código Semáforo:

<img width="859" height="539" alt="image" src="https://github.com/user-attachments/assets/121103b1-5017-4c0e-b209-7b2190cf7f23" />


### ¿Cómo funciona mi código?

Primero se enciende el LED rojo durante 3 segundos.

Después se apaga el rojo y se enciende el azul durante otros 3 segundos.

Por último, se apaga el azul y se enciende el verde durante 1 segundo.

Cuando termina, vuelve a empezar desde el rojo.

| LED | Tiempo |
|---|---|
| Rojo | 3 segundos |
| Azul | 3 segundos |
| Verde | 1 segundo |

Así consigo que las luces se enciendan por turnos y no todas a la vez.

#### 3.6. Montaje del circuito

Para montar mi semáforo, primero he desconectado el cable USB de la placa ESP32.

Después he seguido estos pasos:

1. He colocado los tres LED en la protoboard.
2. He comprobado las patas positivas y negativas de cada LED.
3. He colocado una resistencia de 220 Ω para cada LED.
4. He conectado los cables a los pines GPIO2, GPIO13 y GPIO14.
5. He conectado las patas negativas de los LED a GND.
6. He revisado que los cables estuvieran bien conectados.
7. He conectado la placa al ordenador con el cable USB.
8. He abierto Arduino IDE.
9. He seleccionado `ESP32 Wrover Module` y el puerto `COM3`.
10. He pulsado `Verify` para comprobar el código.
11. Después he pulsado `Upload` para cargarlo en la placa.

Al principio tuve que revisar algunas conexiones porque los LED no funcionaban como esperaba.

Después de corregir los cables y comprobar el código, conseguí que los tres LED se encendieran uno detrás de otro.

Para comprobarlo, también he grabado un vídeo donde se puede ver el funcionamiento del semáforo.

#### 3.8. Vídeo personal de la práctica

En este vídeo muestro el funcionamiento del semáforo que he montado con la placa ESP32. Los tres LED se encienden uno detrás de otro.

https://github.com/user-attachments/assets/42677446-6aaa-4988-a1eb-3cb9592470c9



#### 3.9. Evidencias


<img width="800" height="800" alt="1000168107" src="https://github.com/user-attachments/assets/92316690-c512-4f63-bd02-4c9fce3bbe46" />



<img width="800" height="800" alt="1000168116" src="https://github.com/user-attachments/assets/ebd81404-f170-4290-bc85-d187399888bf" />



<img width="800" height="800" alt="1000166728" src="https://github.com/user-attachments/assets/e3119db0-c2ac-45f8-9bbb-2f37d0631ae6" />



<img width="802" height="800" alt="1000168124" src="https://github.com/user-attachments/assets/d054bfb7-1382-4d4d-b23f-661d281955ce" />



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
