# Practica 2: Guardar los numeros pares

## 1. Descripcion del problema

El programa pide cinco numeros enteros, identifica los pares y los guarda en un arreglo. Puede servir para separar datos que cumplen una condicion en otros proyectos.

## 2. Entradas y salidas

**Entradas:**
1. Cinco numeros enteros escritos por el usuario.

**Salidas:**
1. La cantidad de numeros pares encontrados.
2. Los numeros pares guardados en el arreglo.

## 3. Restricciones e invariante

**Restricciones:**
- Se deben leer exactamente 5 numeros enteros.
- El arreglo debe tener espacio para 5 numeros, porque todos podrian ser pares.

**Tamano del arreglo y por que:**

El arreglo tiene tamano 5 porque en el peor caso los cinco numeros son pares.

**El 0 y los negativos son pares:**

Si. El 0 es par porque es divisible entre 2, y los negativos tambien pueden ser divisibles entre 2; por ejemplo, -4 % 2 es 0.

**Invariante:**

Despues de cada vuelta, `totalPares` indica cuantas posiciones iniciales del arreglo estan ocupadas y tambien la siguiente posicion libre.

## 4. Casos resueltos a mano

| Caso | Numeros | Pares guardados | Posicion de cada par |
|---|---|---|---|
| 1 | 3, 8, 5, 2, 7 | 8, 2 | 0 y 1 |
| 2 | 1, 2, 3, 4, 5 | 2, 4 | 0 y 1 |
| 3 | 0, -3, -4, 7, 1 | 0, -4 | 0 y 1 |

## 5. Receta en pseudocodigo

La receta completa esta en `RECETA.md`.

**Probe mi receta a mano con un caso:** Si

**Tuve que corregirla:** Si, corregi la posicion donde se guardan los pares y el incremento de los contadores.

## 6. Como compilar y ejecutar

```bash
g++ -Wall -Wextra -std=c++17 main.cpp -o numeros_pares
./numeros_pares
```

## 7. Ejemplo de ejecucion

Para `3, 8, 5, 2, 7`, el programa muestra:

```text
Pares encontrados: 2
8 2
```

## 8. Experimentos

**Experimento A:** Las posiciones vacias muestran valores no confiables porque no fueron inicializadas. Por eso despues se debe recorrer solo hasta `totalPares`.

**Experimento B:** Se guardaron los pares en posiciones incorrectas o quedaron posiciones intermedias vacias, porque la vuelta del ciclo no indica cuantas posiciones del arreglo ya estan ocupadas.

## 9. Tabla de pruebas

| Caso | Numeros | Esperado | Obtenido | Paso |
|---|---|---|---|---|
| Mezcla | 1, 2, 3, 4, 5 | 2 pares: 2, 4 | 2 pares: 2, 4 | Si |
| Posiciones distintas | 3, 8, 5, 2, 7 | 2 pares: 8, 2 | 2 pares: 8, 2 | Si |
| Todos pares | 2, 4, 6, 8, 10 | 5 pares | 5 pares: 2, 4, 6, 8, 10 | Si |
| Todos impares | 1, 3, 5, 7, 9 | 0 pares | 0 pares | Si |
| Con cero y negativos | 0, -3, -4, 7, 1 | 2 pares: 0, -4 | 2 pares: 0, -4 | Si |
| Entrada invalida | `hola` o `3.5` | vuelve a pedir | muestra mensaje y vuelve a pedir | Si |
| Caso propio 1 | -2, 11, 12, 13, 14 | 3 pares: -2, 12, 14 | 3 pares: -2, 12, 14 | Si |
| Caso propio 2 | 6, 7, 0, -5, -8 | 3 pares: 6, 0, -8 | 3 pares: 6, 0, -8 | Si |

## 10. Bitacora de mejoras

| # | Que fallo o que quise mejorar | Que cambie | Funciono |
|---|---|---|---|
| 1 | La receta tenia pasos incompletos. | Complete los valores iniciales, la condicion y los incrementos. | Si |
| 2 | Faltaba recorrer solo los pares guardados. | Use `totalPares` como limite del segundo ciclo. | Si |

**Reto elegido:** No elegi un reto opcional.

## 11. Dudas para el profesor

| Duda | Lo que ya intente |
|---|---|
| No tengo dudas pendientes. | Revise la receta, compile y probe los casos de la tabla. |

## 12. Reflexion final

**Que aprendi:** Aprendi a redactar una receta y a usar un contador separado para guardar los pares.

**Que cambiaria de mi proceso:** Hubiera puesto mas atencion en clase y preguntado antes cuando no entendia.

**Lo mas dificil y como lo resolvi:** Lo mas dificil fue redactar la receta. Lo resolvi investigando, preguntando y probandola a mano.

**Pregunta sin responder:** Ninguna.

**Por que no puedo usar la variable del ciclo para guardar en el arreglo:** Porque el ciclo cuenta numeros revisados, pero `totalPares` cuenta las posiciones ocupadas por pares. Son cantidades diferentes cuando aparecen impares.

## 13. Lista de verificacion antes de entregar

- [x] Complete todas las secciones y no quedan campos pendientes.
- [x] El programa compila sin advertencias.
- [x] Probe todos los casos de la tabla.
- [x] Hice los Experimentos A y B y deje el codigo correcto al terminar.
- [x] No modifique `utilerias.h`.
- [x] Hice al menos 3 commits con mensajes claros.
- [ ] Hice `git push` y verifique mi fork en GitHub.
- [ ] Entregue el enlace de mi fork en Classroom.
