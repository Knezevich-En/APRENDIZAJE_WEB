# 📘 La Biblia del Desarrollo Web (Cheat Sheet Detallado)

Este documento es tu guía definitiva y detallada con todas las variaciones de código posibles para lo que hemos aprendido hasta el momento.

---

## 🧱 Parte 1: HTML BÁSICO Y AVANZADO (Estructura y Semántica)

### 1.1 Etiquetas Básicas
*   **Encabezados:** Jerarquía desde `<h1>` hasta `<h6>`. 
    *   *Regla:* Solo un `<h1>` por documento para SEO.
*   **Párrafos y Listas:** 
    *   `<p>Mi texto</p>`
    *   Desordenada: `<ul><li>Elemento 1</li></ul>`
    *   Ordenada: `<ol><li>Elemento 1</li></ol>`

### 1.2 Enlaces e Imágenes
*   **Enlaces (`<a>`):**
    ```html
    <a href="https://google.com">Link normal</a>
    <a href="https://google.com" target="_blank">Abre nueva pestaña</a>
    <a href="mailto:correo@correo.com">Abre app de correo</a>
    <a href="tel:+123456789">Abre app de teclado numérico</a>
    <a href="#mi-id">Salta a otra sección de la página</a>
    ```
*   **Imágenes (`<img>`):** Requiren `src` y `alt` siempre.
    ```html
    <!-- loading="lazy" retrasa la carga hasta hacer scroll -->
    <img src="foto.jpg" alt="Descripción para ciegos" loading="lazy">
    ```

### 1.3 Formularios Interactivos (`<form>`)
*   **Cajas de texto (`<input>`):**
    ```html
    <input type="text" placeholder="Tu nombre">
    <input type="password" placeholder="Tu contraseña">
    <input type="email" placeholder="correo@ejemplo.com">
    <input type="number" min="1" max="10">
    ```
*   **Caja grande y Menús Desplegables:**
    ```html
    <textarea rows="4" cols="50">Escribe un párrafo...</textarea>
    
    <select name="opciones">
      <option value="1">Opción 1</option>
      <option value="2">Opción 2</option>
    </select>
    ```
*   **Agrupadores y Accesibilidad:**
    El `<label>` se asocia via `for` y `id`. Todo se envuelve en un `<fieldset>` con un `<legend>`.
    ```html
    <fieldset>
      <legend>Datos Personales</legend>
      <label for="nombre">Dime tu nombre</label>
      <input type="text" id="nombre">
    </fieldset>
    ```

### 1.4 HTML Semántico (Adiós a los Divs infinitos)
*   `<header>`: Inicio de la página o de un artículo.
*   `<nav>`: Bloque de enlaces de navegación (Menú principal).
*   `<main>`: El contenido protagonista de la página, solo hay uno.
*   `<article>`: Contenido que tiene sentido por sí mismo (Noticia de blog).
*   `<section>`: Agrupador temático de contenido.
*   `<footer>`: Pie de página.

---

## 🎨 Parte 2: CSS BÁSICO E INTERMEDIO (Estilos y Arquitectura)

### 2.1 El Modelo de Caja (Box Model) Detallado
Todo elemento es cuadrado. 
*   **Reset Universal:** Imprescindible en todo proyecto.
    ```css
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box; /* Previene que el padding modifique el tamaño real de la caja */
    }
    ```
*   **Padding (Relleno Interior):**
    ```css
    /* Individuales */
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;
    
    /* Shorthands (Atajos) */
    padding: 10px; /* Aplica a los 4 lados */
    padding: 10px 20px; /* Arriba/Abajo 10px, Derecha/Izquierda 20px */
    padding: 10px 20px 30px 40px; /* Arriba, Derecha, Abajo, Izquierda (Las agujas del reloj) */
    ```
*   **Margin (Espaciado Exterior):** Funciona igual que padding (`margin-top`, etc).
    *   *Truco de centrado:* `margin: 0 auto;` centra cajas en medio de la pantalla.
