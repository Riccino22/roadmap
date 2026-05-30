# 13 — Tool calling

También llamado **function calling**. Hasta acá los LLMs solo responden texto. Tool calling es cómo hacemos que **hagan cosas**.

## Cómo funciona

1. Le declarás al modelo qué tools tiene disponibles, con su `name`, `description` y `input_schema` (JSON Schema).
2. Cuando el modelo decide que necesita una tool, devuelve un **JSON estructurado** diciendo "quiero llamar a `X` con estos parámetros".
3. **El modelo NO ejecuta la tool.** Vos ejecutás la función y le devolvés el resultado.
4. El modelo sigue con esa info en el contexto.

```
User: "¿Qué tiempo hace en Buenos Aires?"
Model: tool_call(get_weather, {"city": "Buenos Aires"})
You: ejecutás get_weather → "22°C, soleado"
Model: "En Buenos Aires hay 22°C y está soleado."
```

## Caso especial: code execution

Le das al modelo una tool que **ejecuta código** (Python, JS) en un sandbox. Así puede:

- Hacer cálculos exactos (los LLMs son malos con aritmética)
- Generar gráficos
- Procesar archivos
- Hacer pequeñas transformaciones de datos

Es lo que hace ChatGPT cuando "analiza datos" o Claude con su tool `code_execution`.

## Ideas para experimentar

- Implementar 2-3 tools (get_weather, search_web, calculator) y armar un mini-agente.
- Probar el mismo problema con / sin code execution.
- Ver cómo el modelo decide cuándo usar una tool y cuándo no.
