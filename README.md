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
![alt text](https://www.cs.us.es/~jalonso/cursos/i1m/temas/tema-28/fig/ordenes.png)

# Complejidad Logaritmica

# Complejidad Exponencial

