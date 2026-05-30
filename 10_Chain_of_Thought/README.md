# 10 — Chain of Thought y variantes

Si un LLM solo predice el próximo token, ¿cómo "razona"? Pidiéndole que **piense en voz alta antes de responder**.

## CoT — Chain of Thought

Paper original: Wei et al. 2022 (Google). Mostraron que agregar `"Let's think step by step"` mejoraba dramáticamente la performance en tareas de razonamiento (matemática, lógica, código).

```
Prompt: "Si tengo 5 manzanas y le doy 2 a Juan, ¿cuántas tengo?
Pensemos paso a paso."
```

## Variantes

- **Self-Consistency:** corrés el mismo prompt N veces con temperatura alta, te quedás con la respuesta más frecuente. Útil para zero-shot.
- **Tree of Thoughts (ToT):** el modelo explora múltiples ramas de razonamiento como un árbol, podando las que no llevan a buen puerto.
- **Self-refine:** el modelo critica su propia respuesta y la mejora.

## Hoy

CoT ya viene entrenado de fábrica en los modelos modernos → ver [11_Modelos_de_Reasoning](../11_Modelos_de_Reasoning).

## Ideas para experimentar

- Resolver un problema matemático con / sin "pensá paso a paso".
- Implementar Self-Consistency con N=5 y comparar con N=1.
