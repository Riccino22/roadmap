# 17 — Patrones de orquestación

Cuando combinás varias llamadas a LLMs, hay 5 patrones bien establecidos (del post de Anthropic):

## 1. Prompt chaining

Pasos **secuenciales fijos**: el output de uno es el input del siguiente.

```
[Outline] → [Draft] → [Edit] → [Final]
```

Útil cuando la tarea se descompone naturalmente en sub-tareas.

## 2. Routing

Un LLM **clasifica el input** y lo manda al sub-flujo correcto. Es despachar.

```
Input → [Classifier LLM] → "soporte técnico" → Flow A
                        → "ventas"          → Flow B
                        → "billing"         → Flow C
```

Permite usar modelos más chicos / prompts específicos por categoría.

## 3. Parallelization

Varios LLMs trabajan **en paralelo**. Dos sabores:
- **Sectioning** — partís la tarea en pedazos independientes.
- **Voting** — varios corren la misma tarea y votás / agregás.

## 4. Orchestrator-workers

Un LLM **coordinador** planifica dinámicamente y **delega** a sub-agentes / sub-tareas. Más flexible que chaining porque los sub-pasos no están fijos.

Ejemplo: agente de research que decide qué temas investigar y lanza sub-tareas por cada uno.

## 5. Evaluator-optimizer

Un LLM **genera**, otro **evalúa**, loop hasta pasar un umbral.

```
Generator → Output → Evaluator → "no, mejorá X"
       ↑________________________↓
```

Útil para escritura, código, traducción.

## En la práctica

Los más usados en producción: **routing** y **orchestrator-workers**.

## Ideas para experimentar

- Implementar cada patrón en su forma mínima.
- Tomar un workflow real y ver cuál de los 5 le aplica.

## Recursos

- [Building Effective Agents — Anthropic](https://www.anthropic.com/research/building-effective-agents) (con diagramas)
