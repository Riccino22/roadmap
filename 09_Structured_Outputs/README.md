# 09 — Structured outputs

Por default un LLM devuelve **texto libre**, y parsearlo para integrarlo en código es un dolor (regex frágiles, formatos inconsistentes).

**Structured outputs** = forzar al modelo a devolver **JSON válido contra un schema** que vos definís.

Soportado nativamente por:

- OpenAI: `response_format` con JSON Schema o Pydantic / Zod
- Anthropic: tool use con `input_schema`
- Google Gemini: `response_schema`
- Ollama / open source: vía `outlines`, `instructor`, `jsonformer`

Es la base técnica de [tool calling](../13_Tool_Calling): un tool call es básicamente structured output con un schema predefinido.

## Cuándo usarlo

- Cualquier integración programática (`response.fields.something`).
- Extracción de datos (entidades, clasificación).
- Pipelines donde un output alimenta el siguiente paso.

## Ideas para experimentar

- Definir un Pydantic / Zod model y pedirle al LLM datos que lo cumplan.
- Probar el mismo prompt con / sin structured output → comparar consistencia.
