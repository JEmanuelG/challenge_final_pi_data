# Fiscalito – Asistente Fiscal Inteligente (RAG)

**Fiscalito** es un chatbot basado en **Retrieval-Augmented Generation (RAG)** que responde consultas sobre **Monotributo en Argentina**, utilizando exclusivamente **documentación oficial** de ARCA, ANSES y Mi Argentina.

Este proyecto fue desarrollado como **Challenge Final** para **Pi Data Strategy & Consulting**, demostrando el diseño e implementación de una arquitectura RAG end-to-end con backend y frontend desacoplados.


## Objetivo del proyecto

Brindar respuestas:
- Claras y concisas
- En español
- Basadas únicamente en fuentes oficiales
- Sin generar información falsa

Fiscalito está orientado a usuarios que no cuentan con conocimientos técnicos o fiscales que necesitan orientación con el régimen de Monotributo.



## Arquitectura

Usuario > Streamlit (Chat UI) > POST /ask FastAPI (API REST) > RAG Pipeline (LangChain) > ChromaDB (Vector Store) > LLM (Cohere)



## Stack Tecnológico

### Backend
- **Python 3.10+**
- **FastAPI**
- **LangChain**
- **Cohere (LLM + Embeddings)**
- **ChromaDB**
- **Uvicorn**

### Frontend
- **Streamlit**

### IA
- **Embeddings:** `embed-v4.0`
- **LLM:** `command-a-03-2025`
- **RAG:** Semantic Search + Context Injection



## Documentación utilizada

El sistema se alimenta exclusivamente de documentos en formato PDF obtenidos de fuentes oficiales:
- Ley de Monotributo
- Información de Monotributo de ANSES
- Documentación oficial ARCA
- Guías de Mi Argentina

Los documentos son indexados en una base vectorial persistente mediante **ChromaDB**.



## Consideraciones técnicas
- El LLM responde solo con información presente en el contexto
- Ante una misma pregunta, el sistema devuelve la misma respuesta
- El prompt limita la respuesta a máximo 3 oraciones
- Se optimizó latencia reduciendo tokens y chunks
- Inicialización de modelos y DB fuera del ciclo de request



## Autor
### Emanuel Guaráz
- Challenge Final – Pi Data Strategy & Consulting


