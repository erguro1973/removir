# <img src="./img/removir_logo.png" width="50" /> RemoVir <img src="./img/removir_logo.png" width="50" /> <img src="./img/borrador.png" align="right" width="100" /> 

## Este repositorio contiene todos los recursos: instrucciones, código, documentación y datos para ayudarte a reciclar un Split (evaporador interior de aire acondicionado) a un eficiente filtro HEPA

Podrás montar un **purificador de aire con filtro HEPA** por poco más del coste de los filtros y lo más importante. Ayudarás a mantener el medio ambiente mientras proteges del contagio de COVID-19 el espacio que más necesites.

<img src="./img/TablaRiesgosCOVID.png" width="400" align="left" />

```text
Hemos querido enfocar nuestros esfuerzos a este tipo 
de dispositivos porque creemos que pueden ser una 
importante ayuda a evitar contagios. Las últimas 
evidencias científicas demuestran la transmisión de 
virus por aerosoles, es decir, por el mismo hecho de 
respirar. Esto aumenta el nivel de COV (Compuestos 
Orgánicos Volátiles entre los que se encuentra el 
virus SARS-CoV-2) algo que va correlacionado con la 
concentración de CO2. Esta evidencia hace necesaria 
una correcta ventilación de los espacios cerrados. 
Lo que es tan importante como mantener una distancia 
mínima.
```
<br>
<br>
<br>

Este proyecto parte de la aportación de Ernesto Gutiérrez [@erguro1973](https://twitter.com/erguro1973) y de los asistente a varios talleres realizados en el [Fablab de Mallorca](http://fablabmallorca.com/) y organizados por la [Asociación de Makers Mallorca](https://makespacemallorca.org/).

<img src="./img/removir_poster.png" width="400" align="right" />

**¿Con que vamos a trabajar?**
* Análisis de flujos de aire.
* Control de motores.
* Uso de filtros HEPA.
* Programación C++ e IDE de Arduino
* Microcontroladores ESP8266.
* Sensores
* Comunicaciones MQTT
<br>

<img src="./img/IMG_9772.JPG" width="200" align="right" />

## Primer RemoVir, un _Mínimo Producto Viable_
Hemos trabajado sobre un Split marca ¿?. Que ha resultado muy adecuado tanto para la sustitución de la electrócnica como para acomodar los filtros HEPA. Aunque se trata de un MPV. pretendemos que alcance un nivel H13 o superior según el estándar europeo EN 1822-1:2009. Incorporaremos un completo sistemas de medición de calidad de aire, CO2, COV, temperatura, humedad y presión atmosférica de manera que sea capaz de adaptar su funcionamiento a las condiciones detectadas.

<img src="./img/IMG_9900.JPG" width="200" align="left" />

### Filtro HEPA (High Efficiency Particulate Air)
Un filtro HEPA funciona con diferentes principios. Lo que determina el comportamiento de la parte impulsora de aire. Una regla básica a tener en cuenta es que una mayor presión de aire puede bajar la eficiencia en la captura de componentes muy pequeños como virus.
El producto elegido ha sido ¿?...
<img src="./img/HEPA_Fundamentos.png" width="400" align="center" />

### Electrónica
Se ha planteado utilizar el WEMOS D1 MINI Pro. Que es un procesador tipo ESP8266 de 16 bits con programación nativa en C++.
El borrador del esquemático de momento es este:
<img src="./removir_breadboard.png" align="center" />

### Estructura
Hay que tener en cuenta que detro de un Split encontraremos un ´evaporizador´. A todos los efectos es un radiador de aluminio que sin formar parte de la estructura del aparato. Le confiere uan rigidez estructural que perderemos si no acomodamos los filtros HEPA teniendo en cuenta esta doble función. El diseño de las piezas adicionales evidentemente es una caso diferente para cada modelo. 
Como ejemplo de cómo hacerlo, se han usado patrones en cartulina que luego se han modelizado en SolidWorks para acabar imprimiendolos en 3D de filamento. Los ficheros podéis encontrarlos en este mismo repo.

### Flujo de aire
Este es un concepto que hay que tener presente durante todo el rediseño del equipo. Tanto en el aspecto de caudal como el de presión. Una cosa el el volumen de aire por hora que podamos hacer pasar el equipo y otra diferente es la presión que el ventilador pueda aplicar al aire que mueve. Evidentemente ambos parámetros se ven disminuidos respecto al modelo de aire acondicionado original al sustituir el evaporizador por los filtro HEPA que ofrecen mucha más resistencia al paso del aire.
No está de más valorar las modificaciones haciendo sencillas pruebas de flujo como esta:
[![RemoVir RealSmokeTest](./img/removir_SmokeTest.png)](https://youtu.be/LHWRh8wFhkA)

### Certificación
Como nos gusta saber si el trabajo está bien hecho, y sobre todo, si cumple su función. Una vez instalado mediremos los parámetros de operación como caudal de aire, reducción de COV, etc... para sacar conclusiones sobre mejoras en la siguiente iteracción.
<br>
Llegado el momento vamos a trabajar sobre la conocida hoja de excel de la Universidad de Hardvard que [tenéis aqui](https://github.com/Makespace-Mallorca/removir/blob/main/doc/Harvard-CU%20Boulder%20Portable%20Air%20Cleaner%20Calculator%20for%20Schools.v1.1.xlsx). Considerando esta plantilla se puede realizar el cálculo del CADR ( CLEAN AIR DELIVERY RATE) necesario del purificador, según el tamaño de la habitación, siendo este un parámetro que se indica en todos estos tipos de elementos. Como orientación, para una habitación media de 50m2 y un nivel de renovación bajo sería necesario al menos uno aparato con capacidad de 400 l/min.



