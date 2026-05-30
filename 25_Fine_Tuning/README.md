# 24 — Fine-tuning

Entrenar un modelo base con **tus datos** para especializarlo.

## El orden correcto

Antes de pensar en fine-tuning, probá (en este orden):

1. **Prompting** mejor ([prompt engineering](../07_Prompt_Engineering) + [few-shot](../07_Prompt_Engineering)).
2. **[RAG](../12_RAG)** — para darle conocimiento que no tiene.
3. **[Tool use](../13_Tool_Calling)** — para darle capacidades.
4. **Modelo más grande / mejor**.
5. **Recién acá**, fine-tuning.

## Cuándo fine-tuning sí tiene sentido

- Necesitás un **formato muy específico** que el modelo no captura ni con prompting.
- Necesitás **latencia mínima** con un modelo chico.
- Tenés **mucho data propio** de alta calidad.
- Querés un modelo **especializado** en un dominio cerrado.

## Tipos

- **Full fine-tuning** — entrenás todos los pesos. Caro y rara vez necesario.
- **LoRA / QLoRA** — entrenás unas capas adicionales pequeñas, mucho más barato.
- **Instruction tuning** — adaptás formato de instrucciones.
- **RLHF / DPO** — alineación con preferencias humanas.

## La realidad

Fine-tuning es **la solución más cara y compleja**. Es lenta de iterar (cada cambio = re-entrenamiento), difícil de evaluar, y se "rompe" si cambiás el modelo base.

> Dejalo para el final. La mayoría de las veces, mejor prompting + RAG resuelve.

## Ideas para experimentar

- Hacer LoRA sobre un modelo chico (Llama 3 8B, Qwen 2.5 7B) con un dataset propio.
- Comparar fine-tuned vs RAG sobre el mismo problema.
