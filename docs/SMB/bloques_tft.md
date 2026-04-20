Cuando escogemos como tipo de proyecto "ESP32 STEAMakers S3 + TFT" en el menú "Visualización tenemos la opción de "Pantalla TFT" que ofrece los siguientes bloques:

![Bloques pantalla TFT](../img/SMB/Bloques_tft.png){.center-img100}

En "Pantalla TFT" también tenemos la entrada "RAM" que presenta los siguientes bloques:

![Bloques TFT RAM](../img/SMB/Bloques_tftRAM.png){.center-img100}

Vamos a describir brevemente cada uno de ellos y daremos programas de ejemplo para los mismos.

## <FONT COLOR=#007575>**Bloque Inicializar**</font>
Inicialización con la rotación elegida.

Bloque de un solo uso obligatorio en el bloque ‘Inicializar’

![Bloque Inicializar](../img/SMB/B_ini.png){.center-img33}

Realiza las tareas necesarias para trabajar con la pantalla TFT. Debe ejecutarse al menos una vez en el bloque Inicializar o setup().

El bloque inicializa la pantalla y establece el ángulo en el que deseamos mostrar los datos, permitiendo así trabajar en formato normal o apaisado y la orientación deseada.

En STEAMakersBlocks trabaja con la librería Adafruit_ST7789.h

⇒ ==**Ejemplo inicialización y rotación**==

- [x] [**Descargar programa P01_inic_rotar**](../SMB/prog/P01_inic_rotar.abp)

| Programa | Resultado |
|---|---|
|![P_01_inic_rotar0](../img/SMB/P_01_inic_rotar0.png) |![R_01_inic_rotar0](../img/SMB/R_01_inic_rotar0.png) |
|![P_01_inic_rotar180](../img/SMB/P_01_inic_rotar180.png) |![R_01_inic_rotar180](../img/SMB/R_01_inic_rotar180.png) |
|![P_01_inic_rotar90](../img/SMB/P_01_inic_rotar90.png) |![R_01_inic_rotar90](../img/SMB/R_01_inic_rotar90.png) |
|![P_01_inic_rotar270](../img/SMB/P_01_inic_rotar270.png) |![R_01_inic_rotar270](../img/SMB/R_01_inic_rotar270.png) |

## <FONT COLOR=#007575>**Retroiluminación**</font>
En la librería los comandos que controlan el pin físico de retroiluminación (backlight) de la pantalla son:

* **backlight(1)**: Enciende los LEDs traseros del panel (luz encendida).
* **backlight(0)**: Apaga los LEDs traseros (pantalla a oscuras).

El bloque Retroiluminación, Backlight o Activación es:

![Bloque Retroiluminación](../img/SMB/B_backlight.png){.center-img33}

La utilidad de este bloque radica en:

1. **Ahorro de energía**: Apagar la retroiluminación es la forma más rápida de reducir el consumo de batería de tu proyecto sin apagar el microcontrolador.
2. **No borra datos**: Alternar estos comandos no borra lo que hay en la pantalla; simplemente hace que sea visible o invisible para el ojo humano.

⇒ ==**Ejemplo de retroiluminación**==

- [x] [**Descargar programa P02_backlight**](../SMB/prog/P02_backlight.abp)

El programa hace parpadear el mensaje en pantalla. Se muestra el mensaje 1 segundo y se pasa el estado a ON (desactiva la retroiluminación por ser activo a nivel bajo) espera 2 segundo y se pone en OFF (activa la retroiluminación) volviendo a ser visible el mensaje durante 1 segundo, y así sucesivamente.

![P02_backlight](../img/SMB/P02_backlight.png){.center-img75}

En la animación se ve el funcionamiento del programa:

![P02_backlight](../img/SMB/F02_backlight.gif){.center-img}

## <FONT COLOR=#007575>**Fondo de pantalla**</font>
Se trata del color de fondo o relleno de pantalla (Fill). El color se selecciona de la paleta siguiente haciendo clic sobre el cuadrado de color negro:

