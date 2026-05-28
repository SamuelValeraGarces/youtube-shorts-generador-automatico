# YouTube Shorts - Generador Automático

Workflow de n8n que genera videos cortos automáticamente usando IA.

## Flujo

1. **Trigger manual** — inicia el workflow
2. **OpenAI (gpt-4o-mini)** — genera un guion de 30–45 segundos con hook, desarrollo y cierre
3. **Extracción de keywords** — convierte el guion en palabras clave para buscar clips
4. **Pexels API** — busca videos en formato vertical (portrait) para cada keyword
5. **Descarga de clips** — descarga los archivos MP4
6. **Guardado local** — guarda los clips en `C:\Users\<tu-usuario>\videos\`

## Requisitos

- [n8n](https://n8n.io/) instalado
- Cuenta en [OpenAI](https://platform.openai.com/) con API key
- Cuenta en [Pexels](https://www.pexels.com/api/) con API key

## Configuración

1. Copia `.env.example` a `.env` y rellena tus API keys
2. En n8n, importa el archivo `workflows/youtube_shorts_generador.json`
3. En los nodos HTTP Request, reemplaza los valores de los headers `Authorization` con tus keys
4. Ejecuta el workflow manualmente

## Estructura
<img width="1985" height="548" alt="image" src="https://github.com/user-attachments/assets/3b4f8ac6-f331-4c53-a1c0-9f5be8bb4110" />

```
workflows/
└── youtube_shorts_generador.json   # Workflow principal
.env.example                        # Variables de entorno de ejemplo
```
