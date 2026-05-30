# 03 — Tokens

Un **token** es la unidad mínima de texto que el modelo procesa. Puede ser una palabra entera, un fragmento o un signo de puntuación. Por ejemplo, "Ciudad" puede partirse en varios tokens (`Ciu`, `dad`).

Como regla práctica: **1 token ≈ 3/4 de palabra en inglés** (en español suele consumir un poco más).

## Por qué importan

- Los proveedores **cobran por token** (input + output, con precios distintos).
- La **ventana de contexto** se mide en tokens.
- El modelo genera tokens **de a uno** → eso es lo que ves como *streaming*.

## Ideas para experimentar

- Usar el tokenizer de OpenAI / Anthropic para contar tokens de un texto.
- Comparar cuántos tokens consume el mismo texto en distintos idiomas.
- Implementar streaming en una llamada y mostrar tokens en vivo.

## Recursos

- [OpenAI Tokenizer](https://platform.openai.com/tokenizer)
- [tiktoken](https://github.com/openai/tiktoken)
