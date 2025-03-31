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