![Paleta de colores](../img/SMB/paleta.png){.center-img33}

El bloque para establecer el color de fondo de la pantalla es:

![Bloque Fondo de pantalla](../img/SMB/B_fonfo_pant.png){.center-img}

⇒ ==**Ejemplo fondos pantalla**==

- [x] [**Descargar programa P03_fondoPantalla**](../SMB/prog/P03_fondoPantalla.abp)

En el ejemplo anterior vamos a cambiar los bloques de retroiluminación por este bloque y establecer como colores de fondo blanco y negro.

![P03_fondoPantalla](../img/SMB/P03_fondoPantalla.png){.center-img75}

El efecto ahora será que el texto se muestra cuando el fondo es negro y no se muestra cuando el fondo es blanco. Observamos así la diferencia entre los bloques Backlight y Fill.

![P03_fondoPantalla](../img/SMB/F03_fondoPantalla.gif){.center-img}

## <FONT COLOR=#007575>**Dibujo de pixeles**</font>
El bloque que dibuja el pixel de coordenadas (x,y) del color establecido es:

![Bloque Dibujo de pixeles](../img/SMB/B_dib_pixel.png){.center-img}

⇒ ==**Ejemplo de dibujo de pixeles**==

- [x] [**Descargar programa P04_dibuja pixel**](../SMB/prog/P04_dibuja pixel.abp)

El programa siguiente va a dibujar cada 3 segundos dos patrones rectangulares de pixeles de dos colores diferentes dejando en blanco un número aleatorio de líneas entre cada línea.

![P04_dibuja pixel](../img/SMB/P04_dibuja pixel.png){.center-img75}

El funcionamiento es el siguiente:

![P04_dibuja pixel](../img/SMB/P04_dibuja pixel.gif){.center-img}

## <FONT COLOR=#007575>**Dibujo de líneas**</font>
El bloque que dibuja una línea entre los puntos de coordenadas (x0,y0) y (x1,y1) es:

![Bloque Dibujo de líneas](../img/SMB/B_dib_linea.png){.center-img75}

⇒ ==**Ejemplo de dibujo de líneas**==

- [x] [**Descargar programa P05_dibuja lineas**](../SMB/prog/P05_dibuja lineas.abp)

El programa siguiente dibujará 50 líneas de color azul desde unas coordenadas (x0,y0) aleatorias hasta la coordenada (10,10). El proceso se repite cada 2 segundos desde una pantalla con fondo gris claro.

![P05_dibuja lineas](../img/SMB/P05_dibuja_lineas.png){.center-img100}

El funcionamiento es el siguiente:

![P05_dibuja lineas](../img/SMB/P05_dibuja_lineas.gif){.center-img}

## <FONT COLOR=#007575>**Dibujo de rectángulos**</font>
El bloque dibuja un rectángulo a partir de las coordenadas (x,y) dadas de la altura y anchura indicadas y en el color elegido. El rectángulo se rellena si fill está en ON o solamente se dibuja el perímetro si está en OFF. El bloque es:

![Bloque Dibujo de rectángulos](../img/SMB/B_dib_rect.png){.center-img75}

⇒ ==**Ejemplo de dibujo de rectángulos**==

- [x] [**Descargar programa P06_dibuja rectangulo**](../SMB/prog/P06_dibuja rectangulo.abp)

El programa siguiente dibuja 10 rectángulos de 60x50 px en color verde en coordenadas (x,y) definidas por patrones aleatorios. Dichos rectángulos se rellenan a la mitad en color azul. El proceso se repite tras una espera de 2 segundos.

![P06_dibuja rectangulo](../img/SMB/P06_dibuja_rectangulo.png){.center-img100}

El funcionamiento es el siguiente:

![P06_dibuja rectangulo](../img/SMB/P06_dibuja_rectangulo.gif){.center-img}
