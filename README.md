Generador de Presentaciones con IA (Client-Side)
Una aplicación web sin servidor (serverless) que genera presentaciones de diapositivas completas (texto e imágenes) utilizando Inteligencia Artificial. La aplicación se ejecuta completamente en el navegador y permite descargar el resultado como un archivo HTML independiente y portable.
✨ Características Principales
100% Client-Side: No requiere instalación de backend, Node.js ni Python. Funciona con un solo archivo index.html.
Multilenguaje: Interfaz y generación de contenido disponibles en Español, Inglés, Francés y Alemán.
Modelos de IA Flexibles:
Texto (LLMs): Selección entre Gemini, GPT-5 Nano, Claude, Deepseek, Perplexity, etc.
Imagen: Selección entre Flux, ZImage, Kontext, NanoBanana, etc.
Lógica de Contenido Inteligente:
Estructura automática: Introducción → Subtemas Específicos → Conclusión.
Prevención de duplicados: La IA "recuerda" qué diapositivas ha generado para no repetir temas.
Personalización Visual: Estilos artísticos (Cubismo, Realismo, Anime, etc.) y relación de aspecto (Vertical/Horizontal).
Edición y Control:
Regeneración de imágenes individuales con nuevas semillas (seeds).
Posibilidad de editar el prompt de la imagen manualmente antes de aprobarla.
Exportación Portable: Descarga la presentación en un archivo HTML con las imágenes incrustadas en Base64 (no requiere internet para visualizarse una vez descargada).
🚀 Cómo Usar
Clonar/Descargar: Descarga el archivo index.html de este repositorio.
Abrir: Haz doble clic en index.html para abrirlo en tu navegador web favorito (Chrome, Edge, Firefox, etc.).
Configurar API:
Ingresa tu API Key de Pollinations.ai en el campo superior.
Generar:
Elige el idioma, el modelo de lenguaje (LLM), el tema y el estilo visual.
Haz clic en "Generar Presentación".
Descargar:
Una vez generado el texto, aparecerá el botón de descarga.
Puedes esperar a que se generen las imágenes, regenerar las que no te gusten o editar sus prompts.
Al hacer clic en "Descargar Presentación", obtendrás un archivo .html listo para presentar.
🛠️ Integración Técnica (Pollinations AI)
Esta aplicación actúa como una interfaz frontend que interactúa directamente con la API pública de Pollinations.ai.
Generación de Texto (Estructura)
La aplicación realiza peticiones secuenciales a la API de texto para construir la narrativa:
Endpoint: GET https://enter.pollinations.ai/api/generate/text/{prompt}
Ingeniería de Prompt: Se inyecta un System Prompt que define el rol de experto en presentaciones. El User Prompt varía dinámicamente para cada diapositiva, enviando al LLM la lista de títulos ya generados para asegurar que cada nueva diapositiva trate un subtema distinto.
Generación de Imágenes
Para cada diapositiva, se genera una ilustración única:
Endpoint: GET https://enter.pollinations.ai/api/generate/image/{prompt}
Parámetros: Se utiliza el parámetro seed (semilla aleatoria) para garantizar que, aunque el prompt sea el mismo, la imagen pueda regenerarse y variar.
Persistencia: Al descargar la presentación, la aplicación convierte las imágenes obtenidas de la API a cadenas Base64 y las incrusta en el HTML final. Esto garantiza que la presentación funcione offline y no dependa de enlaces externos que puedan expirar.
⚙️ Configuración Disponible
Opción	Descripción
API Key	Tu llave personal de Pollinations (formato plln_sk_...).
LLM	El "cerebro" que escribe el texto (ej. gemini-search, claude, deepseek).
Estilo	El filtro artístico visual (ej. Cyberpunk, Watercolor, Realism).
Aspect Ratio	Formato de las diapositivas: Horizontal (PC) o Vertical (Móvil/TikTok).
📋 Requisitos
Un navegador web moderno con soporte para JavaScript (ES6+).
Una conexión a internet activa (para comunicarse con la API de IA).
Una API Key válida de Pollinations.
📄 Licencia
Este proyecto es de código abierto. Siéntete libre de modificarlo y mejorarlo.
Diseñado por Juan Guillermo Rivera Berrío utilizando tecnología Deepseek y Pollinations.
