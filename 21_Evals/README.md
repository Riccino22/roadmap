# 21 — Evals

**Probablemente el concepto más subestimado de todos.**

Sin evals:
- No sabés si tu agente funciona.
- No sabés si una "mejora" es realmente una mejora o estás rompiendo cosas en otro lado.
- No podés iterar con confianza.

Los evals son **tests, pero adaptados al hecho de que los LLMs son [no-determinísticos](../06_Determinismo_y_Temperatura)**.

## Tipos de evals

- **Asserciones duras** — el output incluye este string / pasa este schema.
- **LLM-as-judge** — otro LLM evalúa si el output cumple criterios subjetivos.
- **Human evals** — humanos puntúan outputs (caro pero gold standard).
- **A/B comparison** — dado output A y B, ¿cuál es mejor?
- **Métricas específicas de tarea** — F1 para clasificación, BLEU para traducción, pass@k para código.

## Set de evals

Necesitás:
- Un **dataset** representativo de los inputs reales.
- **Criterios** claros (rubric) de qué es éxito.
- Un **runner** que ejecute y reporte métricas.
- Idealmente, integración con CI para detectar regresiones.

## Frameworks

- `promptfoo`, `braintrust`, `langsmith`, `inspect-ai`, `deepeval`

## La regla

> Toda app seria con LLMs en producción necesita evals. Los descubrís tarde y duele.

## Ideas para experimentar

- Armar un set de 20 inputs + outputs esperados para una tarea simple.
- Implementar LLM-as-judge para una tarea subjetiva (calidad de escritura).
- Medir si cambiar de modelo realmente mejora algo en tu caso.
