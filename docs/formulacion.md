# Formulación del modelo

> Plantilla de trabajo para la **entrega 1** (planteamiento y formulación, sin solución numérica). Las secciones siguen el enunciado del curso. Todo lo marcado con [COMPLETAR] lo escribo yo.

**Título del proyecto:** [COMPLETAR]
**Estudiante:** Jerónimo Restrepo Ramírez
**Curso:** Programación no Lineal (posgrado)

---

## 1. Descripción del problema

- ¿Cuál es el problema y en qué contexto se presenta? [COMPLETAR]
- ¿Por qué es importante resolverlo? [COMPLETAR]
- ¿Qué decisiones se deben tomar? [COMPLETAR]
- ¿Qué se pretende optimizar? [COMPLETAR]

## 2. Revisión de literatura

Cómo se ha abordado el problema y qué se toma de cada trabajo.

| Fuente | Qué aporta a la formulación |
|---|---|
| Manservigi et al. (2025) | [COMPLETAR] |
| [COMPLETAR] | [COMPLETAR] |

## 3. Clasificación del problema

Justificar matemáticamente cada punto.

- Minimización o maximización: [COMPLETAR]
- Con o sin restricciones: [COMPLETAR]
- Continuo, entero, binario o mixto: [COMPLETAR]
- Programación no lineal (dónde está la no linealidad): [COMPLETAR]
- Convexo o no convexo: [COMPLETAR]
- Una o varias restricciones no lineales: [COMPLETAR]

## 4. Variables de decisión

| Símbolo | Significado | Unidad | Dominio y cotas | Interpretación |
|---|---|---|---|---|
| [COMPLETAR] | Velocidad de rotación de la PAT | [COMPLETAR] | [COMPLETAR] | [COMPLETAR] |
| [COMPLETAR] | Caudal desviado por el bypass | [COMPLETAR] | [COMPLETAR] | [COMPLETAR] |
| [COMPLETAR] | Carga estrangulada por la válvula | [COMPLETAR] | [COMPLETAR] | [COMPLETAR] |

## 5. Parámetros del modelo

| Símbolo | Significado | Unidad | Valor | Fuente |
|---|---|---|---|---|
| [COMPLETAR] | [COMPLETAR] | [COMPLETAR] | [COMPLETAR] | [COMPLETAR] |

## 6. Función objetivo

$$
\max_{x} \; f(x) = \text{[COMPLETAR]}
$$

Qué representa cada término y por qué es adecuada: [COMPLETAR]

## 7. Restricciones

$$
g_j(x) \le 0, \qquad h_k(x) = 0, \qquad l_i \le x_i \le u_i
$$

| Restricción | Significado en el problema | ¿No lineal? Origen |
|---|---|---|
| [COMPLETAR] | [COMPLETAR] | [COMPLETAR] |

## 8. Modelo matemático completo

[COMPLETAR]

## 9. Conjunto factible

$$
X = \left\{ x : g_j(x) \le 0,\; h_k(x) = 0,\; l_i \le x_i \le u_i \right\}
$$

- Qué representa en el problema real: [COMPLETAR]
- ¿Vacío o no vacío? [COMPLETAR]
- ¿Acotado? [COMPLETAR]
- ¿Convexo? ¿Hay restricciones que generan regiones no convexas? [COMPLETAR]

## 10. Análisis preliminar de propiedades

- Continuidad y diferenciabilidad: [COMPLETAR]
- Convexidad de la función objetivo y del conjunto factible: [COMPLETAR]
- Existencia de óptimos: [COMPLETAR]
- Posibles óptimos locales múltiples: [COMPLETAR]
- Posibles dificultades numéricas: [COMPLETAR]

## 11. Supuestos de modelación

- [COMPLETAR]

## 12. Referencias

Ver [`../references/referencias.bib`](../references/referencias.bib).
