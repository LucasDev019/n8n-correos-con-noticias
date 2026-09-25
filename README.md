# Automatización de resumen de noticias con n8n + IA

Workflow de n8n que obtiene noticias sobre inteligencia artificial, las filtra, las resume mediante un modelo de lenguaje local con Ollama y envía un resumen HTML por correo electrónico.

## Flujo

1. **Manual Trigger** — inicia el workflow manualmente.
2. **HTTP Request** — consulta NewsAPI y obtiene noticias en español sobre inteligencia artificial.
3. **Split Out** — separa los artículos para procesarlos individualmente.
4. **Filter** — descarta artículos sin descripción y artículos marcados como `\[Removed]`.
5. **Basic LLM Chain** — genera un resumen neutral de 2-3 frases por noticia.
6. **Ollama Chat Model** — utiliza un modelo de lenguaje local.
7. **Aggregate** — reúne los resultados.
8. **Code in JavaScript** — genera el HTML del correo.
9. **Send a message** — envía el resumen mediante Gmail.

## Tecnologías

* n8n
* NewsAPI
* HTTP / REST API
* Ollama
* LLM / IA generativa
* JavaScript
* Gmail
* Automatización y procesamiento de datos

## Qué demuestra

* Integración de APIs externas.
* Automatización de procesos con n8n.
* Filtrado y procesamiento de datos.
* Uso de IA local mediante Ollama.
* Generación dinámica de HTML con JavaScript.
* Integración con servicios de correo.

## Configuración

El `workflow.json` es una versión sanitizada del workflow original.

Antes de ejecutarlo debes configurar:

* Una API key propia de NewsAPI.
* Un modelo de Ollama compatible.
* Una cuenta de Gmail en n8n.
* El correo electrónico de destino.

En el nodo **HTTP Request**, sustituye `YOUR\_NEWSAPI\_API\_KEY` por tu API key.

Las credenciales de Gmail y Ollama no se incluyen en este repositorio; deben configurarse en tu propia instancia de n8n.

