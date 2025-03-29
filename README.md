# Generador Banco Preguntas GIFT Moodle

Herramienta simple en un único archivo HTML para generar bancos de preguntas en formato **GIFT** (Opción Múltiple y Verdadero/Falso) para **Moodle**, utilizando la IA de **Google Gemini**. ¡Descarga y úsalo directamente en tu navegador!

## Captura de Pantalla / Demo

![Captura de Pantalla del Proyecto](URL_A_LA_IMAGEN_O_PLACEHOLDER)
*(Opcional: puedes añadir un enlace a una demo en vivo aquí: [Link a Demo en Vivo](URL_DEMO_SI_EXISTE))*

## Características Principales

*   **Generación Automática con IA:** Crea preguntas GIFT utilizando la API de Google Gemini.
*   **Tipos de Pregunta:** Soporta la generación de preguntas de **Opción Múltiple** y **Verdadero/Falso**.
*   **Interfaz Sencilla:** Todas las funcionalidades están contenidas en un **único archivo `index.html`**. No requiere instalación ni servidor.
*   **Conexión API Segura:** Requiere una clave API de Google Gemini (con opción de mostrar/ocultar).
*   **Selección de Modelo Gemini:** Permite elegir el modelo específico de Gemini a utilizar (cargado dinámicamente tras introducir la API Key).
*   **Configuración Flexible:**
    *   Define el **tema** o descripción del contenido para las preguntas.
    *   Selecciona el **número de preguntas** a generar.
    *   Elige el **tipo de pregunta** (Opción Múltiple o Verdadero/Falso).
    *   **Opciones Condicionales (para Opción Múltiple):**
        *   Número de respuestas por pregunta.
        *   Permitir múltiples respuestas correctas (con puntuación parcial).
        *   Aplicar penalizaciones configurables para respuestas incorrectas.
*   **Vista Previa Interactiva:** Muestra las preguntas generadas antes de descargar, permitiendo revisar el formato, las respuestas y el feedback. Incluye manejo visual de errores de formato GIFT.
*   **Selección de Preguntas:** Permite seleccionar individualmente las preguntas deseadas (y válidas) de la vista previa.
*   **Descarga Fácil:**
    *   Botón para descargar **todas** las preguntas generadas en un archivo `.gift`.
    *   Botón para descargar únicamente las preguntas **seleccionadas** en un archivo `.gift`.
*   **Feedback al Usuario:** Indicadores de carga y mensajes de error claros durante la interacción con la API y la generación/parseo de preguntas.
*   **Diseño Responsivo:** Interfaz adaptable gracias a Bootstrap.

## Tecnologías Utilizadas

*   **HTML5:** Estructura semántica del contenido.
*   **CSS3:** Estilos personalizados y layout.
*   **Bootstrap 4.5.2:** Framework CSS para diseño responsivo y componentes UI.
*   **Font Awesome 6.0.0:** Biblioteca de iconos.
*   **JavaScript (ES6+):** Lógica del cliente, interacción con API Gemini, manipulación del DOM, generación de archivos, parseo básico de GIFT y lógica condicional de UI.
    *   Uso de `fetch` y `async/await` para llamadas API.
    *   Creación de `Blob` para descarga de archivos.
*   **Google Gemini API:** Servicio externo de IA generativa.
*   **Dependencias JS de Bootstrap:**
    *   jQuery 3.5.1 Slim
    *   Popper.js 2.5.3

## Instalación / Visualización

Este proyecto es un único archivo HTML estático. No requiere instalación.

1.  **Clona o descarga el repositorio:**
    ```bash
    git clone URL_DEL_REPOSITORIO
    ```
    O descarga el archivo `index.html` directamente.
2.  **Navega al directorio (si clonaste):**
    ```bash
    cd NOMBRE_DEL_DIRECTORIO
    ```
3.  **Abre el archivo `index.html` en tu navegador web moderno.**

**¡Importante!** Se requiere **conexión a internet** para:
*   Cargar las librerías de Bootstrap y Font Awesome desde sus CDNs.
*   Realizar las llamadas a la API de Google Gemini para generar las preguntas.

## Uso

1.  Abre el archivo `index.html` en tu navegador.
2.  Ingresa tu **Clave API de Google Gemini**. Los modelos compatibles se cargarán en el desplegable.
3.  Selecciona el **Modelo Gemini** que deseas usar.
4.  Escribe una **Descripción del Tema** detallada para las preguntas. Puedes incluir contexto, nivel educativo, idioma deseado o incluso pegar texto base.
5.  Selecciona el **Tipo de Pregunta** (Opción Múltiple o Verdadero/Falso).
6.  Configura el **Nº de Preguntas**.
7.  *Si elegiste Opción Múltiple*, configura el Nº de Respuestas, si permites Múltiples Correctas y la Penalización. Estas opciones se ocultarán si eliges Verdadero/Falso.
8.  Haz clic en el botón "**Generar Banco de Preguntas GIFT**".
9.  Espera mientras la aplicación se comunica con la API. Verás un indicador de carga.
10. Las preguntas generadas aparecerán en la sección "**Vista Previa de Preguntas**". Revisa el formato. Las preguntas con errores de formato GIFT se marcarán en rojo y mostrarán el bloque original.
11. Haz clic sobre las preguntas válidas que desees incluir en la descarga selectiva (se marcarán con un fondo azul).
12. Utiliza los botones "**Descargar Todo**" o "**Descargar Selección**" para obtener el archivo `.gift`. La descarga de selección excluirá automáticamente las preguntas marcadas con error.
13. Importa el archivo `.gift` descargado en tu banco de preguntas de Moodle.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE.md` (si existe) para más detalles.
*(Sugerencia: Añade un archivo LICENSE.md con el texto de la licencia MIT si aún no lo tienes)*.

## Contacto

Creado por **[Tu Nombre/Usuario GitHub]** - **[Tu Email o Red Social (Opcional)]**
