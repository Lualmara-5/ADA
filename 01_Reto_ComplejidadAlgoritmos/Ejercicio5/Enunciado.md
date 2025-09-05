# 🔁 Ejercicio 5: Números de Lychrel

## 📝 Enunciado
- Un capicúa es un número natural de al menos dos dígitos que se lee igual de izquierda a derecha y de derecha a izquierda.
**Ejemplo:** 363, 1221.

- El proceso consiste en que dado un número `n`:
    - Invertir sus cifras → `rev(n)`.
    - Sumarlo: `n = n + rev(n)`.
    - Repetir hasta obtener un capicúa.

- Si se obtiene un capicúa, la salida es el número de iteraciones necesarias.
- Si `n` ya es capicúa desde el inicio → `0`.
- Si durante el proceso el número llega a un valor `>= 1e10`, se imprime `"L"` para indicar que se sospecha que es un número de Lychrel.

- **Ejemplos**:

`75 → 75+57=132 → 132+231=363` (capicúa en 2 pasos).

`145 → 145+541=686` (capicúa en 1 paso).

- Un **número de Lychrel** sería aquel que nunca llega a un capicúa aplicando este proceso.

👉 No se sabe si existen realmente. El caso más famoso es el **196**, que no se ha demostrado aún si converge.

---
 
## 📤 Entrada
- Varios casos de prueba (≤ 1000).
- Cada caso es un número entero positivo, de al menos 2 dígitos y menor que 10000.
- La entrada termina con un 0, que no es un caso de prueba.

## 📤 Salida
- Para cada caso, imprimir en una línea:
    - El número de iteraciones requeridas para llegar a un capicúa.
    - `"L"` si se supera el límite de `1e10`.

## ✅Ejemplo

### Entrada:
```bash
145
32123
75
196
2584
0
```
### Salida:
```bash
1
0
2
L
L
```

### Explicación:
- `145 → 686` (1 iteración).
- `32123` ya es capicúa (0 iteraciones).
- `75 → 132 → 363` (2 iteraciones).
- `196` crece demasiado → sospechoso (`L`).
- `2584` también crece hasta superar `1e10` → (`L`).
