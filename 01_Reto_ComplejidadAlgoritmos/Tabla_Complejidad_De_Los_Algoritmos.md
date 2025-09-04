# Tabla de Complejidades de Algoritmos ⚡

En Análisis y Diseño de Algoritmos (ADA) es clave entender cómo **crece el tiempo de ejecución** a medida que aumenta la entrada (`N`).  
Estas son las complejidades más comunes, ordenadas de **más rápida a más lenta**.

---

## 📊 Complejidades Comunes

| Notación | Nombre | Descripción | Ejemplo típico |
|----------|--------|-------------|----------------|
| **O(1)** | Constante | Siempre tarda lo mismo, sin importar `N`. | Acceder a un elemento de un array por índice |
| **O(log N)** | Logarítmica | Crece muy despacio aunque `N` sea grande. | Búsqueda binaria |
| **O(N)** | Lineal | Tiempo proporcional a la cantidad de datos. | Recorrer una lista completa |
| **O(N log N)** | Casi Lineal | Un poco más que lineal, pero mucho más eficiente que cuadrática. | Quicksort, Mergesort |
| **O(N²)** | Cuadrática | Crece rápido, cada elemento se compara con todos. | Doble bucle anidado |
| **O(N³)** | Cúbica | Aún más costosa que cuadrática. | Multiplicar matrices naive |
| **O(2^N)** | Exponencial | Imposible de manejar con `N` grandes. | Algoritmos de fuerza bruta (subset sum, backtracking) |
| **O(N!)** | Factorial | La más costosa, crece brutalmente rápido. | Generar todas las permutaciones |

---

## ⚖️ Resumen visual

- 🚀 **O(1), O(log N)** → ideales, muy eficientes.  
- 🙂 **O(N), O(N log N)** → aceptables en la práctica.  
- ⚠️ **O(N²), O(N³)** → solo sirven para `N` pequeños.  
- ❌ **O(2^N), O(N!)** → impracticables para `N` moderados.  

---

## 🎯 Tip
En concursos o problemas tipo ADA, **siempre intenta reducir** la complejidad hacia **O(N log N)** o menor.  
Un algoritmo O(N²) puede funcionar con `N = 1000`, pero fracasar con `N = 10^5`.  
