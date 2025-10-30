# 🗺️ El Problema del Pirata Paranóico y las 5 Islas

**Clasificación:** Acertijo de Lógica y Algoritmia (Brain Teaser)
**Objetivo:** Encontrar el oro escondido en una de 5 islas en el menor número de días posible, garantizando el éxito.

---

## 📜 Reglas del Juego

1.  **Islas:** Hay 5 islas en fila (numeradas del 1 al 5).
2.  **Movimiento Propio:** En el día puedes visitar **una** isla.
3.  **Movimiento del Oro (Parker):** Al final de cada día, el pirata Parker mueve el oro exactamente **una isla** adyacente (ej: de la Isla 3 a la 2 o 4).
4.  **Meta:** Diseñar una secuencia de visitas que garantice encontrar el oro sin importar dónde comience.

---

## 🔑 La Clave de la Solución: La Paridad (Par/Impar)

El secreto para garantizar el éxito es entender el movimiento del oro a través de la **paridad** de la isla (si el número de la isla es par o impar).

* **Si el oro está en una isla PAR (2, 4):** Después de 1 movimiento, estará en una isla **IMPAR** (1, 3, 5).
* **Si el oro está en una isla IMPAR (1, 3, 5):** Después de 1 movimiento, estará en una isla **PAR** (2, 4).

Nuestro objetivo es **alinear** nuestra visita con la paridad que el oro está forzado a tener después de varios días.

---

## 🎯 Mi Solución: Estrategia Garantizada en 5 Días

La estrategia más eficiente es utilizar **dobles visitas consecutivas** para forzar un alineamiento rápido.

| Día | Mi Visita | Paridad de la Isla | Razón Clave |
| :---: | :---: | :---: | :--- |
| **1** | **Isla 2** | PAR | Empezamos en una isla par. Si el oro estaba en I1, I2, o I3, puede que lo encontremos. |
| **2** | **Isla 2** | PAR | **¡Repetimos!** Si el oro no estaba en I2 el día 1, ahora es muy probable que haya regresado a una isla par. Al no encontrarlo en estos dos días, eliminamos muchas posibilidades iniciales. |
| **3** | **Isla 3** | IMPAR | Hacemos un barrido central. El oro, después de 3 movimientos, debe estar en una isla de paridad opuesta a la de su inicio. |
| **4** | **Isla 4** | PAR | Cubrimos la otra isla par principal. |
| **5** | **Isla 4** | PAR | **¡Repetimos!** El oro está forzado a estar en un número limitado de posiciones (generalmente I3 o I4). Al visitar I4 por segunda vez, garantizamos encontrarlo si se movió correctamente. |

### 🎉 ¡El Éxito en 5 Días!

La repetición de las visitas en la Isla 2 (Días 1 y 2) y en la Isla 4 (Días 4 y 5) es lo que garantiza el éxito. Al visitar la misma isla dos veces seguidas, compensamos los dos posibles movimientos del pirata, asegurándonos de que si el oro se mueve "hacia nosotros" o "lejos de nosotros", la segunda visita lo encuentre o lo fuerce a una posición conocida.

---

## 💡 Ejercicio para Recordar el Procedimiento

Para estudiar esto en el futuro, no intentes memorizar la secuencia. En su lugar, recuerda estos dos pasos:

1.  **Identifica la Paridad:** El oro alterna su paridad (Par → Impar → Par → Impar...).
2.  **Usa Doble Búsqueda:** Aplica la estrategia de **visitar la misma isla dos días seguidos** para **eliminar dos posibilidades de inicio** al mismo tiempo y acortar la búsqueda. La secuencia **2, 2** es crítica.