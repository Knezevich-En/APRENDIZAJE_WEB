# 📘 Resumen del Curso de Desarrollo Web (Cheat Sheet)

Este documento guarda la teoría y código fundamental de todo lo que hemos aprendido hasta ahora. ¡Úsalo como tu manual de referencia rápida!

---

## 🧱 Parte 1: HTML BÁSICO (Domina el Esqueleto)

*   **Estructura Base:** Todo documento HTML necesita `<!DOCTYPE html>`, `<html>`, un `<head>` (configuraciones ocultas) y el mágico `<body>` (donde vive todo lo visible).
*   **Encabezados y Párrafos:** Desde `<h1>` (el rey de la página, solo 1 por sitio) hasta `<h6>`. Además la etiqueta `<p>` para textos normales.
*   **Listas:**
    *   Desordenada plana: `<ul>`
    *   Ordenada numérica: `<ol>`
    *   El ítem individual: `<li>` (obligatoriamente va adentro de la lista).
*   **Enlaces e Imágenes (Atributos):**
    *   `<a href="url" target="_blank">`: El ancla, usa target blank para abrir nueva pestaña.
    *   `<img src="ruta.jpg" alt="texto">`: Etiqueta vacía (no se cierra). El `alt` es vital para si se rompe la imagen.
*   **Formularios Básicos:** La etiqueta maestra `<form>`. Adentro usamos `<input type="text">` o `password`/`email` y un `<button>`.

---

## 🧠 Parte 2: HTML AVANZADO (Nivel Profesional)

*   **Comentarios:** El código que nadie ve sirve para los programadores. HTML `<!-- -->` y CSS `/* */`.
*   **La pareja de oro (Label + Input):** Siempre usa `<label for="idDelInput">` para conectar el texto explicativo con el campo respectivo para mayor accesibilidad.
*   **Elementos extra de Formulario:**
    *   `<textarea>`: Caja de texto grande multilinea.
    *   `<select>` y `<option>`: Para crear menús desplegables.
    *   `<fieldset>` y `<legend>`: Agrupadores visuales impresionantes de formularios.
*   **Acordeones Nativos:** `<details><summary>Título</summary> TEXTO </details>`. El texto se esconde hasta hacer clic.
*   **Enlaces Mágicos:** `mailto:` (Envia correo), `tel:` (Llama por teléfono), y `#id` (Nos mueve a otra parte de la misma página).
*   **Multimedia y Optimización:**
    *   `<audio>` y `<video>` siempre con `controls`.
    *   `loading="lazy"` en imágenes para que la página vuele en rendimiento.
*   **Semántica Moderna:** Usamos cajas lógicas (`<header>`, `<main>`, `<footer>`, `<nav>`) en vez de genéricas (`<div>`) para enamorar a Google.

---

## 🎨 Parte 3: CSS BÁSICO (Magia Visual)

*   **Regla de Oro Universales:** SIEMPRE reseteamos la página usando: `* { margin:0; padding:0; box-sizing:border-box; }`. Así el tamaño no se "infla".
*   **Selectores Básico:** A la etiqueta por su nombre `h1`, a la clase con punto `.miclase`, al ID con hashtag `#mi-id`.
*   **El Modelo de Caja (Box Model):** TODO es un rectángulo.
    *   `padding`: El cojín hacia adentro.
    *   `margin`: El escudo o empujón hacia afuera.
    *   `border`: La línea que los divide.
*   **Tipografía y Colores:**
    *   Conectamos Google Fonts y usamos `font-family`.
    *   En color, usamos HEXA (`#ff00ff`) para colores más precisos en `color`, `background-color`.
*   **Unidades y Decoración:** No usar solo `px`. Usar `%`, `vh` para adaptarnos a las pantallas. Le damos impacto con fondos de degradado `linear-gradient` y sombras `box-shadow`.

---

## ⚙️ Parte 4: CSS INTERMEDIO (Arquitectura y Movimiento)

*   **Selectores Compuestos:** Como el descendiente `main p` o el hermano directo `h1 + p`. Ayudan a ser precisos sin crear decenas de clases.
*   **El peso (Cascada y Especificidad):** CSS se lee de arriba a abajo. Lo último de abajo gana. PERO un ID le gana a una Clase, no importa donde esté.
*   **Pseudoclases y Pseudoelementos:**
    *   `:hover` (Acción cuando el puntero pasa encima).
    *   `::before` y `::after` (Inyectan "fantasmas" `content` a la pantalla desde CSS).
*   **Metodología BEM (Bloque__Elemento--Modificador):** Por ejemplo `.formulario__titulo`, la mejor forma de nombrar clases.
*   **Layout (Display):**
    *   `block`: Ocupan toda la fila.
    *   `inline`: Tristes... no respetan anchos ni márgenes verticales.
    *   `inline-block`: Lo mejor de ambos mundos para botones (como nuestros enlaces `<a>`).
*   **Control del Espacio (Positions):**
    *   `relative`: Libera las ataduras y crea una "cárcel" para sus hijos.
    *   `absolute`: Fantasma flotante absoluto que se guía por su abuelo `relative`.
    *   `fixed`: Pegado eternamente a la pantalla del usuario (como un NavBar o Footer).
    *   `z-index`: El Rey del 3D, decide quién tapa a quién.

*[Este archivo se mantendrá actualizado en tiempo real con nuestras lecciones...]*.
