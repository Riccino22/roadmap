# 04 — Ventana de contexto

La **memoria de corto plazo** del modelo: cuánto texto puede procesar en una sola llamada, contando input + output.

- GPT-3.5: 16K tokens (~un informe largo)
- Modelos actuales: 200K, 1M, o más (1M ≈ todo el texto de la Biblia en inglés)

Cuando se llena, el modelo empieza a olvidar lo más viejo. Por eso, después de una conversación larga, "se pierde" información que diste al inicio.

Esta limitación es la que motiva muchas otras técnicas:
- [RAG](../12_RAG) — para traer solo lo relevante
- [Memoria de agentes](../18_Memoria_de_Agentes) — para persistir entre sesiones
- [Caching de prompts](../24_Costos_Latencia_y_Caching) — para no repagar el mismo contexto

## Ideas para experimentar

- Llenar la ventana de un modelo y medir cuándo empieza a olvidar.
- Comparar el "lost in the middle" effect: poner una pregunta al inicio, al medio y al final de un contexto largo.
