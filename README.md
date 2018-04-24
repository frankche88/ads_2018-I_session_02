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

# Complejidad Logaritmica

# Complejidad Exponencial

