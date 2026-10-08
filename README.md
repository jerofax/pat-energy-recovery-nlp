<p align="center">
  <img src="assets/banner.svg" alt="Esquema sin datos: la curva de la red y, una tras otra, curvas H-Q rojas de una bomba como turbina a distintas velocidades; se marca su punto de operación" width="100%">
</p>

<h1 align="center">Recuperación de energía con bombas como turbinas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/estado-en%20desarrollo-e5383b" alt="Estado: en desarrollo">
  <img src="https://img.shields.io/badge/fase-formulaci%C3%B3n-8c959f" alt="Fase: formulación">
  <img src="https://img.shields.io/badge/python-numpy%20%C2%B7%20scipy%20%C2%B7%20matplotlib-1f2328" alt="Python: numpy, scipy, matplotlib">
  <img src="https://img.shields.io/badge/licencia-MIT-1f2328" alt="Licencia MIT">
</p>

En una red de distribución de agua, las válvulas reductoras de presión (PRV) controlan la presión **disipando** energía. Este proyecto estudia qué pasa si en lugar de la válvula se instala una **bomba operando como turbina (PAT)** y plantea su operación como un **problema de programación no lineal**: decidir, instante a instante, cómo regular la máquina para recuperar la mayor cantidad de energía posible sin dejar de cumplir las condiciones de presión de la red.

Es mi proyecto individual del curso de posgrado de **Programación no Lineal**.

---

## Estado

> **En desarrollo, fase de formulación.** Todavía no hay solución numérica ni resultados propios. Este README se irá actualizando con cada entrega.

| Entrega | Contenido | Fecha | Estado |
|---|---|---|---|
| 1 | Planteamiento y formulación del modelo (sin solución numérica) | [COMPLETAR] | En curso |
| 2 | [COMPLETAR] | [COMPLETAR] | Pendiente |
| 3 | [COMPLETAR] | [COMPLETAR] | Pendiente |

## La idea

El punto de partida es el trabajo de **Manservigi et al. (2025)**. Allí se estudia una red real del norte de Italia y una flota de 16 PATs con curvas características experimentales, y se comparan dos estrategias de regulación:

- **Regulación hidráulica**: la PAT gira a velocidad fija; una válvula en serie estrangula el exceso de carga (*throttle*) y una línea de bypass desvía el exceso de caudal (*bypass*).
- **Regulación eléctrica**: un inversor ajusta la velocidad de rotación de la PAT para seguir el punto de operación de la red.

Según el paper, la **PAT #12** resulta la máquina óptima para esa red con ambas estrategias, y la regulación hidráulica recupera hasta el 44,1 % de la energía hidráulica disponible frente a un máximo de 16,5 % con la eléctrica. Los autores mencionan **estrategias de regulación adicionales (por ejemplo, la híbrida)** como trabajo futuro. *Estas cifras son resultados del paper, no de este repositorio.*

Lo que hago aquí:

1. **Modelo continuo** sobre el caso del paper (PAT #12): en cada instante, las variables de decisión son la **velocidad de rotación**, el **caudal desviado** por el bypass y la **carga estrangulada**. Se maximiza la energía recuperada sujeto a las curvas de la máquina (leyes de afinidad) y a las condiciones de la red.
2. **Regulación híbrida**: combinar en un mismo modelo la regulación por velocidad con el estrangulamiento y el bypass, que es la estrategia que el paper deja abierta.
3. **En exploración, versión de dos niveles**: un nivel de **diseño** (qué máquina y con qué parámetros) y un nivel de **regulación** (cómo operarla en cada instante). Esta parte todavía no está definida.

La no linealidad aparece, entre otras cosas, en las leyes de afinidad (la potencia escala con el cubo de la velocidad) y en las curvas características H–Q y P–Q de la máquina.

### Aplicación objetivo (aspiracional)

Me gustaría hacer el mismo análisis para las PATs de **EPM** en **El Dorado** y **La Estrella**. **Hoy no tengo datos de EPM**, así que esto es solo un objetivo a futuro y no forma parte de los resultados del proyecto.

## Estructura del repositorio

```text
pat-energy-recovery-nlp/
├── docs/
│   ├── formulacion.md        # plantilla del modelo (sigue el enunciado de la entrega 1)
│   └── entregas/
│       ├── entrega-1/        # planteamiento y formulación
│       ├── entrega-2/
│       └── entrega-3/
├── src/                      # código del modelo y de los solvers
├── notebooks/                # experimentos y figuras
├── data/                     # vacío: los datos son bajo solicitud (ver data/README.md)
├── references/
│   └── referencias.bib
├── assets/banner.svg
├── requirements.txt
└── LICENSE
```

## Cómo reproducirlo

Todavía no hay código ejecutable. Cuando lo haya, la idea es:

```bash
git clone https://github.com/jerofax/pat-energy-recovery-nlp.git
cd pat-energy-recovery-nlp
python -m venv .venv
source .venv/bin/activate   # en Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Los datos de la red **no están en el repositorio** (ver [`data/README.md`](data/README.md)).

## Referencias

- Manservigi, L., Marsili, V., Mazzoni, F., Castorino, G. A. M., Farsoni, S., Losi, E., Alvisi, S., Bonfè, M., Franchini, M., Spina, P. R. y Venturini, M. (2025). *Hydraulic and electrical regulations of pumps as turbines for energy recovery in water distribution networks: Energy and economic analysis*. **Cambridge Prisms: Water**, 3, e7. [doi:10.1017/wat.2025.10004](https://doi.org/10.1017/wat.2025.10004). Acceso abierto, CC BY-NC 4.0.
- Nocedal, J. y Wright, S. J. (2006). *Numerical Optimization* (2.ª ed.). Springer. [doi:10.1007/978-0-387-40065-5](https://doi.org/10.1007/978-0-387-40065-5).
- [COMPLETAR: resto de la revisión de literatura]

Las referencias están en formato BibTeX en [`references/referencias.bib`](references/referencias.bib). En el repositorio no hay PDFs de artículos ni de libros, solo las citas y los enlaces.

## Licencia

El código y los documentos propios están bajo licencia [MIT](LICENSE). El paper base tiene su propia licencia (CC BY-NC 4.0) y se cita, no se redistribuye.

---

<p align="center">Hecho por <a href="https://github.com/jerofax">Jerónimo Restrepo</a> · <a href="https://jerofax.github.io">jerofax.github.io</a></p>
