# Generador y Simulador Banco Preguntas GIFT Moodle
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/soyunomas/GeminiGiftGenerator/blob/main/LICENSE)
[![Demo](https://img.shields.io/badge/Demo-Live-brightgreen)](https://soyunomas.github.io/GeminiGiftGenerator/index.html)
Herramienta integrada en un único archivo HTML que combina dos funcionalidades principales mediante pestañas:

1.  **Generador GIFT:** Crea bancos de preguntas en formato **GIFT** (Opción Múltiple y Verdadero/Falso) para **Moodle**, utilizando la IA de **Google Gemini**.
2.  **Simulador GIFT:** Carga archivos `.gift` (o preguntas generadas) y permite responderlas en una interfaz similar a Moodle, con corrección detallada y cálculo de puntuación (incluyendo penalizaciones).

¡Descarga el archivo `index.html` y úsalo directamente en tu navegador!

*Puedes probar una demostración en vivo aquí: [Link a Demo en Vivo](https://soyunomas.github.io/GeminiGiftGenerator/index.html)*

## Capturas de Pantalla
* Interfaz de usuario generador de preguntas:

![Captura de Pantalla del Proyecto](image-1.png)

* Detalle de preguntas generadas con posibilidad de seleccionar las que queramos para luego descargarlas:

![Captura de Pantalla del Proyecto](image-2.png)

* Interfaz de usuario simulador:

![Captura de Pantalla del Proyecto](image-3.png)

* Detalle de valoración del simulador:

![Captura de Pantalla del Proyecto](image-4.png)

## Características Principales

### General
*   **Interfaz Unificada con Pestañas:** Accede al Generador y al Simulador fácilmente desde la misma página.
*   **Archivo Único:** Todas las funcionalidades están contenidas en `index.html`. No requiere instalación ni servidor (solo navegador moderno y conexión a internet).
*   **Diseño Responsivo:** Interfaz adaptable gracias a Bootstrap.

### Generador GIFT (Pestaña "Generador GIFT")
*   **Generación Automática con IA:** Crea preguntas GIFT utilizando la API de Google Gemini.
*   **Tipos de Pregunta:** Soporta la generación de preguntas de **Opción Múltiple** y **Verdadero/Falso**.
*   **Conexión API Segura:** Requiere una clave API de Google Gemini (con opción de mostrar/ocultar).
*   **Selección de Modelo Gemini:** Permite elegir el modelo específico de Gemini a utilizar (cargado dinámicamente, con `gemini-1.5-flash-latest` como preferido por defecto).
*   **Configuración Flexible:**
    *   Define el **tema** o descripción del contenido.
    *   Selecciona el **número de preguntas**.
    *   Elige el **tipo de pregunta**.
    *   **Opciones Condicionales (Opción Múltiple):** Nº de respuestas, Múltiples Correctas (con puntuación parcial), Penalizaciones configurables.
*   **Vista Previa Interactiva:** Muestra las preguntas generadas, permite seleccionar las deseadas y marca visualmente errores de formato GIFT.
*   **Descarga Fácil:** Botones para descargar **todas** las preguntas o solo las **seleccionadas** en formato `.gift`.
*   **Integración con Simulador:** Botones para **cargar directamente** las preguntas generadas (todas o selección) en la pestaña del Simulador para probarlas inmediatamente.
*   **Feedback al Usuario:** Indicadores de carga y mensajes de error claros.

### Simulador GIFT (Pestaña "Simulador")
*   **Carga de Archivos:** Sube archivos `.gift` o `.txt` mediante selección o arrastrar y soltar (drag & drop).
*   **Parseo GIFT:** Interpreta preguntas de Opción Múltiple (simple/múltiple) y Verdadero/Falso, incluyendo feedback y porcentajes de puntuación/penalización.
*   **Interfaz tipo Moodle:** Presenta las preguntas de forma familiar.
*   **Interactividad:** Permite seleccionar respuestas (radio/checkbox) con feedback visual inmediato del estado ("Sin responder", "Respuesta guardada").
*   **Corrección Detallada:** Evalúa las respuestas al pulsar "Enviar Intento y Corregir", mostrando feedback específico por opción y general por pregunta.
*   **Cálculo de Puntuación Avanzado:** Considera puntuaciones parciales y **penalizaciones** configuradas en el formato GIFT para calcular la nota.
*   **Resultados Completos:**
    *   Muestra puntuación total, porcentaje y **nota sobre 10**.
    *   Presenta un **cálculo detallado (colapsable)** mostrando cómo se obtuvo la puntuación de cada pregunta (incluyendo valores positivos y negativos antes de limitar).
    *   Desglose de preguntas correctas, parcialmente correctas, incorrectas y sin responder.
    *   Fecha y hora de finalización.
*   **Repetir Intento:** Permite volver a realizar el mismo cuestionario cargado sin necesidad de subir el archivo de nuevo.

## Tecnologías Utilizadas

*   **HTML5:** Estructura semántica.
*   **CSS3:** Estilos personalizados.
*   **Bootstrap 4.5.2:** Framework CSS (incluye Tabs, Collapse, etc.).
*   **Font Awesome 6.0.0:** Iconos.
*   **JavaScript (ES6+):** Lógica del cliente, interacción API, manipulación DOM, generación/parseo GIFT, cálculo de puntuación, lógica de UI.
    *   `fetch`, `async/await`.
    *   `FileReader`, `Blob`.
    *   IIFE (Immediately Invoked Function Expressions) para encapsular scripts.
*   **Google Gemini API:** IA generativa externa.
*   **Dependencias JS de Bootstrap:**
    *   jQuery 3.5.1 Slim
    *   Popper.js 2.5.3

## Instalación / Visualización

Este proyecto es un único archivo HTML estático.

1.  **Clona o descarga el repositorio:**
    ```bash
    git clone https://github.com/soyunomas/GeminiGiftGenerator
    ```
    O descarga el archivo `index.html` directamente.
2.  **Navega al directorio (si clonaste):**
    ```bash
    cd GeminiGiftGenerator
    ```
3.  **Abre el archivo `index.html` en tu navegador web moderno.**

**¡Importante!** Se requiere **conexión a internet** para:
*   Cargar Bootstrap y Font Awesome desde CDNs.
*   Realizar llamadas a la API de Google Gemini (en la pestaña Generador).

## Uso

1.  Abre `index.html`. Verás dos pestañas: "Generador GIFT" y "Simulador".

### Para Generar Preguntas:
1.  Permanece en la pestaña "**Generador GIFT**".
2.  Ingresa tu **Clave API de Google Gemini**.
3.  Selecciona el **Modelo Gemini**.
4.  Escribe una **Descripción del Tema**.
5.  Configura el **Tipo de Pregunta**, Nº de Preguntas y otras opciones si aplica.
6.  Haz clic en "**Generar Banco de Preguntas GIFT**".
7.  Revisa la **Vista Previa**. Selecciona las preguntas deseadas haciendo clic sobre ellas.
8.  Usa los botones:
    *   "**Descargar Todo**" / "**Descargar Selección**" para guardar el archivo `.gift`.
    *   "**Cargar Todo en Simulador**" para enviar todas las preguntas generadas a la otra pestaña.
    *   "**Cargar Selección en Simulador**" para enviar solo las preguntas seleccionadas. Al pulsar uno de estos, la interfaz cambiará automáticamente a la pestaña "Simulador".

### Para Simular un Cuestionario:
1.  Ve a la pestaña "**Simulador**".
2.  **Opción A (Archivo):** Carga un archivo `.gift` o `.txt` usando "Seleccionar Archivo" o arrastrándolo a la zona designada.
3.  **Opción B (Desde Generador):** Usa los botones "Cargar..." en la pestaña Generador.
4.  Responde las preguntas presentadas. El estado cambiará a "Respuesta guardada".
5.  Haz clic en "**Enviar Intento y Corregir**".
6.  Revisa los resultados: puntuación, nota sobre 10, desglose.
7.  Haz clic en el botón <i class="fas fa-chevron-down"></i> junto a "Detalle del Cálculo" para ver cómo se obtuvo la puntuación de cada pregunta, incluyendo penalizaciones.
8.  Usa "**Repetir Cuestionario**" para volver a intentarlo o "**Cargar Otro Archivo**" para empezar de nuevo (esto te devolverá a la pantalla de carga).

## Pre-configurar API Key (Opcional)

Puedes incrustar una API Key directamente en el código fuente (lee la advertencia de seguridad más abajo).

1.  Abre `index.html` con un editor.
2.  Localiza la constante `API_KEY` cerca del inicio de la función `DOMContentLoaded`.
3.  Está marcado con // -- Poner tu API-KEY aquí ---
4.  Introduce tu clave entre las comillas `""`.

**Ejemplo:**

```javascript
    <!-- ==================== SCRIPTS ==================== -->

    <!-- Script del GENERADOR GIFT -->
    <script>
        (function() { // IIFE Generador
            document.addEventListener('DOMContentLoaded', function () {
                // --- Variables Generador (igual) ---
                const loadInSimulatorButton = document.getElementById('load-in-simulator-button');
                const loadSelectedInSimulatorButton = document.getElementById('load-selected-in-simulator-button');
                const API_KEY = "AQUI-PONES-TU-API-KEY"; // -- Poner tu API-KEY aquí ---
                const apiKeyInput = document.getElementById('gemini-api-key');
                const showApiKeyButton = document.getElementById('show-api-key');
                // ... resto del código JavaScript del generador ...
            });
        })();
    </script>
```
**¡Advertencia de Seguridad Importante!** ⚠️

> Incrustar tu clave API directamente en el código HTML/JavaScript significa que **cualquier persona que tenga acceso al archivo podrá verla**. **NO subas este archivo con tu clave API personal a un repositorio público (como GitHub)**, ya que expondrías tu clave y podrías incurrir en costes si alguien la utiliza. Esta opción es más adecuada para uso estrictamente personal, local o en distribuciones muy controladas donde confías plenamente en los usuarios que tendrán acceso al código fuente. La forma recomendada y segura es que cada usuario introduzca su propia clave API en la interfaz web.

## Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles.

## Contacto

Creado por **soyunomas**
