# 📐 Ejercicio 5: Secuencia NuNuDoN

Se define la siguiente secuencia **NuNuDoN** (*N plus Number of Divisors of N*):  

![Secuencia NuNuDoN](./Img/Secuencia_NuNuDoN.png)

Por lo que los primeros seis términos de dicha secuencia serían: `1, 2, 4, 7, 9, 12`.

El problema entonces es, dados dos valores enteros (A) y (B) ((A < B)), encontrar la cantidad de números de dicha secuencia que se encuentran dentro del rango ([A, B]).

---

## 📤 Input
- La primera línea contiene un entero `N` → número de casos de prueba (≤ 100).
- Cada una de las siguientes `N` líneas contiene dos enteros `A` y `B` (1 ≤ A < B ≤ 100000).

---

## 📥 Output
Para cada caso de prueba, imprimir en una línea la cantidad de números de la secuencia que se encuentran dentro del rango `[A, B]`.

---

## 🧩 Ejemplo

### Input
```bash
3
1 12
1 100
65 70
```

### Output
```bash
6
20
0
```

---

## 🔑 Explicación del ejemplo

- `[1, 12]` → en ese rango están los 6 primeros términos de la secuencia: `1, 2, 4, 7, 9, 12`.
- `[1, 100]` → en ese rango aparecen los primeros 20 términos.
- `[65, 70]` → no hay términos de la secuencia en ese intervalo → resultado = `0`.

---

## 💡 Idea de la solución

- La secuencia se construye de **manera acumulativa**:
    - Se parte de 𝑁_0=1
    - Cada nuevo término se obtiene sumando al anterior la **cantidad de divisores** que tiene.

- Como B ≤ 100000, basta con **precomputar la secuencia una vez hasta superar 100000**.
- Luego, para cada consulta [A, B]:
    - Contar cuántos términos precalculados caen dentro del rango.

De esta forma, se evita recomputar la secuencia en cada caso de prueba, lo que asegura eficiencia.

---

