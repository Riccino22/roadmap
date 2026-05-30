# 02 — Parámetros

Cuando vemos nombres tipo `Llama-3-70B` o `Qwen2.5-7B`, esos números son los **parámetros**: los pesos internos que el modelo aprendió durante el entrenamiento. La "B" es por *billion* (miles de millones).

Más parámetros suele significar más capacidad, pero también más costo y más latencia. Hoy, modelos chicos bien entrenados (Llama 3 8B, Qwen 2.5 7B, Haiku) pueden superar a modelos grandes más viejos.

## Tradeoffs

| Aspecto | Modelo chico | Modelo grande |
|---|---|---|
| Costo por token | Bajo | Alto |
| Latencia | Baja | Alta |
| Capacidad de razonamiento | Limitada | Mejor |
| Hardware para correr local | Laptop | Datacenter |

## Ideas para experimentar

- Correr una misma tarea con un modelo 7B y uno 70B, medir diferencia de calidad y costo.
- Probar Haiku vs Sonnet vs Opus en la misma tarea.
