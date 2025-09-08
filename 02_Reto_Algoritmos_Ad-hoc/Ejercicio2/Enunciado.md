# 🌌 Ejercicio 2: Día del Olimpo

No sé si ya lo sabías, pero los planetas de nuestro sistema solar fueron bautizados por antiguas civilizaciones como una forma de honrar a sus dioses.

Así por ejemplo, los babilonios ya conocían el planeta más cercano al **Sol** como **Nabu**, en honor a su dios de la escritura y el destino, mientras que los antiguos griegos lo llamaban **Stilbon**, y sus descendientes más modernos lo denominaron **Hermes**, en honor al mensajero de los dioses del Olimpo, y por la rapidez con la que se mueve por el cielo (tarda sólo 88 días en dar una vuelta alrededor del sol, viajando a casi 48 kilómetros por segundo, más rápido que cualquier otro planeta). Los romanos le dieron el nombre del dios equivalente en su mitología: **Mercurio**.

Entre tanto, gracias a su brillo característico (debido a su proximidad y la densidad de su atmósfera, es el tercer objeto celeste más brillante en nuestro firmamento después del Sol y la Luna) y su aparición al amanecer, los antiguos romanos asociaron al segundo planeta con **Venus**, la diosa del amor y la belleza, mientras que los griegos lo asociaban con su diosa equivalente, **Afrodita**.

Puedes consultar el origen del resto de nombres en 👉 [astrobitácora](https://www.astrobitacora.com/de-donde-vienen-los-nombres-de-los-planetas/).

---

## 🌠 Contexto del problema
Supongamos que, de manera consistente con este origen *"divino"*, los antiguos griegos denominaron "**el día del Olimpo**", a aquel día en el que todos los planetas se encuentran perfectamente alineados.

Si el día de hoy ocurriera ese fenómeno, y además supiéramos el tiempo exacto en días que tarda la traslación de cada uno, ¿cuántos días faltarían para la siguiente de estas festividades?

Consideremos que:
- En el caso de nuestro sistema solar, podríamos estar interesados no necesariamente en la alineación de los nueve planetas (cosa que probablemente nunca ocurra antes que se acabe el universo), sino de cualquier subconjunto de dos o más planetas.

- Incluso podríamos estar interesados en cualquier otro sistema de un único sol.

---

## 📥 Input
- La primera línea contiene la cantidad `N` de casos (no más de 500).
- Luego siguen `N` líneas.
- Cada línea contiene entre **2 y 5 valores enteros positivos** (no mayores a 5000), separados por espacios, que corresponden al periodo de traslación en días de cada planeta.
- Estos valores no necesariamente están organizados según la distancia al sol.

## 📤 Output
La salida debe tener `N` líneas, cada una con la cantidad de días faltantes para el siguiente **día del Olimpo**.

---

## 🧩 Ejemplo

### Input
```bash
4
20 10 30
88 226 365 687 4332
1000 1000 1000 1000
99 97
```
### Output
```bash
60
900156286920
1000
9603
```

---

## 🌟 Pistas de solución

- Piensa en qué ocurre cuando quieres encontrar el momento en que **dos planetas** se alinean: ese momento es un **múltiplo común** de sus periodos de traslación.  
- Para extenderlo a varios planetas, necesitas calcular un número que sea múltiplo común de todos ellos.  
- El problema entonces se reduce a calcular el **mínimo común múltiplo (MCM)** de los periodos dados.  
- Recuerda que el MCM se puede obtener usando el **máximo común divisor (MCD)**.  
