# 01 — LLMs

**Large Language Model.** Modelos entrenados sobre cantidades masivas de texto cuya función básica es predecir el próximo token dado un contexto. Todo lo demás (chat, agentes, RAG, tool calling) son técnicas alrededor de este predictor estadístico para parchar sus limitaciones: no tiene memoria, no sabe nada después de su entrenamiento, no puede actuar en el mundo, y a veces alucina.

## Proveedores

- **Pagos / cerrados:** Anthropic (Claude), OpenAI (GPT), Google (Gemini)
- **Más libres / flexibles:** Groq, OpenRouter, Ollama (local)

## Librerías

- **Por proveedor:** `anthropic`, `openai`, `google-genai`
- **Genéricas (modelo-agnósticas):** LangChain, LlamaIndex, Hugging Face Transformers

## Ideas para experimentar

- Hacer la misma llamada con tres proveedores distintos y comparar respuestas.
- Levantar un modelo local con Ollama (`llama3`, `qwen2.5`) y compararlo con uno de API.
- Usar OpenRouter para switchear de modelo sin cambiar código.
