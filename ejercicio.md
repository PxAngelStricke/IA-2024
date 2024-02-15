# Ejercicios de IA

## Obtener la secuencia de percepcion y medida de rendimiento

### 1. Problema de Flavio Josefo (secuencia de percepcion)

**Planteamiento:** 40 Solados en circulo, matan al de la izquierda hasta que quede uno ¿Dónde se debe de colocar Josefo?

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

En este caso el circulo de la muerte se puede resolver por medio de una formula donde el sobreviviente quedara en la posicion `2m+1` pero ¿Como obtenemos esta `m`? pues primero dependiendo de la cantidad de soldados tendremos que descomponerlos en factores de 2, en este caso son `N = 40 soldados`

1. Convertimos en factor de 2 a N
   ¿Por cual numero debo elevar el 2 para estar mas cerca del 40?
   `2^5 = 32`
   Ahora solo sumamos el restante para llegar a N soldados
   `2^5 + 8 = 40`
2. Este restantees el que será nuestra m de nuestra formula `2m+1`
   Reemplazamos m en la formula
   `2(8) + 1 = 17`
3. Listo, el sobreviviente quedara en la posicion 17


Veamos si esto es cierto.

~~~
Primera vuelta
[s1][X][s39][X][s37][X][s35][X][s33][X]
[X]                                 [s31]
[s3]                                 [X]
[X]                                 [s29]
[s5]                                 [X]
[X]                                 [s27]
[s7]                                 [X]
[X]                                 [s25]
[s9]                                 [X]
[X]                                 [s23]
[s11]                                [X]
[X][s13][X][s15][X][s17][X][s19][X][s21]
~~~

~~~
Segunda vuelta
[s1][X][X][X][s37][X][X][X][s33][X]
[X]                             [X]
[X]                             [X]
[X]                             [s29]
[s5]                            [X]
[X]                             [X]
[X]                             [X]
[X]                             [s25]
[s9]                            [X]
[X]                             [X]
[X]                             [X]
[X][s13][X][X][X][s17][X][X][X][s21]
~~~

~~~
Tercera vuelta
[s1][X][X][X][X][X][X][X][s33][X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [s25]
[s9]                          [X]
[X]                           [X]
[X]                           [X]
[X][X][X][X][X][s17][X][X][X][X]
~~~

~~~
Cuarta vuelta
[X][X][X][X][X][X][X][X][s33][X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X][X][X][X][X][s17][X][X][X][X]
~~~

~~~
Ultima vuelta vuelta
[X][X][X][X][X][X][X][X][X][X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X]                           [X]
[X][X][X][X][X][s17][X][X][X][X]
~~~

Como podemos observar efectivamente el soldado 17 fue el ultimo que sobrevivio. Como ultima curiosidad, podemos obtener este mismo resultado de una manera muchisimo mas sencilla, la cual la podemos obtener convirtiendo los N soldados a un numero binario, despues el primer digito binario moverlo al final y convertir nuevamente ese numero binario a decimal.

Por ejemplo:
Tenemos `N = 40` soldados esto convertido a binario es `101000`, movemos el primer digito hacia el final quedandonos de esta manera `010001` y al convertirlo a decimal nos da `17`, que es el numero de sobreviviente que quedará al final. 


### 2. Las 100 cajas y los 100 prisioneros
**Planteamiento:** 100 cajas con número, cada prisionero tiene un número. Si todos encuentran su numero ganan
Sí uno falla todos mueren.