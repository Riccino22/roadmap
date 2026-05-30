# 12 — RAG (Retrieval-Augmented Generation)

**Problema:** el modelo no conoce tus datos privados ni lo que pasó después de su training.

**Solución:** buscar información relevante en el momento de la consulta y pasársela al modelo como contexto.

## Pipeline básico (vector RAG)

1. **Ingesta:** tomás tus documentos (wiki, base de datos, PDFs).
2. **Chunking:** los partís en fragmentos manejables.
3. **Embeddings:** cada fragmento → vector numérico que representa su significado.
4. **Storage:** los vectores se guardan en una **vector database**.
5. **Retrieval:** la pregunta del usuario también se convierte en vector, buscás los chunks más cercanos por similitud (cosine, dot product).
6. **Generación:** los chunks recuperados van al contexto del LLM, que responde con esa info.

## Embeddings y espacio multidimensional

Conceptos con significado parecido quedan cerca en el espacio vectorial. Lo que en un plano cartesiano son 2 dimensiones (X, Y), en embeddings reales son **cientos o miles** de dimensiones.

## Vector databases

- **Especializadas:** Pinecone, Weaviate, Qdrant, Milvus, Chroma
- **Sobre Postgres:** `pgvector`
- **In-memory:** FAISS

## Variantes

- **Vector RAG** (lo descrito arriba) — el más común.
- **GraphRAG** — usa un grafo de conocimiento con entidades y relaciones explícitas. Mejor cuando las relaciones entre conceptos importan más que la similitud textual.
- **Hybrid search** — combina búsqueda vectorial con keyword search (BM25).
- **Reranking** — después del retrieval, un modelo más fino reordena los resultados.

## Ideas para experimentar

- Indexar tus notas personales con Chroma + un modelo de embeddings y hacer Q&A.
- Comparar retrieval con / sin reranker.
- Probar GraphRAG sobre un dominio con relaciones (organigrama, knowledge base).
