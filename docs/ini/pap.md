!!! abstract "Aviso"
    En este momento, la placa permite ser vinculada con un agente y para comunicarse con la plataforma ai.keyestudio.com es necesario el kit del micrófono y el altavoz. Proximamente está previsto que se pueda programar en SteamakersBlocks.

Esta página ofrece una guía paso a paso para poner en marcha la placa ESP32 STEAMakers AI desde cero. Está pensada para alumnado de secundaria, bachillerato y formación profesional, así como para docentes que deseen introducir proyectos de programación e inteligencia artificial en el aula.

A lo largo de la guía se explican, de forma clara y ordenada, todos los pasos necesarios: desde la primera conexión de la placa al ordenador, la carga del firmware y la vinculación con la plataforma de inteligencia artificial, hasta la realización de las primeras pruebas con un chatbot.

No es necesario tener conocimientos previos: cada apartado incluye explicaciones detalladas, micro-pasos y listas de verificación para evitar errores habituales y facilitar el aprendizaje. Siguiendo esta guía, podrás tener la placa correctamente configurada y lista para empezar a desarrollar proyectos educativos con tecnología e IA.

## <FONT COLOR=#007575>**Antes de comenzar**</font>
Antes de conectar la placa, y con el fin de evitar la mayoría de los problemas iniciales, es importante que te asegures de que tienes todo lo necesario.

Necesitarás:

* Un ordenador con sistema operativo Linux, Windows o MacOS
* Conexión Wi-Fi
* Cable USB-C de datos (asegurate que es de datos y no sólo de carga)
* El kit formado por la placa ESP32 STEAMakers AI, el microfóno y el altavoz

## <FONT COLOR=#007575>**Presentación**</font>
### <FONT COLOR=#AA0000>Què és la placa ESP32 STEAMakers AI</font>
ESP32 STEAMakers AI es una placa basada en el microcontrolador ESP32-S3, pensada para proyectos educativos STEAM.  
Permite:

* Programación visual
* Conexión Wi-Fi y Bluetooth
* Integración con plataformas de inteligencia artificial
* Conexiones fáciles con infinidades de sensores y actuadores

<div class="container-wrapper-genially" style="position: relative; min-height: 400px; max-width: 100%;"><video class="loader-genially" autoplay="autoplay" loop="loop" playsinline="playsInline" muted="muted" style="position: absolute;top: 45%;left: 50%;transform: translate(-50%, -50%);width: 80px;height: 80px;margin-bottom: 10%"><source src="https://static.genially.com/resources/loader-default-rebranding.mp4" type="video/mp4" />Your browser does not support the video tag.</video><div id="68f50fda2e43e30f1ceb7a70" class="genially-embed" style="margin: 0px auto; position: relative; height: auto; width: 100%;"></div></div><script>(function (d) { var js, id = "genially-embed-js", ref = d.getElementsByTagName("script")[0]; if (d.getElementById(id)) { return; } js = d.createElement("script"); js.id = id; js.async = true; js.src = "https://view.genially.com/static/embed/embed.js"; ref.parentNode.insertBefore(js, ref); }(document));</script>

### <FONT COLOR=#AA0000>Entornos</font>
Respecto al entorno de trabajo decir que la placa está diseñada para funcionar:

* Conectada a un ordenador
* Utilizando un navegador web
* Sin instalaciones complejas en estos primeros pasos

Los entornos de programación disponibles para la placa son:

* **STEAMakersBlocks**. Programación visual avanzada que requiere conexión por USB
* **MicroBlocks**. Programación visual ideal para comenzar. Se puede conectar por USB o Bluetooth.
* **Plataforma ai.keyestudio.com**. Permite crear y gestionar agentes de inteligencia artificial.

En esta sección nos centraremos en poner la placa en marcha y hacer una primera prueba con IA.

## <FONT COLOR=#007575>**Puesta en marcha**</font>
### <FONT COLOR=#AA0000>Primera conexión al ordenador</font>
Para conectar la placa por primera vez y que sea reconocida, será necesario descargar e instalar el driver CH340. Éste permite la comunicación entre el dispositivo y la ESP32 STEAMakers AI.

