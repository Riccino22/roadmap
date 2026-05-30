# 15 — Agentes (workflow vs agent)

Un **agente** es un LLM en un **loop** con acceso a [tools](../13_Tool_Calling) y un **objetivo**.

```
while not done:
    response = llm.call(context, tools)
    if response.tool_calls:
        result = execute(response.tool_calls)
        context.append(result)
    else:
        done = True
```

El LLM decide qué hacer → ejecuta una tool → observa el resultado → decide el próximo paso. Eso es todo.

## Workflow vs Agent

Distinción clave del post ["Building Effective Agents" (Anthropic)](https://www.anthropic.com/research/building-effective-agents):

| | **Workflow** | **Agent** |
|---|---|---|
| Quién decide los pasos | Vos, en código | El LLM |
| Predictibilidad | Alta | Baja |
| Flexibilidad | Limitada | Alta |
| Costo | Bajo | Alto |
| Debugging | Fácil | Difícil |
| Cuándo usar | Tareas conocidas y estructuradas | Tareas abiertas que requieren decisión |

## Regla práctica

**Empezá siempre con workflow.** Andate a agente solo si la tarea **realmente** lo necesita. La mayoría de los "agentes" en producción son workflows con LLMs en pasos específicos.

## Ideas para experimentar

- Implementar el mismo problema como workflow y como agente, comparar costo / latencia / calidad.
- Armar un agente ReAct mínimo a mano (sin frameworks) en ~50 líneas.

## Recursos

- [Building Effective Agents — Anthropic](https://www.anthropic.com/research/building-effective-agents)
