# 🪖 Ejercico 1: Organización de batallones

Según la crítica, la mejor batalla de *El Señor de los Anillos*, y una probablemente de las mejores del cine en general, es la que tiene lugar a las afueras de la capital de Gondor, *Minas Tirith*.  
En esta batalla, en la que por cierto se presenta el inolvidable enfrentamiento entre **Éowyn y el Rey Brujo de Angmar**, un gigantesco ejército de **200.000 orcos y trolls** siembran el terror entre sus enemigos.

Saurón es muy psico-rígido, por lo que quiere **distribuir ese ejército en batallones de exactamente la misma cantidad de soldados**.  

El asunto es que hay muchas maneras de hacer la distribución:  
- Puede tener **20 batallones de 10.000 cada uno**  
- O **50 batallones de 4.000 cada uno**  
- Entre otras.

Pobre Saurón 😢... dado el tamaño de su ejército (no solo para esta batalla sino para otras), ¿le ayudarías a determinar la **cantidad de formas de distribución exactas**, sabiendo que el tamaño mínimo de un batallón es de un soldado?

---

## 📥 Input
- La primera línea contiene la cantidad **N** de casos (no más de 100).  
- Luego siguen **N** líneas, cada una con un entero positivo **E** correspondiente al tamaño del ejército (**2 ≤ E ≤ 500.000**).

## 📤 Output
La salida debe tener **N líneas**, cada una con la cantidad de distribuciones diferentes posibles.

---

## 🧩 Ejemplo

### Input
```bash
4
200000
25
10000
9887
```
### Output
```bash
42
3
25
2
```
