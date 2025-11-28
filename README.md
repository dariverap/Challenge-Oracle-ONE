# 🔐 Encriptador de Mensajes - Oracle ONE Challenge

> **Desarrollado por:** Diego Rivera | **Rol:** Frontend Developer
> **Contexto:** Desafío Oracle Next Education (ONE) - Alura Latam

## 📋 Introducción

Bienvenido a la documentación técnica del **Encriptador de Mensajes**. Este proyecto es una aplicación web *client-side* diseñada para transformar textos mediante un algoritmo de sustitución de caracteres. El objetivo principal es ofrecer una herramienta segura y eficiente para encriptar y desencriptar comunicaciones, priorizando una experiencia de usuario (UX) fluida y una interfaz adaptativa (Responsive Design).

La aplicación destaca por su arquitectura limpia, ausencia de dependencias externas pesadas y un enfoque estricto en la semántica HTML5 y estándares modernos de JavaScript (ES6+).

## 🛠 Tech Stack

El proyecto ha sido construido utilizando una arquitectura monolítica basada en estándares web nativos, garantizando máximo rendimiento y compatibilidad.

*   **Core:**
    *   ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white) **HTML5 Semántico:** Estructuración robusta del contenido (`main`, `section`, `header`).
    *   ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white) **CSS3 Moderno:** Uso extensivo de Flexbox, CSS Grid implícito, Animaciones (`@keyframes`) y Variables.
    *   ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) **Vanilla JavaScript (ES6+):** Lógica de negocio, manipulación del DOM y gestión de eventos sin frameworks.

*   **Metodología & Estilos:**
    *   **Mobile First Approach:** Diseño responsivo adaptado desde móviles hasta pantallas de alta resolución.
    *   **CSS Reset:** Normalización de estilos para consistencia entre navegadores.
    *   **BEM (Inspiración):** Convenciones de nomenclatura de clases para mantenibilidad.

## 🚀 Instalación y Despliegue

Al ser una aplicación estática, no requiere procesos de compilación (build) ni gestores de paquetes (npm/yarn).

### Pasos para ejecutar localmente:

1.  **Clonar el repositorio:**
    ```bash
    git clone https://github.com/tu-usuario/dariverap-challenge-oracle-one.git
    ```

2.  **Navegar al directorio:**
    ```bash
    cd dariverap-challenge-oracle-one
    ```

3.  **Ejecutar la aplicación:**
    *   **Opción A (Doble click):** Abre el archivo `index.html` directamente en tu navegador web favorito (Chrome, Firefox, Edge).
    *   **Opción B (VS Code Live Server):** Si usas VS Code, haz clic derecho en `index.html` y selecciona "Open with Live Server" para un entorno de recarga automática.

## 📦 Análisis de Módulos Principales

La arquitectura del proyecto se divide en tres capas lógicas esenciales para garantizar la separación de responsabilidades:

### 1. Motor de Encriptación y Validación (`js/message_encrypter.js`)
Este es el corazón de la lógica de negocio. Contiene funciones puras y manejadores de estado que orquestan la transformación de datos.
*   **Algoritmo de Sustitución:** Implementa el mapeo de vocales a cadenas específicas (`e` -> `enter`, `i` -> `imes`, etc.) utilizando métodos de string como `.replaceAll()`.
*   **Validación Estricta:** Función `validate(text)` que asegura, mediante iteración y códigos ASCII/Regex, que el input solo contenga letras minúsculas sin acentos, previniendo errores de codificación.
*   **Manejo del Portapapeles:** Integración con la Clipboard API para una UX superior mediante la función `copyOption()`.

### 2. Sistema de Diseño Adaptativo (`css/style.css`)
El módulo de presentación maneja la identidad visual y la adaptabilidad del layout.
*   **Breakpoints Estratégicos:** Uso de `@media queries` para tres entornos críticos:
    *   *Desktop (> 1024px):* Layout horizontal con panel lateral.
    *   *Tablet (770px - 1024px):* Reajuste de flujos y tamaños de tipografía.
    *   *Mobile (< 415px):* Stack vertical (columnas) optimizado para el tacto.
*   **Micro-interacciones:** Animaciones CSS (`@keyframes typing`, `rotateImagen`, `beats`) que proveen feedback visual al usuario sin impactar el rendimiento del hilo principal de JS.

### 3. Capa de Interacción y Feedback (DOM & Modales)
Gestiona la comunicación entre el usuario y el sistema.
*   **Sistema de Modales:** Implementación de un modal nativo (sin librerías) que intercepta errores (ej. texto vacío, caracteres inválidos) y confirmaciones de éxito.
*   **Controladores de Eventos:** Listeners vinculados a los botones de acción (`click`) que disparan la lógica de negocio y actualizan el DOM dinámicamente (ej. ocultar la imagen de "sin mensaje" y mostrar el resultado).

---
© 2024 Diego Rivera. Proyecto realizado con fines educativos para Oracle Next Education.
