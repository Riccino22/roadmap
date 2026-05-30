# Roadmap: Fundamentos para trabajar con LLMs y Agentes

Este repo es un mapa de los conceptos base que considero fundamentales para entender y construir con LLMs y agentes hoy. Cada carpeta es un item del roadmap, con un README que profundiza el concepto y un espacio para hacer prácticas y experimentos.

La idea no es tener todo, sino tener un orden mental claro y un lugar para experimentar con cada pieza.

## Estructura

### Fundamentos del modelo
- [01_LLMs](./01_LLMs) — Qué es un LLM, proveedores, librerías
- [02_Parametros](./02_Parametros) — Parámetros del modelo (7B, 120B, etc.)
- [03_Tokens](./03_Tokens) — Tokens, tokenización, streaming
- [04_Ventana_de_Contexto](./04_Ventana_de_Contexto) — Contexto, límites, olvido
- [05_System_Prompt](./05_System_Prompt) — Rol, reglas, formato
- [06_Determinismo_y_Temperatura](./06_Determinismo_y_Temperatura) — Sampling y no-determinismo

### Comunicación con el modelo
- [07_Prompt_Engineering](./07_Prompt_Engineering) — Zero-shot, few-shot, role prompting
- [08_Context_Engineering](./08_Context_Engineering) — Diseñar todo el contexto, SDD
- [09_Structured_Outputs](./09_Structured_Outputs) — JSON contra schema

### Cómo razonan los modelos
- [10_Chain_of_Thought](./10_Chain_of_Thought) — CoT, ToT, Self-Consistency
- [11_Modelos_de_Reasoning](./11_Modelos_de_Reasoning) — o1, o3, R1, extended thinking

### Dándole conocimiento al modelo
- [12_RAG](./12_RAG) — Retrieval-Augmented Generation, embeddings, vector DBs

### Dándole capacidades al modelo
- [13_Tool_Calling](./13_Tool_Calling) — Function calling, code execution
- [14_MCP](./14_MCP) — Model Context Protocol

### Agentes y orquestación
- [15_Agentes](./15_Agentes) — Qué es un agente, workflow vs agent
- [16_Arquitecturas_de_Agentes](./16_Arquitecturas_de_Agentes) — ReAct, Reflexion, HITL
- [17_Patrones_de_Orquestacion](./17_Patrones_de_Orquestacion) — Chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer
- [18_Memoria_de_Agentes](./18_Memoria_de_Agentes) — Corto y largo plazo, Agentic RAG
- [19_Harness_Engineering](./19_Harness_Engineering) — Diseño del entorno del agente
- [20_Skills](./20_Skills) — Conocimiento procedural reutilizable

### Realidad de producción
- [21_Evals](./21_Evals) — Tests para sistemas no-determinísticos
- [22_Guardrails_y_Seguridad](./22_Guardrails_y_Seguridad) — Prompt injection, privacidad
- [23_Costos_Latencia_y_Caching](./23_Costos_Latencia_y_Caching) — Prompt caching, optimización
- [24_Fine_Tuning](./24_Fine_Tuning) — Cuándo (y cuándo no) hacer fine-tuning
- [25_Open_Source_vs_Cerrados](./25_Open_Source_vs_Cerrados) — Llama, Qwen, DeepSeek vs APIs

## Recursos generales

- ["Building Effective Agents" (Anthropic)](https://www.anthropic.com/research/building-effective-agents)
- Paper original de ReAct (Yao et al. 2022)
- Paper original de CoT (Wei et al. 2022)
- Blog de Lilian Weng
- Blog de Simon Willison
- [modelcontextprotocol.io](https://modelcontextprotocol.io)
