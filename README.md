# Ambientes de desarrollo de software
Tarea Big O session 02 

1 La notación de Landau
1.1 Definición de O(g)

    La función f pertenece a la clase de complejidad de g (en símbolos, f ∈ O(g)) si existe un c y un n₀ tales que para todo n ≥ nₒ se tiene que |f(n)| ≤ c|g(n)|
    f ∈ O(g) syss ∃c∃nₒ∀n(n ≥ n₀ → |f(n)| ≤ c|g(n)|)
    f ∈ O(g) syss

limsup   |f(x)/g(x)| < ∞
x → ∞

    Intuitivamente, sólo se considera el término más importante y se ignoran los factores constantes.
    Ejemplos:
        3n²+5n-7 ∈ O(n²).
        O(2g(n)) = O(g(n))
        O(log n) = O(ln n)
        O(3n²+5n-7) = O(n²)
        O(n²) ⊂ O(n³)
        O(2ⁿ) ⊂ O(3ⁿ)
        
        
2 Órdenes de complejidad
2.1 Principales órdenes de complejidad

    Orden 	Nombre
    O(1) 	constante
    O(log n) 	logarítmica
    O(n) 	lineal
    O(n log n) 	casi lineal
    O(n²) 	cuadrática
    O(n³) 	cúbica
    O(a^n) 	exponencial

2.2 Tasas de crecimiento

![image](https://www.cs.us.es/~jalonso/cursos/i1m/temas/tema-28/fig/ordenes.png)

# Complejidad Logaritmica
1 Especificación de la función binarySearch
    Precondicion:
    La lista tiene que estar ordenada.
    
    calculada usando las propiedades
    Valor a buscar
    Lista Ordenada
    Primera posicion 
    ultima posicion
    posicion media

2 Definición recursiva de la función binarySearch

posicion_media :: (ultima_posicion + Primera_posicion) /2

      if (posicion_media < Primera_posicion)
          return no_encontrado 

      if (Lista_Ordenada[posicion_media] > Valor_a_buscar)
          return BinarySearch(Lista_Ordenada, Valor_a_buscar, Primera_posicion, posicion_media-1)
      else if (A[mid] < value)
          return BinarySearch(Lista_Ordenada, Valor_a_buscar, posicion_media+1, ultima_posicion)
      else
          return Primera_posicion


Estadísticas de la función binarySearch

    El tiempo necesario para buscar (potencia 2 n) para n en [1024,2048,4096,8192,16384,32768] se recoge en la siguiente tabla

       N	   time     position
      1024	   595	       853
                      
      2048	    18	      1067
                      
      4096	     3	       803
                      
      8192	     4	      2055
                      
     16384	     3	     13551
                      
     32768	     7	     15685
                      
     65536	     5	     14723
                      
    131072	     6	     34713
                      
    262144	    15	    234065
                      
    524288	    23	    349561

4 Ecuaciones de coste de la función binarySearch

    Si T(n) es el tiempo necesario para encontrar un valor en una lista ordenada (de longitud n), entonces

T(1) = 1
T(n) = 1 + T(n/2)

5 Demostración de que binarySearch pertenece O(log n)

    Basta demostrar que para la función binarySearch, T(n) = 1 + log n (logaritmo en base 2).
    Se demuestra por inducción.
    Caso base:

T(1) = 1 = 1 + log 1

    Caso inductivo:

T(n) 
= 1 + T(n/2)           [por coste de binarySearch]
= 1 + (1 + log(n/2))   [por hipótesis de inducción]
= 1 + (1 + log n - 1)  [por álgebra]
= 1 + log n            [por álgebra]


T(n) 
= 1 + T(n/2)

= 1 + ( 1 + T(n/4))


# Complejidad Exponencial

1 Especificación de la función fibonacci

    Programa que muestra los N primeros números de la sucesión de Fibonacci de forma recursiva. Ejemplo de los primeros números de Fibonacci: 0,1,1,2,3,5,8,13,21,34…

2 Definición recursiva de la función fibonacci

f(0) = 0
f(1) = 1

Caso recursivo:
f(n) = f(n-1) + f(n-2)

3 Estadísticas de la función fibonacci

    El tiempo necesario para calcular (raiz 100 n) para n en [14..20] se recoge en la siguiente tabla

    n 	segs
    14 	0.14
    15 	0.27
    16 	0.53
    17 	1.04
    18 	2.03
    19 	4.08
    20 	8.10

    En la tabla se observa que por cada número que aumenta n se duplica el tiempo y el espacio. Por tanto la relación entre n y el tiempo necesario para calcular (raiz 100 n) es del orden 2ⁿ

4 Ecuaciones de coste de la función fibonacci

    Si T(n) es el tiempo necesario para calcular (raiz a x n), entonces

T(0)   = 1
T(n+1) = 2*T(n)

    Nota: Las ecuaciones de coste se pueden resolver con Wolfram Alpha.

5 Demostración de que raiz ∈ O(2ⁿ) (es decir, es de coste exponencial)

    Basta demostrar que para la función raiz, T(n) = 2ⁿ.
    Se demuestra por inducción.
    Caso base:

T(0) = 1 = 2^0

    Caso inductivo:
        Suponemos la hipótesis de inducción: T(n) = 2ⁿ
        Hay que demostrar que T(n+1) = 2^(n+1).
        Demostración

T(n+1) 
= 2*T(n)   [por coste de raiz]
= 2*2ⁿ     [por hip. de inducción]
= 2^(n+1)  [por álgebra]
