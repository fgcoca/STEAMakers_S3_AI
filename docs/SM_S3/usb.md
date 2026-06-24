La placa **STEAMakers AI** (basada en el microcontrolador ESP32-S3) destaca por su capacidad de manejar **USB** de dos formas distintas: **nativo** y **no nativo** (a través de puente USB a UART). Esta versatilidad permite al usuario elegir entre una conexión directa de alta funcionalidad o una conexión de depuración estándar.

Aquí tienes la descripción detallada:

## <FONT COLOR=#007575>**USB OTG Nativo (Native USB)**</font>
[USB On-The-Go](https://es.wikipedia.org/wiki/USB_On-The-Go) conocido también por el acrónimo **USB OTG** y como USB host y como Adaptador para USB es una extensión de la norma USB 2.0, utilizada por primera vez a fines de 2001, que permite a los dispositivos USB tener mayor flexibilidad en la gestión de la interconexión.

* **Descripción**: Es el puerto USB conectado directamente a los pines internos del chip ESP32-S3 (GPIO19 y GPIO20). No requiere un chip externo para comunicarse con el ordenador.
* **Capacidad OTG** (On The Go, se traduce como “para llevar”): Permite que la placa funcione como:

    ◦ **Dispositivo (Device)**: Se emula a sí misma como un teclado, ratón (HID), o unidad de almacenamiento (Mass Storage) al conectarse a un PC.
    
    ◦ **Anfitrión (Host)**: Permite conectar periféricos USB, como teclados o pendrives, directamente a la placa.
* **Uso principal**: Programación directa (flashing), depuración rápida, y proyectos de emulación de periféricos (teclado/ratón)
* **Funcionalidad**: Permite que el chip actúe tanto como dispositivo (un ratón, teclado o unidad de almacenamiento conectada a un PC) como anfitrión/host (conectarle a él un pendrive o un teclado).
* **Ventaja principal**: Puedes emular dispositivos de interfaz humana (HID) o usar protocolos avanzados sin necesidad de chips intermediarios.
* **Programación**: Se puede usar para cargar código directamente mediante el protocolo DFU (Device Firmware Upgrade).

## <FONT COLOR=#007575>**USB No Nativo (Puente USB a UART)**</font>

* **Descripción**: La placa utiliza el chip CH340 intermedio que convierte la señal USB en señal serie (UART - RX/TX) para comunicarse con el ESP32-S3.
* **Funcionalidad**: Su uso principal es la programación y depuración (monitor serie). No tiene capacidades de "Host" ni puede emular teclados/ratones directamente, ya que el PC solo "ve" un puerto COM o serie.
 
    ◦ **Programación**: Se utiliza principalmente para cargar el código (flashing).
    
    ◦ **Consola**: Ideal para visualizar los datos en el monitor serie.

* **Limitaciones**: No puede actuar como Host USB, ni emular dispositivos USB complejos (HID) de forma nativa; solo funciona como puerto serie virtual.
* **Ventaja principal**: Es extremadamente robusto para la carga de código y permite ver mensajes de error en la consola incluso si el firmware principal del chip falla.
* **Conexión**: Internamente se conecta a los pines de transmisión y recepción (TX y RX) del ESP32-S3.

## <FONT COLOR=#007575>**Comparativa**</font>

| Característica | USB OTG Nativo | USB No Nativo (UART) |
| --- | --- |  --- |
| Conexión | Directa a GPIO19/20 | Vía Chip Puente |
| Modo Host | :material-check: SÍ (Lee pendrives, teclado) | :material-close: NO|
| Emulación USB (HID) | :material-check: SÍ (Teclado, ratón) | :material-close: NO|
| Programación | Rápida | Estándar |
| Uso Recomendado | Aplicaciones avanzadas, Gadgets USB | Carga de código y Monitor Serie |
