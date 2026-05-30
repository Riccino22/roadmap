# 11 — Modelos de reasoning

Modelos modernos con **CoT entrenado de fábrica**: hacen razonamiento explícito (a veces visible, a veces oculto) **antes** de la respuesta final.

## Ejemplos

- OpenAI: `o1`, `o3`, `o4-mini`
- Anthropic: Claude con **extended thinking**
- DeepSeek: `R1`
- Google: Gemini con `thinking`
- Open source: `QwQ`, `DeepSeek-R1`

## Tradeoffs

| | Modelo normal | Modelo reasoning |
|---|---|---|
| Latencia | Baja | Alta (segundos a minutos) |
| Costo | Bajo | Alto (cobran tokens de thinking) |
| Calidad en razonamiento | OK | Mejor |
| Tareas simples | Bien | Overkill |

## Cuándo usarlos

✅ Matemática, lógica, código difícil, planning, debugging complejo.
❌ Chat casual, respuestas rápidas, clasificación simple, summarization.

## Ideas para experimentar

- Mismo problema en Sonnet vs Sonnet con extended thinking → comparar.
- Mismo problema en GPT-4o vs o3 → ver cuándo el thinking vale el costo.
