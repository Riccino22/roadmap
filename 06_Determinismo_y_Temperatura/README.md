# 06 — Determinismo y temperatura

Si el modelo elige el token "más probable", ¿por qué dos llamadas iguales devuelven respuestas distintas?

Porque el modelo no elige el token más probable: calcula una **distribución de probabilidad** sobre todos los tokens posibles y **samplea** uno. La **temperatura** controla qué tan "plana" es esa distribución:

- `temperature = 0` → casi siempre el token más probable (cuasi-determinista)
- `temperature = 0.7` → balance creatividad / coherencia (default típico)
- `temperature = 1.5` → muy creativo, a veces incoherente

## Otros parámetros de sampling

- `top_p` (nucleus sampling): considera solo los tokens cuya probabilidad acumulada llega a `p`.
- `top_k`: considera solo los `k` tokens más probables.
- `seed`: en algunos proveedores ayuda a reproducir resultados, pero no garantiza determinismo total.

**Implicación importante:** los LLMs son no-determinísticos por default. Esto rompe los tests tradicionales → ver [Evals](../21_Evals).

## Ideas para experimentar

- Misma llamada × 10 con `temperature=0` y con `temperature=1` → comparar varianza.
- Tarea creativa (escribir un poema) vs estructurada (extraer JSON) → qué temperatura conviene.
