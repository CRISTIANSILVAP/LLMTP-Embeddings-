# LLMTP-Embeddings-

Repo de práctica basado en el Capítulo 2 de **LLMs-from-scratch** (Sebastian Raschka): preparación de texto, tokenización, muestreo con ventana deslizante y creación de embeddings.

## Contenido

- Notebook principal: `embeddings.ipynb`
- Texto de ejemplo (corpus): `the-verdict.txt`

## Qué se hizo (requisitos cubiertos)

En `embeddings.ipynb` se incluye:

- **Código core del capítulo**: 
	- carga/descarga del texto (The Verdict)
	- tokenización simple con regex (para intuición)
	- construcción de vocabulario + IDs de tokens
	- tokenizador con tokens especiales (`<|endoftext|>`, `<|unk|>`)
	- tokenización BPE con `tiktoken` (estilo GPT-2)
	- creación de dataset/dataloader para *next-token prediction* con ventana deslizante
	- demo de embeddings de tokens y embeddings posicionales (token + posición)

- **Markdown en español con explicaciones propias** sobre por qué cada paso importa para LLMs / sistemas agénticos.
	- Incluye la respuesta a: **“¿Por qué los embeddings codifican significado, y cómo se relacionan con conceptos de redes neuronales?”**

- **Experimento**: variar `max_length` y `stride` y reportar cuántas muestras (`samples`) se generan.
	- Se explica por qué el solapamiento (overlap) ayuda y cuál es el trade-off.

## Requisitos

- Python 3.x
- Paquetes:
	- `torch`
	- `tiktoken`
	- `requests`

Nota: el notebook incluye una celda que instala dependencias **solo si faltan**.

## Cómo ejecutar

### Opción A: VS Code (recomendado)

1. Abrir `embeddings.ipynb`
2. Seleccionar un kernel de Python
3. Ejecutar todo: “Run All”

### Opción B: desde terminal

Si tenés Jupyter instalado:

```bash
python -m pip install notebook
jupyter notebook
```

Abrís `embeddings.ipynb` y ejecutás todas las celdas.

## Créditos

- Fuente original del material: https://github.com/rasbt/LLMs-from-scratch
- Texto `the-verdict.txt`: *The Verdict* (Edith Wharton, dominio público)