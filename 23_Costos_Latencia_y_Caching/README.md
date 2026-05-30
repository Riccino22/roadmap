# 23 — Costos, latencia y caching de prompts

Restricciones **reales** de diseño que no aparecen en los tutoriales pero matan productos.

## Costos

Un agente que itera 10 veces por consulta puede ser técnicamente hermoso y económicamente inviable.

- Cobran por **input tokens** y por **output tokens** (precios distintos).
- Modelos de [reasoning](../11_Modelos_de_Reasoning) cobran también por **thinking tokens**.
- Cada tool call agrega contexto que se cobra en cada iteración.

**Tip:** mediar costo por interacción antes de escalar.

## Latencia

Cada llamada al LLM tarda **segundos**. Los usuarios no esperan.

Acumuladores típicos:
- N iteraciones del agente
- Modelos de reasoning (pueden tardar minutos)
- Tools lentas (web search, base de datos)

Estrategias:
- **Streaming** para mostrar respuesta mientras se genera.
- **Modelos chicos** para sub-tareas simples ([routing](../17_Patrones_de_Orquestacion)).
- **Paralelización** cuando hay sub-tareas independientes.
- **Caching** (abajo).

## Prompt caching

Cachear el **prefijo común** de tus prompts (system prompt largo, documentos de contexto, definiciones de tools) para no repagar y recomputar en cada llamada.

Soportado por Anthropic, OpenAI, Gemini. Bien usado: **baja costos hasta 90% y reduce latencia significativamente**.

Cómo funciona en Anthropic: marcás `cache_control` en bloques del prompt, los siguientes 5 minutos esos tokens se cobran ~10% y se sirven más rápido.

### Reglas para cachear bien

- Poné lo **estable** al principio del prompt (lo cacheable).
- Poné lo **variable** al final (la query del usuario).
- Cacheá tools y system prompts largos.

## Ideas para experimentar

- Medir cost / latency de un agente real, identificar el peor offender.
- Implementar prompt caching y medir la mejora.
- Comparar streaming vs no-streaming en UX.
