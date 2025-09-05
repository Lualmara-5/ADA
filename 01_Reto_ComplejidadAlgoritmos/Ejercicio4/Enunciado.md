# 🧮 Ejercicio 4: Números de Kaprekar

---

## 📖 Enunciado

Un número **Kaprekar** es un entero positivo mayor a 3 que cumple la siguiente propiedad:

1. Se eleva al cuadrado.

2. Se separa el resultado en dos partes (izquierda y derecha).

3. La **suma de ambas partes** es igual al número original.

### ⚡ Ejemplos:

- (9² = 81) → (8 + 1 = 9) ✅ (Kaprekar)
- (2728² = 7441984) → (744 + 1984 = 2728) ✅ (Kaprekar)
- (4879² = 23804641) → (238 + 04641 = 4879) ✅ (Kaprekar)
- (100² = 10000) → (100 + 00 = 100) ❌ (NO Kaprekar)

⚠️ La segunda parte nunca puede ser nula, pero puede empezar en ceros.

---
 
## 📤 Entrada
- La primera línea contiene un entero `C` → cantidad de casos (≤ 20000).
- Luego siguen `C` líneas, cada una con un número entero positivo `< 1e6`.

## 📤 Salida
- Para cada caso imprimir una línea:
    - `"KAP"` si el número es Kaprekar.
    - `"NO"` en caso contrario.

## ✅Ejemplo

### Entrada:
```bash
3
2728
100
4879
```
### Salida:
```bash
KAP
NO
KAP
```

---
