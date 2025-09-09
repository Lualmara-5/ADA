# 🔢 Teorema de los números primos

El **teorema de los números primos** describe la distribución asintótica de los números primos y formaliza la idea intuitiva de que los primos son menos frecuentes conforme los números crecen.

Este resultado fue planteado inicialmente por **Carl Friedrich Gauss** entre 1792 y 1793, luego por **Adrien-Marie Legendre** en 1798, y refinado nuevamente por Gauss años después.

Siendo P(n) la función que cuenta la cantidad de números primos menores o iguales que n, el teorema establece que:

P(n) ∼ ( n / ln(n) )

El error respecto a esta aproximación puede calcularse como:

e = P(n) - ( n / ln(n) )

---

## 📥 Input
- La primera línea contiene la cantidad `C` de casos (no más de 10000).
- Luego siguen `C` líneas cada una con el valor de n tal que: (10 < n < 100000)

## 📤 Output
- La salida debe contener C líneas.
- Cada línea corresponde al error e, redondeado al número entero más cercano.

---

## 🧩 Ejemplo

### Input
```bash
3
20
5000
99999
```
### Output
```bash
1
82
906
```
---

## 🌟 Pistas de solución

1. Para obtener **P(n)** (la cantidad de primos menores o iguales a `n`), una forma eficiente es usar el **algoritmo de la Criba de Eratóstenes**.
   
2. La parte analítica se calcula con la fórmula:  
   ```python
   import math
   aprox = n / math.log(n)
   ```

3. Finalmente, el error se obtiene como:
   ```bash
   error = P[n] - aprox
   ```
   
4. No olvides **redondear al entero más cercano** usando `round(error)`.

---
