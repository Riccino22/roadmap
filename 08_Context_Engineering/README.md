# 08 — Context engineering

Un paso más allá del prompt engineering: **diseñar todo lo que el modelo ve** en su ventana de contexto, no solo el prompt del usuario.

El contexto incluye:

- [System prompt](../05_System_Prompt) (rol, reglas, formato)
- Historial de la conversación
- Documentos recuperados vía [RAG](../12_RAG)
- Definiciones de [tools](../13_Tool_Calling) disponibles
- Resultados de tool calls previos
- [Skills](../20_Skills) cargadas bajo demanda
- Few-shot examples

**Cambio de paradigma:** antes pensábamos "cómo escribo el prompt". Ahora pensamos **"cómo armo todo el contexto"**.

## SDD — Spec-Driven Development

Aplicación concreta: en vez de escribir código directamente, escribís una **especificación detallada** (capacidades, user stories, diagramas, edge cases) que sirve de input para agentes de coding (Claude Code, Cursor, Codex). El contexto bien armado es lo que hace que el agente genere algo cercano a lo que querés.

## Ideas para experimentar

- Tomar una tarea, armar el contexto "mínimo" vs el "rico" → comparar output.
- Hacer SDD: escribir un spec, dárselo a Claude Code, ver qué pasa.
