# 25 — Open source vs cerrados

Hoy existen **modelos open weight muy capaces**: Llama (Meta), Qwen (Alibaba), DeepSeek, Mistral, `gpt-oss` (OpenAI). Algunos corren en una laptop, otros necesitan datacenter.

## Tradeoffs

| Aspecto | API cerrada (Claude, GPT, Gemini) | Open weight (Llama, Qwen, DeepSeek) |
|---|---|---|
| Capacidad top | Sí | Cerrando la brecha |
| Costo por token | Más alto | Más bajo (o 0 self-hosted) |
| Privacidad | Confiás en el proveedor | Total control |
| Latencia | Depende del proveedor | Depende de tu infra |
| Fine-tuning | Limitado | Total |
| Velocidad de actualización | Auto, instant | Vos elegís cuándo |
| Operación | Cero | Vos sos sysadmin |

## Cómo correr open weight

- **Local liviano:** Ollama (Mac, Windows, Linux).
- **Local serio:** vLLM, llama.cpp, LM Studio.
- **Hosted open weight:** Groq, Together, Fireworks, OpenRouter, DeepInfra.

## Cuándo elegir cada uno

**Cerrados (API):**
- Vas rápido a producción.
- Necesitás capacidad top.
- No tenés equipo de infra para LLMs.

**Open weight:**
- Privacidad / compliance estrictos.
- Volumen alto donde el costo por token mata el negocio.
- Necesitás fine-tuning serio.
- Querés evitar lock-in con un proveedor.

## La nota honesta

Para un producto que arranca, casi siempre conviene **API cerrada** primero (Claude / GPT). Si funciona y los números crecen, ahí evaluás open weight. Empezar con infra propia y modelos locales suele ser sobreingeniería.

## Ideas para experimentar

- Correr Llama 3 8B en Ollama y compararlo con Haiku en una tarea real.
- Comparar costos a 1M tokens/mes: GPT-4o-mini vs Llama en Groq vs Llama self-hosted.
