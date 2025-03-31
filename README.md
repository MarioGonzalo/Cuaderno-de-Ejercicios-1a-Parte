# Cuaderno-de-Ejercicios-1a-Parte


## Ejercicio 1

Para un sistema de comunicaciones con 17 niveles de señal, que funciona en banda
base, calcular el máximo ancho de banda si el ruido es despreciable y la tasa de
transmisión es de 10 Mbits/s. ¿Qué tipo de medio guiado se podría utilizar para el
sistema?

Para calcular el máximo ancho de banda emplearemos la fórmula de Nyquist:

$$ C = 2B log_2(M) $$

Siendo C la tasa de transmisión, B el ancho de banda y M el número de niveles de la señal

Tomando la ecuación anterior la modificaremos para poder hallar el ancho de banda resultando en esta fórmula:

$$ B = \frac{C}{2 log_2(M)}$$

Y resolvemos:

$$ B = \frac{10 * 10^6}{2 * log_2(17)} = \frac{10 * 10^6}{2 * 4.0875} = \frac{10 * 10^6}{8.175} = 1,223 * 10^6 Hz = 12,23 MHz$$

## Ejercicio 2

¿Cuál es la tasa de transmisión máxima en un canal óptico con fibra de ancho de banda
de 1 THz y conversores optoeléctricos de 100 Gbaudios, si la relación SNR es de 15
dB y la modulación utilizada en los conversores es de 4 símbolos en cuadratura?

Primero hay que pasar el SNR de db a lineal para lo que emplearemos la fórmula:

$𝑆𝑁𝑅 = 10 𝑙𝑜𝑔_{10}(𝑆𝑁𝑅) = 10^{\frac{SNR}{10}}$ [dB]

Lo que nos da como resultado:

SNR lineal= $10^{\frac{15}{10}} = 10^1,5 = 31,62$

Ahora emplearemos la fórmula de Shannon para calcular la tasa de transmisión siendo "B" el ancho de banda y "C" la tasa de transmisión máxima:

$C = B * log_2(1 + SNR)$

Para utilizarlos en la fórmula de Shannon los GHz del ancho de banda se ha de pasar a hercios

$$1THz = 10^{12}Hz $$

Ahora sustituimos en la fórmula obteniendo:

$$C = 10^{12} * log_2(1 + 31,62) \rightarrow C = 10^{12} * 5,028 \rightarrow  C = 5,028 * 10^{12} Hz = 5,028 THz$$

Como la transimisión máxima depende de la capacidad de los receptores, en este caso será un QSPK ya que es de 4 símbolos calcularemos la capacidad con esto y los baudios de los conversores optoeléctricos con la fórmula

$$R = R_s * m = 100 * 10^9 * 2 = 200 * 10^9 = 200 GHz = 0,2 THz$$ 

## Ejercicio 3

Si en el sistema anterior se introduce un conector de fibra con un 20% de pérdidas,
responder a las siguientes cuestiones: <br>
a) ¿Se verá afectada la tasa de transmisión máxima? <br>
b) ¿Qué velocidad máxima se tendrá en la salida? <br>

## Ejercicio 4

Indicar el tipo de modulación que se está utilizando y los problemas que plantea en los
casos b y c.

![Image](https://github.com/user-attachments/assets/afa8c61b-f4a7-4cfe-9e57-14ed388bf6a9)

Se está empleando 16-QAM como se puede observar en el caso A ya que se ven 16 puntos.

En el caso B se puede ver que los puntos están dispersos con respecto a su posición lo que puede representar ruido en el canal.

En el caso C los puntos están dispersos y además fuera de su cuadrícula lo que representa el ruido del caso B pero también una desincronización y desajuste.

## Ejercicio 5 

Sabiendo que se transmiten dos señales de forma simultánea y que se aplican dos
modulaciones diferentes:<br>
a) Indicar qué dos modulaciones se están aplicando.<br>
b) Recuperar la información de ambas señales.<br>