*   **Borders y Radius:**
    ```css
    /* Borde largo */
    border-width: 2px;
    border-style: solid; /* solid, dashed, dotted, double */
    border-color: red;
    
    /* Borde Atajo (El más usado) */
    border: 2px solid red;
    border-bottom: 5px dashed blue; /* Poner borde a un solo lado */
    
    /* Redondear esquinas */
    border-radius: 10px; /* 4 esquinas */
    border-radius: 50%; /* Crea un círculo perfecto si la caja es cuadrada */
    ```

### 2.2 Colores, Fondos y Sombras
*   **Fondos (`background`):**
    ```css
    background-color: #ff0000; /* HEX Puro */
    background-color: rgb(255, 0, 0); /* RGB Puro */
    background-color: rgba(255, 0, 0, 0.5); /* RGB con Opacidad (50% transparente) */
    
    /* Degradados Lineales */
    background-image: linear-gradient(to right, red, blue);
    ```
*   **Sombras (`box-shadow`):**
    ```css
    /* EjeX EjeY Difuminado Propagación Color */
    box-shadow: 0px 4px 10px 2px rgba(0, 0, 0, 0.3);
    ```

### 2.3 Selectores Compuestos y BEM
*   **Selectores:**
    ```css
    p { } /* Etiqueta */
    .caja { } /* Clase */
    #unico { } /* ID */
    
    div p { } /* Descendiente: Todos los <p> dentro de cualquier <div> */
    div > p { } /* Hijo Directo: Solo los <p> que sean hijos INMEDIATOS del <div> */
    h1 + p { } /* Hermano adyacente: El <p> inmediatamente debajo del <h1> */
    ```
*   **Metodología BEM (Bloque__Elemento--Modificador):**
    Nomenclatura profesional para clases:
    ```html
    <button class="boton boton--rojo">
      <span class="boton__icono"></span>
      Texto
    </button>
    ```

### 2.4 Comportamiento de Diseño (`display` y Textos)
*   **Display:**
    *   `block`: Ocupan el 100% del ancho de la fila (ej. `<div>`).
    *   `inline`: Fluyen como letras. NO respetan ancho, alto ni márgneres arriba/abajo (ej. `<span>`, `<a>`).
    *   `inline-block`: Fluyen en línea, pero SÍ respetan ancho, alto y márgenes. Ideal para botones.
    *   `none`: Desaparece de pantalla.
*   **Trucos de Texto e Imágenes:**
    ```css
    /* Evitar desbordes de palabras gigantes */
    word-wrap: break-word; 
    
    /* Truncar texto y agregar "..." */
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    
    /* Que las fotos no se aplasten si el width y height son fijos */
    object-fit: cover; /* Recorta preservando proporción */
    object-position: center; /* Enfoca el centro */
    ```

### 2.5 Magias Vivas: Pseudoclases y Transiciones
*   **Estado e Interactividad:**
    ```css
    a:hover { ... } /* Puntero encima */
    input:focus { outline: 2px solid blue; } /* Al hacer clic adentro */
    li:first-child { ... } /* El primero de la lista */
    ```
*   **Animando Suavemente (`transition`):** Si a la clase `.boton` le metes color rojo en el `:hover`, el cambio es seco.
    ```css
    .boton {
       /* Propiedad, Duración, Ritmo */
       transition: background-color 0.3s ease; 
       /* shortcut: transition: all 0.3s ease; */
    }
    ```

### 2.6 Ubicaciones y Layouts (`position`)
Propiedad crítica del CSS intermedio que saca a los elementos de su flujo natural:
*   `position: static`: El estado normal y pasivo de todos.
*   `position: relative`: Conserva su lugar en el flujo, pero te permite "moverlo" usando `top`, `bottom`, `left`, `right`. Además, encierra como "cárcel" a sus hijos absolutos.
*   `position: absolute`: Flota desconectado del flujo real de la página. Se rige por el ancestro con posición relativa más cercano que tenga.
*   `position: fixed`: Flota pegado a la pantalla. Nunca se mueve aunque hagas scroll.
*   `position: sticky`: Es normal hasta que haces scroll, luego se pega al borde de la pantalla.
*   `z-index: 100;`: Define el orden de las capas 3D. El número más alto está al frente de la pantalla.
