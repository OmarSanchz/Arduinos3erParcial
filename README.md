# Arduinos3erParcial
Código 1: Control de un display de 7 segmentos con números aleatorios
-
Explicación detallada:
Este código controla un display de 7 segmentos, un componente común en electrónica que permite mostrar números del 0 al 9. Utiliza un pulsador para alternar entre dos estados: la generación continua de números aleatorios y la pausa para mostrar un único número.
Estructura y funcionamiento:
Inicialización:
El array numero[] almacena las combinaciones binarias necesarias para encender los segmentos específicos del display. Por ejemplo, para mostrar el número 1, solo se deben activar los segmentos correspondientes, y el valor binario se establece como 0b0110000.
Configuración (setup):
Los pines conectados al display (3 a 10) se configuran como salidas.
El pulsador conectado al pin 2 se configura como entrada.
Generación de números:
En el bucle principal (loop), se usa random(1, 7) para generar números aleatorios entre 1 y 6.
Si el pulsador está presionado, el estado cambia: el programa alterna entre detener y reanudar la generación de números.
Control del display:
Dependiendo del número generado, los segmentos correspondientes se activan mediante un bucle que asigna los valores del array numero[] a los pines de salida.
Usos prácticos:
Simulación de un dado electrónico.
Aplicaciones educativas para enseñar conceptos básicos de electrónica digital y control de displays.
Código 2: Control de LEDs con un joystick analógico
-
Explicación detallada:
Este programa utiliza un joystick analógico para controlar cuatro LEDs que representan las direcciones (arriba, abajo, izquierda, derecha) y un LED adicional para el botón de pulsación.
Estructura y funcionamiento:
Inicialización:
Los pines de los LEDs se configuran como salidas.
Los ejes X y Y del joystick están conectados a entradas analógicas (A0 y A1).
El botón del joystick está conectado a un pin digital con un pull-up interno activado.
Lectura del joystick:
Se leen valores analógicos del joystick mediante analogRead(). Estos valores están entre 0 y 1023.
Dependiendo del valor, el programa determina si el joystick se mueve hacia arriba, abajo, izquierda o derecha:
Valores > 700: Dirección hacia adelante o derecha.
Valores < 300: Dirección hacia atrás o izquierda.
Control de LEDs:
Se activan los LEDs correspondientes según la dirección detectada.
Si el botón del joystick está presionado (LOW), se enciende un LED adicional.
Monitor serial:
Se imprimen los valores de los ejes X, Y y el estado del botón en el monitor serial, útil para depuración.
Usos prácticos:
Interfaz de control para robots o dispositivos electrónicos.
Entrenamiento práctico en el uso de sensores analógicos.
Código 3: Teclado matricial para ingresar contraseñas
-
Explicación detallada:
Este programa permite ingresar una contraseña usando un teclado matricial. La contraseña ingresada se compara con una clave maestra predefinida. Si es correcta, se enciende un LED verde; si no, se enciende un LED rojo.
Estructura y funcionamiento:
Inicialización:
Se define el mapeo de teclas en el array keys.
Los pines para las filas y columnas del teclado están especificados en pinesFilas y pinesColumnas.
Configuración (setup):
Se inicializan los LEDs como salidas.
Se establece la comunicación con el monitor serial para depuración.
Lógica principal (loop):
Cada vez que se presiona una tecla, se almacena en el array CLAVE.
Cuando se ingresan 6 caracteres, el programa compara la clave ingresada con la clave maestra usando strcmp().
Acciones según el resultado:
Si la clave es correcta:
Se enciende el LED verde por 2 segundos.
Si es incorrecta:
Se enciende el LED rojo por 2 segundos.
Usos prácticos:
Sistemas básicos de control de acceso.
Simulación de dispositivos de seguridad.
Código 4: Control de un LED RGB con botones
-
Explicación detallada:
Este código controla un LED RGB utilizando tres botones. Cada botón activa un color primario: rojo, verde o azul.
Estructura y funcionamiento:
Inicialización:
Los pines del LED RGB están conectados a salidas PWM.
Los botones están conectados a entradas digitales.
Lógica principal (loop):
Se verifica el estado de cada botón.
Según el botón presionado, la función encenderColor() establece los valores de los canales rojo, verde y azul del LED RGB.
Usos prácticos:
Control básico de iluminación decorativa.
Aprendizaje de LEDs RGB y mezcla de colores.
Código 5: Sistema con sensor ultrasónico y servomotor
-
Explicación detallada:
Este código utiliza un sensor ultrasónico para detectar la proximidad de un objeto y controla un servomotor que simula abrir y cerrar una puerta.
Estructura y funcionamiento:
Sensor ultrasónico:
El sensor mide la distancia al objeto calculando el tiempo que tarda un pulso de sonido en regresar.
Si la distancia medida es menor a 5 cm, se considera que un objeto está cerca.
Control del servomotor:
Si un objeto está cerca:
Se enciende un LED verde y el servomotor mueve la puerta para abrirla.
Después de 3 segundos, el servomotor cierra la puerta y se enciende un LED rojo.
Usos prácticos:
Simulación de puertas automáticas.
Aplicaciones en sistemas de acceso sin contacto.
Código 6: Control de una puerta con servomotor
-
Explicación detallada:
Este código simula un sistema de control de una puerta que se abre y cierra gradualmente utilizando un servomotor.
Estructura y funcionamiento:
Funciones principales:
AbrirPuerta(): Mueve el servomotor en pasos pequeños para abrir la puerta.
CerrarPuerta(): Mueve el servomotor en pasos pequeños para cerrar la puerta.
Indicadores LED:
Durante la apertura o cierre, se activan LEDs para indicar el estado de la puerta.
Usos prácticos:
Demostraciones de sistemas de apertura automática.
Aprendizaje de control preciso de servomotores.
