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
responder a las siguientes cuestiones:
a) ¿Se verá afectada la tasa de transmisión máxima?
b) ¿Qué velocidad máxima se tendrá en la salida?

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

