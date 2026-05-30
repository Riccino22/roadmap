# 05 — System prompt

Instrucciones fijas que el sistema pasa al modelo "por debajo" de la conversación con el usuario. Acá se define:

- El **rol** del asistente
- Las **reglas** de comportamiento
- El **formato** esperado de respuesta
- Restricciones, tono, idioma

Importante: el system prompt **también consume tokens** de la ventana de contexto. Cuanto más largo, menos espacio queda para conversación / RAG / tool results.

## Buenas prácticas

- Ser específico, no genérico.
- Dar ejemplos del formato de salida cuando importa.
- Separar reglas duras ("nunca hagas X") de preferencias ("preferí Y").
- Revisar si conviene mover instrucciones a [skills](../20_Skills) cargadas bajo demanda.

## Ideas para experimentar

- Mismo prompt de usuario, distintos system prompts → comparar respuestas.
- Medir cuánto cambia la respuesta con / sin role prompting.