![Image](https://github.com/user-attachments/assets/87550d4a-5e45-4954-b2ac-323281fcb874)

# Ejercicio 6

Indicar las longitudes de onda que se transmiten en cada uno de los puntos marcados
en el esquema.

![Image](https://github.com/user-attachments/assets/85c5cab4-817a-4acf-839f-8ce16659c439)

En la imagen se observa un sistema de transmisión de señales ópticas con multiplexación por división de longitud de onda (WDM).

Cada fibra tiene una diferente longitud de onda representado por $\lambda$

El combiner se encarga de combinar todas las longitudes de onda en una

Más tarde el splitter distribuye esta longitud de onda por cada cable por lo que en los puntos marcados en el esquema tendrán la misma longitud de onda que será la combinación de las originales

# Ejercicio 7

Se considera una pila de protocolos de 4 capas. La capa 4 envía un bloque de 1 Kbyte.
La capa 3 añade cabeceras de 256 bits y cada paquete es de 512 bytes. La capa 2
añade cabeceras de 512 bits y el campo de datos de las tramas son de 128 bytes. La
capa 1 añade a cada 30 bytes de datos, 32 bits de comienzo, un byte de parada, y 16
bits de CRC. Dibujar todo el proceso de encapsulamiento del sistema transmisor y
calcular la eficiencia del sistema.

- Capa 4 (Bloque de datos):
  - Tamaño: 1 KB = 8192 bits (1024 bytes × 8 bits/byte).

- Capa 3:
  - Se añaden cabeceras de 256 bits = 32 (256/8) bytes
  - Cada paquete es de 512 bytes
  - Para fragmentar los 1024 bytes de la capa 4 se tiene que quitar los 32 bytes de la cabecera al tamaño de los paquetes (512 - 32 = 480)
  - $\frac{1024}{480} = 2,13 Por lo que se usarán 3 paquetes

- Capa 2:
  -  Se añaden cabeceras de 512 bits = 64 bytes
  -  Las tramas son de 128 bytes
  -  Las cabeceras ocupan 64 bytes que hay que quitar de las tramas (128 - 64 = 64)
  -  $\frac{512}{64} = 8 tramas por paquete

- Capa 1:
  - 30 bytes de datos
  - 32 bits de comienzo = 4 bytes
  - 1 byte de parada
  - 16 bits de CRC = 2 bytes
  - 128 + 30 + 32 + 1 + 2 = 165 bytes

Cálculo de eficiencia

Se empleará la fórmula

$$\frac{\text{Datos útiles}}{\text{Datos totales}} * 100$$

Donde los datos útiles serán 1024 bytes y los datos totales serán 3960 por lo que serán:

$$\frac{1024}{3960} * 100 = 25,858%$$

# Ejercicio 8

Un sistema satélite divide la información de la capa 3 en bloques de 1904 bits, a los
que añade una cabecera de 64 bits. Si cada trama tarda en transmitirse 20 ms y la
latencia del satélite es de 85 ms, ¿cuánto tiempo tardará en realizar la transmisión de
5 Mbytes de información?

Se han de enviar 5Mb de información que pasado a bits será

$$5Mb = 5 * 10^6 bytes = 4 * 10^7 \text{ bits}$$

Las tramas son de 1904 bits por lo que para hallar la cantidad de tramas habrá que dividir la cantidad a transmitir entre el tamaño de tramas:

$$\frac{4 * 10^7}{1904} = 3,66 * 10^4 \text{ tramas}$$

Ahora multiplicamos las tramas por su tiempo de transmisión

$$ 3,66 * 10^4 * 20ms = 7,31 * 10^5 ms$$

Se habrá de añadir la latencia a este tiempo aunque es ignorable ya que es muy baja comparada con el tiempo total de transmisión

# Ejercicio 9

Calcular el resultado de un paquete de datos “1111011101010101” en un sistema de
enlace de datos con las siguientes especificaciones:<br>
• Secuencia de inicio de trama “010101010”.<br>
• Protección frente a errores H(7,4).<br>
• Tamaño máximo por trama de 4 bytes.

## Paso 1: División en Tramas

Dado que el tamaño máximo por trama es de 4 bytes (= 32 bits) y nuestro paquete es de 16 bits, se puede encapsular en una sola trama.

## Paso 2: Codificación con Hamming (7,4)

El código H(7,4) toma 4 bits de datos y los codifica en 7 bits, añadiendo bits de paridad para detección y corrección de errores.

Dividimos los datos en bloques de 4 bits:

1111 0111 0101 0101

Codificamos cada bloque con Hamming(7,4):

1111 → 1111010

0111 → 0111011

0101 → 0101001

0101 → 0101001

Por lo que la secuencia codificada con Hamming es:

1111010 0111011 0101001 0101001

## Paso 3: Adición de la Secuencia de Inicio

La secuencia de inicio de trama es "010101010" (9 bits). Al agregarla antes de los datos codificados:

010101010 1111010 0111011 0101001 0101001

## Paso 4: Resultado Final
El paquete transmitido por la capa de enlace de datos es:

0101010101111010011101101010010101001

# Ejercicio 10

Un fabricante indica que su sistema integra un CRC-8 con el siguiente polinomio
generador: 𝐺𝐺(𝑥𝑥) = 𝑥𝑥8 + 𝑥𝑥7 + 𝑥𝑥2 + 1. Plantear los pasos que se deben realizar para
calcular la trama resultante, considerando que el CRC se aplica al final de la trama 2
del ejercicio anterior.

El CRC-8 genera un código de redundancia cíclica de 8 bits, por lo que la nueva trama tendrá 37 + 8 = 45 bits.

El polinomio generador en binario es:

$$G(x) = 100000101$$

Agregamos 8 bits ceros al final de la trama para calcular el CRC:

0101010101111010011101101010010101001000000000

Esto extiende la trama a 45 bits.

Realizamos la división binaria (mod 2) entre esta nueva secuencia y el polinomio 100000101.

Realizamos la división binaria (similar a la división larga en decimal), donde:

Si el bit superior es 1, restamos (XOR) el polinomio generador.

Si el bit superior es 0, simplemente bajamos el siguiente bit.

La operación se realiza en los 37 bits originales, considerando los 8 ceros agregados al final.

Al final del proceso, el residuo de la división (8 bits) será el CRC-8.

El resultado final de la trama con el CRC-8 aplicado es:

010101010111101001110110101001010100111001100

# Pregunta 11

¿Cuántos errores pueden llegar a corregir la codificación H(15,11) y el CRC-32?

La codificación H(15,11) puede detectar dos errores pero solo puede corregir uno mientras que el CRC-32 destaca en detectar errores pero no los puede corregir

# Pregunta 12

La cabecera es: "11111111" (primeros 8 bits).

Los datos codificados son: "01011010101011" (14 bits restantes).

-El código H(14,10):
  -Usa 10 bits de datos.
  -Agrega 4 bits de paridad.

Los bits de paridad están en las posiciones 1, 2, 4 y 8.

Eliminamos las posiciones 1, 2, 4 y 8, obteniendo los datos útiles en las posiciones restantes:

$$0101101011$$

# Pregunta 13

¿A qué protocolo de la capa de enlace de datos corresponde el siguiente esquema
temporal?

![Image](https://github.com/user-attachments/assets/8ceac5d1-145c-42e7-a9dd-ec232438543c)

- El protocolo de la imagen corresponde al protocolo de ventana corrediza concretamente el protocolo Stop-And-Wait ARQ ya que:

  - Envía un solo marco a la vez y espera la confirmación (ACK) antes de enviar el siguiente.
  - Cada trama tiene un número de secuencia (S) que alterna entre 0 y 1.
  - El receptor envía un ACK (reconocimiento) con el número esperado de la siguiente trama.
  - El transmisor solo envía la siguiente trama cuando recibe el ACK correcto.

# Pregunta 14

¿Se puede aplicar el protocolo del ejercicio anterior en el siguiente escenario?

![Image](https://github.com/user-attachments/assets/ecc06bb2-1f12-4db4-811e-8e95caddc592)

No debido a que en este ejemplo el ACK se envia por separado, es decir, este no se incluye dentro del paquete enviado por lo que no es de ventana corrediza

# Pregunta 15

Dibujar un diagrama de ventana deslizante con un receptor con buffer para tres tramas
y un transmisor que dispone de 5 tramas desordenadas que llegan en el orden 0, 3, 2,
4, 1.

# Pregunta 16

Un canal coaxial con FDM con una tasa de transmisión de 500 Mbits/s con una longitud
media de trama de 1/𝜇 = 12584 bits y una tasa de llegada de trama 𝜆 = 20000 trama/s:
a) ¿Qué retardo tendrá?

Primero hay que calcular la tasa de servicio

$$\mu = \frac{C}{L} = \frac{500 * 10^6}{12584} = 39733 trama/s$$

Con esto hallamos el retardo con la fórmula

$$ \frac{1}{\mu - \lambda} = \frac{1}{39733 - 20000} = \frac{1}{19733} = 5,067 * 10^{-5} segundos $$

b) Si lo comparten entre 256 usuarios ¿cuántas portadoras serán necesarias?

Si el canal se comparte entre N=256 usuarios y usa FDM (Multiplexación por División de Frecuencia), entonces cada usuario necesita una portadora separada.

Por lo tanto, el número de portadoras necesarias es 256.

c) ¿Cuánto tiempo tardará un nodo en detectar una colisión?

En un canal de transmisión, el tiempo para detectar una colisión está dado por:

$$ T_{col} = \frac{2*L}{C} = \frac{2 *12584}{500 * 10^6} = 5,034 * 10^{-5} segundos

# Pregunta 17

Representar la trama “1111111101011010101011” con codificación Manchester y
Manchester diferencial. Indicar las unidades y magnitudes en los ejes.

1. Codificación Manchester
   
La codificación Manchester sigue la regla:

Bit 1 → Transición de alto a bajo (↓).

Bit 0 → Transición de bajo a alto (↑).

Cada bit tiene una transición en la mitad del período del reloj.

2. Codificación Manchester Diferencial
   
En Manchester Diferencial, la regla es:

Bit 1 → No hay transición al inicio del bit (mantiene el nivel anterior), pero hay transición en la mitad del bit.

Bit 0 → Hay transición al inicio del bit y también en la mitad.

Este método es más robusto contra errores de polaridad en la señal.

# Pregunta 18

Para soportar 15 nodos activos simultáneamente, utilizaremos dos piconets interconectadas, formando una scatternet:

Piconet 1: 1 Maestro + 7 Esclavos activos.

Piconet 2: 1 Maestro + 8 Esclavos activos (uno de ellos es un puente entre ambas redes).

Un nodo puente participa en ambas piconets, sincronizando la comunicación.

# Pregunta 19


# Pregunta 20

