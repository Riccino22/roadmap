# 18 — Memoria de agentes

Los agentes tienen **dos tipos** de memoria.

## Corto plazo

La conversación actual en la [ventana de contexto](../04_Ventana_de_Contexto). Se pierde cuando termina la sesión o cuando el contexto se llena.

## Largo plazo

Lo que **persiste entre sesiones**:

- Hechos sobre el usuario ("Riccardo es full-stack, le gusta Go")
- Decisiones tomadas en sesiones previas
- Contexto histórico de un proyecto
- Preferencias de estilo

Casi siempre se implementa con **[RAG](../12_RAG)**: guardás eventos importantes en una vector database y el agente los recupera cuando son relevantes.

## Agentic RAG

Cuando es el **agente** el que decide **qué buscar y cuándo**, en vez de un pipeline fijo de retrieval. El retrieval es una tool más, no una etapa pre-LLM.

## Patrones reales

- **Conversation summarization** — resumir conversaciones viejas y guardar el resumen.
- **Fact extraction** — extraer hechos explícitos y guardarlos como memorias tipadas.
- **Episodic memory** — guardar eventos completos para recuperarlos por similitud.

Ver el sistema de memoria de Claude Code (`MEMORY.md` + memorias por archivo) como ejemplo concreto.

## Ideas para experimentar

- Construir un agente con memoria a largo plazo en Chroma.
- Comparar comportamiento con / sin memoria persistente entre sesiones.
