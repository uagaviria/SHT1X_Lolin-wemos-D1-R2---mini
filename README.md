# WeMos D1 mini - arduino

## DESCRIPCIÓN:
- La Wemos D1 Mini es solo ligeramente más grande que usar un módulo ESP12 directamente y aporta muchas ventajas, como incorporar un puerto Micro SD y conversor serial, regulador de tensión que permite alimentarlo a 5V, y terminales para conectar nuestros dispositivos. La placa Wemos D1 Mini es la versión de menor tamaño de su hermana mayor Wemos D1, Con unas dimensiones de 34.2mm x 25.6mm y un peso de 3g, es una de las placas más pequeñas basadas en el ESP8266.

<img src="https://github.com/uagaviria/Wemos-mini/blob/master/img/Wemos-D1-Mini.jpg" />

## QUE PLATAFORMA PARA PROGRAMARLO USAR?
En el recorrito que he tenido yo a cerca de estos dispositivos Wifi, los he usado como NodeMcu y no como Lolin wemos D1 R2 & mini. Ya que cada uno de estos en el momento de programarlo, se haria de una forma diferente. a continiuacion voy a mostrar un enemplo con cada uno, y la forma de prohramar los pines. 

## Con Lolin wemos D1 R2 & mini
La forma de programar aqui si se fijan en la declaracion de los pines se hace tal cual esta escrita en la pcb del wemos.
# Codigo:

```cpp
#include <SHT1x.h>
 
#define dataPin  D4
#define clockPin D3
SHT1x sht1x(dataPin, clockPin);
 
void setup()
{
   Serial.begin(115200); 
   Serial.println("Inicia el Programa");
}
 
void loop()
{
  float temp_c;
  float temp_f;
  float humidity;
 
  // Read values from the sensor
  temp_c = sht1x.readTemperatureC();
  temp_f = sht1x.readTemperatureF();
  humidity = sht1x.readHumidity();
 
  // Print the values to the serial port
  Serial.print("Temperatura: ");
  Serial.print(temp_c);
  Serial.print("C / ");
  Serial.print(" - Farenheit: ");
  Serial.print(temp_f);
  Serial.print("- Humedad: ");
  Serial.print(humidity);
  Serial.println("%");
 
  delay(2000);
}
```
## Con ModeMcu Esp12
En este caso los pines varian en la forma de programar. mas abajo voy a mostrar una imagen de los pines que deberiamos utilizar, dependiendo de la plataforma a utilizar.
```cpp
#include <SHT1x.h>
 
#define dataPin  2//D4
#define clockPin 0//D3
SHT1x sht1x(dataPin, clockPin);
 
void setup()
{
   Serial.begin(115200); 
   Serial.println("Inicia el Programa");
}
 
void loop()
{
  float temp_c;
  float temp_f;
  float humidity;
 
  // Read values from the sensor
  temp_c = sht1x.readTemperatureC();
  temp_f = sht1x.readTemperatureF();
  humidity = sht1x.readHumidity();
 
  // Print the values to the serial port
  Serial.print("Temperatura: ");
  Serial.print(temp_c);
  Serial.print("C / ");
  Serial.print(" - Farenheit: ");
  Serial.print(temp_f);
  Serial.print("- Humedad: ");
  Serial.print(humidity);
  Serial.println("%");
 
  delay(2000);
}
```


 ## Pines del Wemos:
 Si lo deseo utilizar como arduino ModeMcu Esp12 los pines a declarar son los que estan en azul, de los contrario en Lolin wemos mini estan en gris.
<img src="https://github.com/uagaviria/Wemos-mini/blob/master/img/Wemos_pin.png" />






