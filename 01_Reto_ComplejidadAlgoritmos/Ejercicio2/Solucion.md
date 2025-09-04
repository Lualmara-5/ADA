# 🏙️ Problema: Número de Calle

Este readme resuelve el problema **"Número de Calle"**

La idea es encontrar, en una calle con `M` casas numeradas consecutivamente, **cuántas calles S permiten que la suma de los cuadrados de las calles a la derecha sea múltiplo de la suma de los cuadrados de las calles a la izquierda.**

---

## 📜 Enunciado resumido
- La calle tiene M casas numeradas consecutivamente desde 1 hasta M.
- La programadora vive en la calle S (2 < S < M).
- Se calcula:
  - izquierda = 1^2 + 2^2 + ... + (S-1)^2
  - derecha = (S+1)^2 + ... + M^2
- Se busca contar cuántas calles S cumplen: `derecha % izquierda == 0`
- Entrada: varios valores de M (≤ 500 casos), termina con 0.
- Salida: para cada caso, la cantidad de calles que cumplen la condición.

Input:
```
8
42
55
0
```

Output:
```
1
2
0
```
- Para `M=8`, la calle `3` cumple.
- Para `M=42`, las calles `5` y `14` cumplen.
- Para `M=55`, no hay calles que cumplan.

---

## 💡 Idea de la solución
1. La suma de cuadrados de `1` a `n` se puede calcular con la fórmula: `sum_squares(n) = n * (n + 1) * (2n + 1) / 6`
   
2. Para cada calle candidata `S` (`2 <= S <= M-1`):
   
    - Calcular suma izquierda: sum_squares(S-1)
    - Calcular suma derecha: sum_squares(M) - sum_squares(S)
    - Verificar si derecha % izquierda == 0
      
3. Contar cuántas calles cumplen la propiedad

Esta técnica evita recorrer todas las calles con bucles y permite usar fórmulas directas.

---

## 💻 Código en Python
```python
def suma_cuadrados(n):
    return (n * (n + 1) * (2 * n + 1)) // 6

M = int(input())

while M != 0:
  total = suma_cuadrados(M)
  contador = 0
  
  for S in range (3, M):
    izquierda = suma_cuadrados(S-1)
    derecha = total - izquierda - S*S
    
    if derecha % izquierda == 0:
      contador += 1

  print(contador, "\n")
  M = int(input())
```

---

## ⚡ Complejidad
- Para cada caso de prueba se recorren `M-2` calles.
- Cada cálculo de suma usa fórmula cerrada O(1).
- Total: **O(C * M)** donde `C` es la cantidad de casos y `M` el tamaño máximo de la calle.
