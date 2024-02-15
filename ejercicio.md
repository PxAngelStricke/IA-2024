# Ejercicios de IA

## Obtener la secuencia de percepcion y medida de rendimiento

### 1. Problema de Flavio Josefo (secuencia de percepcion)

Planteamiento: 40 Solados en circulo, matan al de la izquierda hasta que quede uno ¿Dónde se debe de colocar Josefo?

~~~
Posicion inicial
[s1][s40][s39][s38][s37][s36][s35][s34][s33][s32]
[s2]                                        [s31]
[s3]                                        [s30]
[s4]                                        [s29]
[s5]                                        [s28]
[s6]                                        [s27]
[s7]                                        [s26]
[s8]                                        [s25]
[s9]                                        [s24]
[s10]                                       [s23]
[s11]                                       [s22]
[s12][s13][s14][s15][s16][s17][s18][s19][s20][s21]
~~~

Para este problema primero debemos entender que el circulo incial es un numero par, por lo cual en la primera vuelta los numeros pares serán eliminados, quedandonos solo 20 sobrevivientes

~~~
Primera vuelta
[s1][][s19][][s17]
[]           []
[s3]         [s15]
[]           []
[s5]         [s13]
[]           []
[s7][][s9][][s11]

~~~

Despues veremos que los que seran eliminados tendran una eliminacion de tipo `4s+3` (donde S es la posicion del soldado), y esto hara que solo nos queden 10 soldados. 

~~~
Segunda vuelta
[s1][][s19][][s17]
[]           []
[s3]         [s15]
[]           []
[s5]         [s13]
[]           []
[s7][][s9][][s11]

~~~