* Accede a la [herramienta web de carga de firmware](https://flash.keyestudio.com/device.html?id=ks5034) y configurala en español si aún no lo está.

!!! info ""
    El driver CH340 es el software requerido para operar con el circuito integrado de la inferfaz USB.

* Descarga el instalador del controlador
* Ejecuta e instala el controlador
* Conecta la placa al ordenador con el cable USB-C
* Tu ordenador ya debería detectarla

![herramienta web de carga de firmware](../img/ini/herramienta_web_carga_firmware.png){.center-img100}

La placa debiera poderse conectar sin problemas y mostrar el siguiente aspecto:

![herramienta web de carga de firmware con placa conectada](../img/ini/herramienta_web_carga_firmware_conect.png){.center-img100}

Si no se conecta:

* Prueba con otro cable USB
* Prueba otro puerto USB
* Reinicia el ordenador

### <FONT COLOR=#AA0000>Montaje del kit y alimentación</font>
La placa puede alimentarse directamente mediante:

* El cable USB-C conectado al ordenador
* Con alimentación externa (no apto para programar)

Para montar los módulos de tu kit es necesario:

* Desconectar la placa de la alimentación
* Conectar los módulos con cuidado
* Revisar que estén bien conectados y que respetan la orientación
* Volver a conectar la placa

![kit montado](../img/ini/kit_montado.png){.center-img75}

El kit consta de los 5 elementos imprescindibles:

* 1 ESP32 STEAMakers AI
* 1 Pantalla TFT de 240x240 px
* 1 Altavoz
* 1 Amplificador SPI
* 1 Micrófono SPI

Hay que fijarse detalladamente en la polaridad y nomenclatura de las conexiones ya que si no las hacemos correctamente existe la posibilidad de romper algún elemento al alimentarlo.

### <FONT COLOR=#AA0000>Carga del firmware</font>
Antes de programar la placa, es necesario cargar el firmware. Para lo que seguiremos los siguientes pasos generales:

* Abre un navegador compatible
* Accede a la [herramienta web de carga de firmware](https://flash.keyestudio.com/)

![herramienta web de carga de firmware (ESP32 WEB Flasher)](../img/ini/ESP32_WEB_Flasher.png){.center-img75}

* Selecciona tu placa
* Selecciona el puerto USB correspondiente en la placa
* Selecciona la última versión del firmware
* Inicia el proceso de carga
* Espera hasta que el navegador indique que ha finalizado

!!! Warning "Durante este proceso:"
    No desconectes la placa  
    No cierres el navegador

A continuación tienes un video con el paso a paso:

<iframe width="1120" height="630" src="https://www.youtube.com/embed/JXXCjN6287A?si=4rYWrsKXgVRQqGXv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Al final deben aparecer los siguientes mensajes:

<center>

![Mensajes finales del flasheo](../img/ini/ESP32_WEB_Flasher_fin.png)  

</center>

### <FONT COLOR=#AA0000>Conexión WiFi</font>
Una vez cargado el firmware es necesario resetear la placa. Para resetearla podemos hacerlo de dos maneras: pulsando el botón de reset o desconectando y conectando el cable USB.

Veremos que aparecen en la pantalla de la placa estos dos datos:

<center>

![Primera pantalla](../img/ini/pant1.png)  

</center>

Para poder conectar la placa a una red WiFi es necesario, primero, conectarse a la red que nos indica en “Connect to:” (KEYES-AI-ED30) y, después, introducir en el navegador la IP que nos indica en “Browser“ (http://192.168.4.1).

Una vez hecho esto debería salirnos una página similar a esta:

<center>

![Pantalla para configurar nuestra Wi-Fi](../img/ini/pant_wifi.png)  

</center>

Aquí es donde debemos establecer los datos de nuestra propia red WiFi para dotar de conexión a internet a la placa.

!!! Warning "IMPORTANTE"
    !!! Note ""
        Es necesario recordar que el ESP32-S3 soporta solamente redes **Wi-Fi de 2.4GHz**

Tras unos instantes nos aparecerá en pantalla el siguiente mensaje:

<center>

![Configuración Wi-Fi guardada](../img/ini/pant_wifi_exit.png)  

</center>

Y lo único que tienes que hacer es seguir las indicaciones del mensaje, es decir, que la placa se resetea automáticamente y la placa con el nuevo firmware queda conectada a nuestra red Wi-Fi.

Si no ocurre el reseteo, hay que resetear la placa manualmente, y ahora nos debe salir un código de 6 dígitos en la pantalla de la placa.

<center>

![Pantalla con el código de 6 digitos](../img/ini/pant_code6.png)  
<FONT COLOR=#FF00FF><b>Copia el código de 6 digitos para usarlo posteriormente</b></font>

</center>

Ya tenemos todo listo para ir al siguiente paso, que es crear nuestro primer agente.

## <FONT COLOR=#007575>**Vinculación con la plataforma AI**</font>
### <FONT COLOR=#AA0000>Configuración de ai.keyestudio.com</font>
El primer paso es registrarse, con este [enlace](https://ai.keyestudio.com/register) podrás crear tu usuario utilizando un correo.

<center>

![Registro de nueva cuenta en ai.keyestudio.com](../img/ini/registro.png)  

</center>

### <FONT COLOR=#AA0000>Creación de un agente</font>
Un agente define cómo se comporta la inteligencia artificial y personalizarlo nos permitirá adaptar ese comportamiento a la funcionalidad que le queramos dar, por ejemplo, éste puede comportarse como un informador de noticias, como un experta ingeniera o incluso como un amigo simpático.

Se puede configurar:

* El rol del agente
* El lenguaje y el tono
* El modelo de inteligencia artificial que utilizará

Una vez identificados la página nos presenta una bienvenida que, configurada en español, tiene el siguiente aspecto:

<center>

![Bienvenida de ai.keyestudio.com](../img/ini/bienve.png)  

</center>

Los agentes están disponibles en la consola, como se ve en la imagen anterior.

Una vez creado, es necesario vincular la placa. Abrimos agentes y veremos algo como:

<center>

![Agentes de ai.keyestudio.com](../img/ini/agentes.png)  

</center>

Pulsando en “Añadir Dispositivo” se abrirá un cuadro donde debemos introducir nuestro código de 6 dígitos que anotamos anteriormente:

<center>

![Añadir dispositivo en ai.keyestudio.com](../img/ini/anadir.png)  

</center>

Una vez añadido el dispositivo ya podemos crear un agente. En la imagen vemos el agente 'prueba' recien creado.

<center>

![Agente prueba en ai.keyestudio.com](../img/ini/prueba.png)  

</center>

Pulsamos en 'configurar rol' y seleccionamos las opciones que nos interesen y ya lo tenemos todo preparado, ¡comenzamos a hacer algunas pruebas!

## <FONT COLOR=#007575>**Primeras pruebas**</font>
### <FONT COLOR=#AA0000>Verificació inicial</font>
Antes de realizar ninguna prueba avanzada, comprueba:

* Que la placa se enciende correctamente
* Que está conectada a la red Wi-Fi
* Que la plataforma reconoce el dispositivo

<center>

![Conexión inicial](../img/ini/1conex.gif)  

</center>

Cuando se muestra 'Pulsar' debes accionar el pulsador 'BOOT' para que se establezca la conexión entre la placa el agente creado en ai.keyestudio.com. Cuando dicha conexión se relice ya puedes iniciar la conversación con el chatbot.

### <FONT COLOR=#AA0000>Primera prueba:chatbot</font>
La primera prueba propuesta es un chatbot.

Esta prueba permite comprobar:

* La comunicación placa ↔ plataforma AI
* Que el firmware funciona correctamente
* Que el agente responde cómo se espera

Si no obtienes respuesta:

* Revisa la conexión a Internet
* Comprueba la configuración del agente
* Reinicia la placa y vuelve a intentarlo

El agente mantiene un histórico de los diálogos mantenidos que se pueden ver como texto o borrarlos.

![](../img/ini/chatbot_conv.png){.center-img100}

