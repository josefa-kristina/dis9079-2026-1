# sesion-02  
### Grupo Jesu, Carla y Magda 
 
## codigos apunte probando    
_probando italica_  
**probando bold**   
<sub> subindice </sub>  
<ins> hola </ins> 
> cita texto
 
### lenguaje Arduino 

1. la placa de desarrollo es el microcontrolador <ins> Arduino Uno R4 **WiFi** </ins>.
2. el <ins> software Arduino IDE </ins> es donde escribiremos el código que correrá en la placa.
3. el <ins> lenguaje de programación Arduino </ins> que es un dialecto del lenguaje C++.

 {= murcielago  
 (= paréntesis  
 [= corchete  

 ### Comenzando:  
 
  <sub> setup(): esta función corre una sola vez, al inicio del programa. se usa para configurar estado inicial y configurar entradas y salidas. </sub>  

```
void setup() {   
}
``` 
 
<sub> loop(): esta función corre después de setup(), y se repite en bucle infinito. se usa para escribir código que actualiza el estado del programa, como lectura de sensores, procesamiento de información, y control de actuadores. </sub> 

``` 
void loop() {    
 }  
```

 ### Ejemplo trabajado hoy  
```c++
// ejemplo00
// imprime la sigla del curso en el monitor serial
// luego espera 1 segundo e imprime :)
// funciona con Arduino Uno R4 WiFi
// marzo 2026
// por montoyamoraga para disenoUDP

// crear instancia de ArduinoLedMatrix
// con nombre pantalla
ArduinoLEDMatrix pantalla;

void setup() {
  // iniciar puerto serial
  Serial.begin(9600);
}

void loop() {
  // imprimir en consola
  Serial.println("dis9079");
  // esperar un segundo
  delay(1000);

  // imprimir en consola
  Serial.println(":)");
  // esperar un segundo
  delay(1000);
}
```

 ```c++
// ejemplo01
// imprime la sigla del curso en la pantalla led
// de la Arduino Uno R4 WiFi
// basado en
// https://docs.arduino.cc/tutorials/uno-r4-wifi/led-matrix/#scrolling-text-example
// marzo 2026
// por montoyamoraga para disenoUDP

// incluir bibliotecas
#include <ArduinoGraphics.h>
#include "Arduino_LED_Matrix.h"

// declarar instancia de ArduinoLEDMatrix
// con nombre pantalla
ArduinoLEDMatrix pantalla;

void setup() {

  // iniciar puerto serial
  Serial.begin(115200);

  // inicializar pantalla
  pantalla.begin();

}

void loop() {

  // definir nuevo dibujo
  pantalla.beginDraw();

  // definir trazo
  pantalla.stroke(0xFFFFFFFF);

  // definir velocidad de deslizamiento
  pantalla.textScrollSpeed(100);

  // definir texto
  const char texto[] = "    diseno udp dis9704 interacciones inalambricas    ";
  
  // definir tipo
  pantalla.textFont(Font_5x7);

  // definir inicio del texto
  pantalla.beginText(0, 1, 0xFFFFFF);

  // imprimir el texto
  pantalla.println(texto);

  // deslizar hacia la izquierda
  pantalla.endText(SCROLL_LEFT);

  // fin del dibujo
  pantalla.endDraw();
}
``` 

 
  
### Mosquitto  

intermediario de mensajes (broker) de código abierto diseñado para implementar los protocolos MQTT
  
lunes 16 marzo 2026 
