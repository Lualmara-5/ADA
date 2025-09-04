# 🏠 Problema: Números de Casa

Este readme resuelve el problema **"Números de Casa"**

La idea es encontrar si existe una casa en una calle de `N` casas (numeradas del 1 al N) tal que la **suma de las casas a su izquierda** sea igual a la **suma de las casas a su derecha**.  

| Casas izquierda | <div align="center">Casa candidata</div> | Casas derecha |
|-----------------|:---------------------------------------:|---------------|
| <div align="center">1 + 2 + 3 + 4 + 5 = **15**</div> | <div align="center">6</div> | <div align="center">7 + 8 = **15** </div> |

---

## 📜 Enunciado resumido
- La calle tiene `N` casas numeradas consecutivamente desde `1` hasta `N`.  
- Se busca una casa `i` tal que: `suma(1...i-1) == suma(i+1...N)`
- Si existe, se imprime el número de la casa.  
- Si no existe, se imprime `"NO"`.  
- El input comienza con `C`, el número de casos de prueba, seguido de `C` valores de `N`.  

Input:
```
3
8
5
9800
```

Output:
```
6
NO
6930
```

---

## 💡 Idea de la solución
La suma total de todas las casas de `1` a `N` es: `S = N * (N + 1) / 2`

Si existe una casa `i` que equilibre las sumas, entonces: `suma(izquierda) = suma(derecha)`

Lo cual se puede demostrar que ocurre **si y solo si** `S` es un número cuadrado perfecto.  
En ese caso, la casa candidata es: `i = sqrt(S)`

Por eso la solución se basa en:
1. Calcular la suma total `S`.  
2. Sacar la raíz cuadrada de `S`.  
3. Revisar si la raíz es un número entero y `<= N`.  
4. Devolver `i` si cumple la condición, o `"NO"` en caso contrario.  

---

## 💻 Código en Python
```python
import math

C = int(input()) 
resultados = []

for _ in range(C):
    N = int(input())
    Casa = math.sqrt((N * N + N) / 2)

    if Casa.is_integer() and Casa <= N:   
        resultados.append(str(int(Casa)))
    else:
        resultados.append("NO")

print("\n".join(resultados))
```

---

## ⚡ Complejidad
- Cada caso se resuelve en O(1), ya que solo se hacen operaciones aritméticas y una raíz cuadrada.
- Para C casos, la complejidad total es O(C).

## 📌 Nota
Este código es una de las posibles soluciones.

Existen muchas formas de resolver el problema (por ejemplo usando math.isqrt para trabajar siempre con enteros y evitar flotantes)
