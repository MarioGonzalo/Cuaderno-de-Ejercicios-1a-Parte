# Cuaderno-de-Ejercicios-1a-Parte

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
