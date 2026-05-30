# 22 — Observabilidad

Si [evals](../21_Evals) son los tests **offline** (mido contra un dataset antes de deployar), **observabilidad** es lo que te dice qué está pasando **online**, en producción, con tráfico real.

Sin observabilidad volás a ciegas: no sabés por qué un usuario se quejó, no detectás degradación de calidad cuando cambia el modelo, no sabés dónde se va el dinero ni la latencia.

## Qué se observa en sistemas con LLMs

- **Traces** — el árbol completo de una request: prompt, tool calls, sub-llamadas a otros LLMs, respuesta final.
- **Tokens y costo** — por request, por usuario, por feature.
- **Latencia** — time-to-first-token, latencia total, por step del agente.
- **Tool calls** — cuáles se invocan, con qué argumentos, qué devuelven, errores.
- **Errores** — rate limits, timeouts, structured output que no parsea, tool failures.
- **Calidad** — feedback explícito (thumbs up/down) e implícito (¿el usuario reformuló la pregunta?).
- **Drift** — el comportamiento cambia cuando el proveedor actualiza el modelo, o cuando entra un tipo de input nuevo.

## Diferencia con observabilidad tradicional

Lo distinto vs. APM clásico:
- Los inputs/outputs son **texto largo** (no nombres de endpoints).
- Una request es un **árbol de llamadas LLM**, no una transacción HTTP plana.
- Necesitás guardar el **contenido** para poder debuggear casos puntuales, no solo métricas agregadas.
- Calidad ≠ "200 OK" — un modelo puede responder "exitosamente" basura.

## Herramientas

- **Específicas para LLMs / agentes:** Langfuse, Langsmith, Arize Phoenix, Helicone, Braintrust, OpenLLMetry.
- **APM tradicional con soporte LLM:** Datadog LLM Observability, New Relic AI Monitoring.
- **DIY:** OpenTelemetry + tu backend favorito.

Muchas se integran como decorators / context managers que envuelven las llamadas al SDK del proveedor.

## Relación con otros items

- [Evals](../21_Evals) — los hallazgos en producción se vuelven nuevos test cases para evals.
- [Harness engineering](../19_Harness_Engineering) — la observabilidad **es parte** del harness.
- [Costos y latencia](../24_Costos_Latencia_y_Caching) — sin medir no podés optimizar.

## Ideas para experimentar

- Integrar Langfuse o Phoenix a un agente y ver las traces de una conversación real.
- Loguear cost/tokens por request en un dashboard simple.
- Capturar fallos de structured output y convertirlos en regression tests.
