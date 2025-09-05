# 📘 Problema: Números de Bernouilli

Este readme resuelve el problema **"Números de Bernouilli"**
La idea es calcular la suma de los primeros N números naturales elevados a la potencia P:

S = $1^P$ + $2^P$ + $3^P$ + ... + $N^P$

Como este valor puede ser muy grande, el resultado debe imprimirse como el residuo de dividirlo entre 49999.

---

## 📜 Enunciado resumido
Se recibe un número `C`, que indica la cantidad de casos de prueba.

Cada caso consiste en dos enteros `N` y `P`.
Para cada caso, calcular: `S % 49999`.

**Entrada:**
```
3
4 3     -> Caso 1: N=4, P=3
2 10
100 100
```
**Salida:**
```
100
1025
41924
```

---

## 📌 Ejemplo explicado

Caso 1:

$1^3$ + $2^3$ + $3^3$ + $4^3$ = 100 % 49999 = 100

---

## 💡 Idea de la solución
1. La suma se puede calcular recorriendo cada número `i` desde `1` hasta `N`.
   
2. Para evitar desbordamientos:
    - Usar la función `pow(i, P, 49999)` que calcula `(i^P) % 49999` directamente y de forma eficiente.
    - Ir acumulando en una variable `Residuo`, aplicando el módulo en cada suma.
      
3. Al final, imprimir el valor acumulado `Residuo`.

Esto aplica las propiedades del módulo:
```
(a + b) % k = ((a % k) + (b % k)) % k
(a * b) % k = ((a % k) * (b % k)) % k
```

---

## 💻 Código en Python
```python
Modulo = 49999
Casos = int(input())

for _ in range(Casos):
  N, P = map(int, input().split())

  Residuo = 0

  for i in range(1, N + 1):
        Residuo = (Residuo + pow(i, P, Modulo)) % Modulo

  print(Residuo, "\n")
```

---

## ⚡ Complejidad

- Cada potencia modular se calcula en **O(log P)**.
- Para cada caso se hacen `N` cálculos → **O(N log P)**.
- Para `C` casos, la complejidad total es **O(C * N log P)**.

Este enfoque es lo bastante eficiente gracias al uso de `pow` con módulo
