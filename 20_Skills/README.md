# 20 — Skills

El siguiente nivel de abstracción sobre prompts y RAG.

Una **skill** es **conocimiento procedural reutilizable**: instrucciones + ejemplos sobre **cómo hacer una tarea específica**, que el agente carga **bajo demanda** solo cuando es relevante.

## Diferencias clave

| | [System prompt](../05_System_Prompt) | [RAG](../12_RAG) | **Skill** |
|---|---|---|---|
| Carga | Siempre | Bajo demanda | Bajo demanda |
| Tipo de info | Reglas / rol | Hechos ("qué sé") | Procedimientos ("cómo hacer X") |
| Costo de tokens | Constante | Variable | Variable |

- **RAG es declarativo:** "el cliente X firmó el contrato Y en marzo".
- **Skills son procedurales:** "para refactorizar un componente React, primero hacé esto, después esto".

## Por qué no meter todo en el system prompt

Porque satura el contexto. Si tu agente tiene 50 capacidades, no querés que las 50 instrucciones estén siempre cargadas — querés que el agente **descubra** la skill relevante y la cargue solo cuando va a usarla.

## Cómo se descubren

Típicamente con descripciones cortas que el modelo lee primero (índice de skills), y el contenido completo se carga al invocarla.

## Ejemplos en Claude Code

- `verify` — cómo correr la app y verificar un cambio
- `code-review` — cómo hacer review del diff actual
- `claude-api` — cómo trabajar con el SDK de Anthropic

## Ideas para experimentar

- Escribir 2-3 skills para tu propio agente.
- Comparar agente con todo en el system prompt vs con skills bajo demanda.
