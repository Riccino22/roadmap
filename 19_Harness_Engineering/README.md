# 19 — Harness engineering

Concepto reciente, popularizado por **Claude Code**.

> La performance de un agente depende **mucho más del entorno** donde opera que del modelo en sí.

El **harness** es el entorno: el conjunto de afordances, restricciones y feedback loops alrededor del LLM.

## Qué entra en el harness

- **Tools** disponibles y sus descripciones
- **Permisos** (qué puede hacer sin pedir confirmación)
- **Hooks** (lo que se ejecuta antes / después de cada acción)
- **Observabilidad** (logs, trazas, métricas)
- **Feedback loops** (cómo el agente sabe si algo funcionó)
- **Restricciones de seguridad** (sandboxing, dry-runs)
- **Persistencia** ([memoria](../18_Memoria_de_Agentes), [skills](../20_Skills))
- **Estructura del contexto** ([context engineering](../08_Context_Engineering))

## La tesis

> Un buen harness con un modelo modesto **supera** a un modelo top con un harness mediocre.

Por eso Anthropic invierte tanto en Claude Code como producto, no solo en el modelo.

## Ideas para experimentar

- Tomar un agente que funcione mal, mejorar **solo** las descripciones de tools → medir.
- Agregar hooks de pre/post tool y ver cómo cambia el comportamiento.
- Comparar el mismo agente con buena y mala observabilidad.
