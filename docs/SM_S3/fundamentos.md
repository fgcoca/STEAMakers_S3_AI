# <FONT COLOR=#8B008B>Notas sobre ESP32 STEAMakers AI</font>
## <FONT COLOR=#007575>**Referencias principales**</font>

* La hoja de datos - [Datasheet ESP32-S3-WROOM-1](https://documentation.espressif.com/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)
* El manual de referencia - [ESP32-S3. Technical Reference Manual Version 1.8](https://documentation.espressif.com/esp32-s3_technical_reference_manual_en.pdf)
* Hoja de datos de la serie S3 - [ESP32-S3 Series. Datasheet Version 2.2](https://documentation.espressif.com/esp32-s3_datasheet_en.pdf#cd-pins-peri-assignment)
* [Pinout y detalles del hardware del ESP32-S3](https://www.luisllamas.es/esp32-s3-detalles-hardware-pinout/)

## <FONT COLOR=#007575>**Pines utilizados en STEAMakers AI**</font>
Todos los pines GPIO (General Purpose Input Output) son pines de entrada, salida o alta impedancia. Los pines GPIO se pueden asignar a diferentes funciones mediante programación.
El ESP32-S3 integra un amplio conjunto de funcionalidades, entre las que se incluyen:

* **Protocolo de comunicación SPI** (Serial Peripheral Interface). Cuenta con cuatro interfaces SPI0, SPI1, SPI2, y SPI3. El SPI0 se usa para conectar con la memoria FLASH, y el SPI1 para PSRAM. Al SPI2 se conecta el zócalo para tarjeta SD. El SPI3 se asocia a los pines D10 a D13.
* **UART** (Universal Asynchronous Receiver/Transmitter). Protocolo de comunicación serie asíncrono de hardware que permite el intercambio de datos entre el chip y dispositivos externos. Dispone de tres, la UART0 se conecta al conversor USB a serie utilizado para programación y depuración. La UART1 está reservado para la memoria flash integrada. La UART2 queda disponible para conectar dispositivos de este tipo.
* **Protocolo I2C** (Inter-Integrated Circuit). Permite conectar hasta 112 dispositivos. Los pines SDA y SCL están asignados a GPIO8 y GPIO9.
* **Protocolo I2S** (Inter-IC Sound). Estándar de interfaz de bus serie para transmitir datos de audio digital sin comprimir entre circuitos integrados.
* **PWM para LED**. El controlador PWM para LED es un periférico diseñado para generar señales PWM para el control de LED. Cuenta con funciones especializadas, como el atenuado automático del ciclo de trabajo. No obstante, el controlador PWM para LED también puede utilizarse para generar señales PWM con otros fines.
* **MCPWM** (Motor Control Pulse Width Modulator). Proporciona seis salidas PWM que pueden configurarse para funcionar en varias topologías. Una topología habitual utiliza un par de salidas PWM que controlan un puente en H para regular la velocidad y el sentido de giro del motor. Los recursos de temporización y control internos se distribuyen en dos tipos principales de submódulos: temporizadores PWM y operadores PWM. Cada temporizador PWM proporciona referencias de temporización que pueden funcionar de forma independiente o sincronizarse con otros temporizadores o fuentes externas. Cada operador PWM cuenta con todos los recursos de control necesarios para generar pares de formas de onda para un canal PWM. El periférico MCPWM también contiene un submódulo de captura dedicado que se utiliza en sistemas en los que es importante la sincronización precisa de eventos externos.
* **USB serie/JTAG** para programación. El JTAG (Joint Test Action Group) es una interfaz de depuración por hardware integrada que permite programar, detener la ejecución (breakpoints), inspeccionar memoria y variables en tiempo real, sin hardware externo.
* **Sensor táctil**. Los pines Touch pueden detectar variaciones en su capacitancia provocadas al tocarlos o acercarse a los pines GPIO con un dedo u otros objetos.
* **Sensor de temperatura**. El sensor de temperatura genera una tensión que varía en función de la temperatura. La tensión se convierte internamente, mediante un convertidor analógico-digital (ADC), en un valor digital. El sensor de temperatura tiene un rango de –40 °C a 125 °C. Está diseñado principalmente para detectar los cambios de temperatura en el interior del chip.
* **Interfaz USB 2.0 On-The-Go (OTG) de velocidad máxima**. La interfaz USB OTG cumple con la especificación USB 2.0.

El ESP32-S3 integra dos ADC SAR (Successive Approximation Register - Registro de Aproximaciones Sucesivas). Es un convertidor analógico-digital de 12 bits y admite mediciones en 20 canales. Los pines están habilitados para analógico.  La conversión analógica-digital tiene entonces $2^{12}$ = 4096 niveles discretos y como el ESP32 S3 trabaja a 3,3V, la precisión es de 3,3/4096 = 0,81 mV.

El ESP32-S3-WROOM-1 es un potente módulo MCU genérico con Wi-Fi y Bluetooth LE, basado en la serie de SoC ESP32-S3. Además de un amplio conjunto de periféricos, la aceleración para las tareas de computación de redes neuronales y procesamiento de señales que proporciona el SoC convierte a estos módulos en la opción ideal para una amplia variedad de escenarios de aplicación relacionados con la IA y la Inteligencia Artificial de las Cosas (AIoT), tales como la detección de palabras de activación, el reconocimiento de comandos de voz, la detección y el reconocimiento facial, el hogar inteligente, los electrodomésticos inteligentes, los paneles de control inteligentes, los altavoces inteligentes, etc.

El ESP32-S3-WROOM-1 incluye una antena integrada en la placa de circuito impreso.

Wi-Fi y Bluetooth comparten la misma antena mediante mecanismos internos de coexistencia.

!!! Note "Sobre SoC"
    SOC (System on Chip) es un chip que combina varios componentes esenciales de un sistema electrónico en un único integrado. Suele incluir una o más CPUs, memoria, almacenamiento, controladores de entrada/salida, etc.

