# ⏰ Ejercicio 4: Fabricación de relojes
En los relojes analógicos a veces el número 4 se escribe como `IIII` en lugar de `IV`.
Con eso, un reloj necesita exactamente:

- 20 símbolos `I`
- 4 símbolos `V`
- 4 símbolos `X`.

Para fabricarlos se usa un molde, que genera varios símbolos de una sola vez.
Por ejemplo, con un molde que produce `5 I`, `1 V`, `1 X`, se pueden fabricar todos los símbolos repitiendo el molde 4 veces sin desperdicio → tamaño del molde = 7.

El problema general es:
Dadas las cantidades necesarias de tres símbolos (`a, b, c`), determinar **el molde más pequeño posible (suma de símbolos en él)** que permita construir un reloj sin desperdiciar ninguno.

---

## 📤 Input
- La primera línea contiene un entero `N` → número de casos de prueba (≤ 1000).
- Cada una de las siguientes `N` líneas contiene tres enteros positivos `a, b, c` (≤ 1e10), que representan la cantidad requerida de cada símbolo.

## 📤 Output
Para cada caso, imprimir en una línea el tamaño del molde más pequeño posible.

---

## 🧩 Ejemplo

### Input
```bash
4
20 4 4
12 12 12
7 6 5
35 10 15
```

### Output
```bash
7
3
18
12
```

---

## 🔑 Explicación De Ejemplo

- `20, 4, 4` -> `mcd = 4` -> molde `(5,1,1)` -> tamaño = 7.
- `12, 12, 12` → `mcd = 12` → molde `(1,1,1)` → tamaño = 3.
- `7, 6, 5` → `mcd = 1` → molde `(7,6,5)` → tamaño = 18.
- `35, 10, 15` → `mcd = 5` → molde `(7,2,3)` → tamaño = 12.

---

## 💡 Idea de la solución

El molde más pequeño posible debe tener las **cantidades mínimas proporcionales** de cada símbolo.
- Si se necesitan `a`, `b`, `c` símbolos, el molde debe contener:<br> a/b, b/m, c/m <br> donde `m = gcd(a, b, c) `(máximo común divisor)
- Entonces, el tamaño mínimo del molde es: <br> a/b + b/m + c/m 

---
