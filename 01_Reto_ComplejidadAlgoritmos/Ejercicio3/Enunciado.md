# 📘 Ejercicio 3: Números de Bernouilli

## 📝 Enunciado
Uno de los usos de los números de Bernouilli es el cálculo de la fórmula de Faulhaber, o suma de los (N) primeros números naturales elevados a un valor constante (P):

$1^P$ + $2^P$ + $3^P$ + ... + $N^P$

Dados los valores de (N) y (P) harías un programa para calcular, no el valor de esta suma, sino el valor del residuo entre esa suma y 49999.

¿Por qué ese residuo? Pues porque dependiendo de los valores de (N) y (P) el valor de la suma puede ser un número muy grande. Para esto recuerda que el residuo (también conocido como módulo) de la suma es igual al módulo de la suma de los residuos, y lo mismo ocurre con el producto:

(a + b) % k = ((a % k) + (b % k)) % k

(a * b) % k = ((a % k) * (b % k)) % k


---

### 📥 Entrada
-  La primera línea de la entrada contiene la cantidad `C`
 de casos, no más de `10000`.
- Luego siguen `C líneas`, cada una con los valores de `N` y `P` separados entre sí por un espacio en blanco `(1 ≤ N, P ≤ 100)`.

### 📤 Salida
- La salida debe tener `C` líneas, cada una con el resultado correspondiente. 

---

### ✅ Ejemplo
**Entrada:**
```
3
4 3
2 10
100 100
```

**Salida:**
```
100
1025
41924
```
