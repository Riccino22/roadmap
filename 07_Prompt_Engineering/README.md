# 07 — Prompt engineering

Cómo le pedís las cosas al modelo: instrucciones claras, formato esperado, ejemplos.

## Técnicas base

- **Zero-shot:** le pedís directo, sin ejemplos.
  > "Clasificá este email como spam o no spam."

- **Few-shot:** le mostrás algunos ejemplos antes de la tarea real.
  > "Email: 'Ganaste un millón' → spam. Email: 'Reunión mañana' → no spam. Email: 'X' → ?"

- **Role prompting:** le decís qué rol tomar.
  > "Sos un médico especialista en cardiología con 30 años de experiencia..."

- **Chain of Thought:** le pedís que piense paso a paso → ver [10_Chain_of_Thought](../10_Chain_of_Thought).

## Tips prácticos

- Específico > genérico.
- Mostrá el formato de salida con un ejemplo.
- Separá instrucciones de datos (delimitadores, XML tags).
- Iterá: probá, medí, ajustá.

## Ideas para experimentar

- Misma tarea: zero-shot vs few-shot vs role prompting → comparar.
- Reescribir un prompt malo y medir la mejora con [evals](../21_Evals).
