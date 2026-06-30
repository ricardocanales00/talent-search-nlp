# Sistema Inteligente para Búsqueda de Talento (NLP)
Proyecto académico de la Maestría en Inteligencia Artificial Aplicada — Tecnológico de Monterrey.
Materia: Procesamiento de Lenguaje Natural | Prof. Luis Eduardo Falcón Morales

## Descripción

Sistema de búsqueda y ranking de candidatos (talent matching) que compara CVs sintéticos contra una vacante real (Software Engineer – Microsoft AI Development Acceleration Program) usando técnicas de NLP, sin emplear atributos protegidos (nombre, género, edad, etc.) para evitar sesgos en el proceso de selección.

## ¿Qué hace?

1. **Generación de CVs sintéticos**: crea 20 CVs en formato PDF y PNG con distintos niveles de seniority (Junior, Mid, Senior).
2. **Extracción de texto**: usa `pypdf` para PDFs y metadata embebida en PNG (simulando un OCR perfecto).
3. **Normalización de texto**: minúsculas, eliminación de acentos y espacios redundantes.
4. **Vectorización TF-IDF**: representa CVs y vacante como vectores TF-IDF (1-2 gramas).
5. **Búsqueda por similitud**: usa FAISS para encontrar los candidatos más similares a la vacante.
6. **Re-ranking por keywords**: ajusta el ranking según coincidencia de habilidades técnicas clave.
7. **Reporte técnico** con la arquitectura del sistema y propuestas de métricas de desempeño.

## Tecnologías utilizadas

- Python
- pandas, numpy
- scikit-learn (TfidfVectorizer)
- FAISS (faiss-cpu)
- pypdf, reportlab (generación/lectura de PDFs)
- Pillow (generación de CVs en PNG con metadata)

## Estructura del proyecto
├── MNA_NLP_actividad_Busqueda_de_Talento.ipynb   # Notebook principal
└── cvs_creados/                                   # CVs sintéticos generados (PDF/PNG)

## Decisiones de diseño relevantes

- Se excluyeron datos sensibles (nombre, género, edad, etc.) del análisis para evitar sesgos.
- Se eligió TF-IDF en lugar de embeddings semánticos (LLM/sentence-transformers) como decisión consciente, priorizando un pipeline reproducible y explicable.
- Los CVs en PNG simulan el texto extraído vía OCR mediante metadata embebida, en vez de usar OCR real.

## Autor
Ricardo López Canales — Matrícula A01422699

## Contexto académico
Proyecto realizado como actividad de equipo para la materia de Procesamiento de Lenguaje Natural, Maestría en Inteligencia Artificial Aplicada, Tecnológico de Monterrey.
