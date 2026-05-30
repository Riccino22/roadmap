# 16 — Arquitecturas de agentes

## ReAct (Reasoning + Acting)

Paper original: Yao et al. 2022. El patrón **base** de casi todos los agentes modernos. El agente alterna:

- **Thought** — pienso qué hacer
- **Action** — invoco una tool
- **Observation** — observo el resultado

Loop hasta cumplir el objetivo.

```
Thought: necesito buscar el clima de Buenos Aires
Action: search("clima Buenos Aires")
Observation: "22°C, soleado"
Thought: ya tengo la respuesta
Final answer: "En Buenos Aires hay 22°C y está soleado."
```

## Reflexion

Agrega **autocrítica**: el agente evalúa su propio output, identifica errores, y vuelve a intentar con ese feedback en el contexto. Útil para tareas donde la primera respuesta suele ser mejorable (código, escritura).

## Human-in-the-loop (HITL)

El agente **pausa en pasos críticos** y le pide aprobación a un humano antes de seguir. Útil para:

- Acciones irreversibles (enviar emails, borrar archivos, hacer pagos)
- Costos altos
- Decisiones con impacto regulatorio / legal

## Ideas para experimentar

- Implementar un agente ReAct sin frameworks.
- Agregar una capa de Reflexion y comparar calidad.
- Diseñar HITL para una tool "enviar email": el agente prepara, el humano confirma.
