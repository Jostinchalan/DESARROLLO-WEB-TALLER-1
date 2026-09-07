# Guía de Defensa Rápida (Preguntas Orientadoras)
## Proyecto: Landing Page "Asistencia Técnica" (Arquitectura CSS Modular)

Aquí tienes la respuesta exacta y directa para defender tu proyecto frente al docente:

---

### 1. ¿Qué propósito cumple cada etiqueta semántica principal de su página?
- **`<header>`**: Delimita la cabecera superior del sitio. Contiene el logotipo de la empresa y la barra de navegación principal.
- **`<nav>`**: Define la sección de navegación de la página. Agrupa los enlaces (`<ul>` y `<li>`) que permiten desplazarse entre las distintas secciones.
- **`<main>`**: Es el contenedor principal que engloba el contenido único y central de la página (excluye cabeceras y pies repetitivos).
- **`<section>`**: Agrupa el contenido en bloques temáticos lógicos (`hero`, `servicios`, `nosotros`, `contacto`). Cada una lleva su propio encabezado `<h2>` para mantener la jerarquía.
- **`<article>`**: Envuelve cada tarjeta individual dentro de las secciones de servicios y ventajas. Se usa `<article>` porque representa contenido independiente que conserva sentido por sí solo.
- **`<address>`**: Agrupa la información de contacto físico y digital del negocio (dirección, teléfono, correo electrónico y horarios).
- **`<footer>`**: Representa el pie de página del sitio, conteniendo los derechos de autor (`&copy; 2026 Asistencia Técnica`) y créditos.

---

### 2. ¿Qué variables CSS definió, en qué archivo las separó y qué mejora aportan?
- **Separación Modular (`variables.css`):**
  - Siguiendo las buenas prácticas de arquitectura CSS (Design System / Tokens), se separó el bloque `:root` en su propio archivo **`variables.css`**, vinculado antes de `styles.css`. Además, se incluye `@import 'variables.css';` en la hoja principal.
- **Variables definidas en `variables.css`:**
  - **Colores:** `--color-primario` (`#1e40af` Azul Marino), `--color-primario-hover` (`#1e3a8a`), `--color-fondo` (`#ffffff`), `--color-superficie` (`#f8fafc`), `--color-tarjeta` (`#ffffff`), `--color-texto` (`#0f172a`), `--color-texto-secundario` (`#475569`), `--color-borde` (`#e2e8f0`).
  - **Tipografía y Tamaños:** `--fuente-principal` ('Segoe UI', sans-serif), `--fuente-tamano-titulo` (`2.2rem`), `--fuente-tamano-base` (`1rem`).
  - **Espaciados:** `--espacio-sm` (`0.5rem`), `--espacio-md` (`1rem`), `--espacio-lg` (`2rem`), `--espacio-xl` (`3.5rem`).
  - **Interacciones y Bordes:** `--transicion` (`all 0.2s ease-in-out`), `--borde-radio` (`8px`), `--sombra-suave`, `--sombra-hover`.
- **¿Qué mejora aportan?**
  - **Arquitectura Modular y Desacoplamiento:** Separar los Tokens en `variables.css` permite mantener los valores globales aislados de las reglas de diseño.
  - **Mantenibilidad:** Facilita cambiar toda la paleta o tema visual sin tocar las reglas de maquetación en `styles.css`.

---

### 3. ¿Por qué eligió Grid para una zona y Flexbox para otra?
- **CSS Grid (Estructura Bidimensional - Filas y Columnas):**
  - **Zonas:** `.grid-servicios`, `.grid-nosotros` y `.grid-contacto`.
  - **Razón:** Grid está diseñado para layouts bidimensionales. Permite alinear automáticamente las tarjetas en múltiples filas y columnas con `display: grid` y `grid-template-columns: repeat(...)`, asegurando que todas las tarjetas tengan el mismo tamaño de forma limpia.
- **Flexbox (Estructura Unidimensional - Alineación en 1 Línea):**
  - **Zonas:** La barra de navegación `.nav` (`justify-content: space-between`), la sección Hero `.hero-contenido` (alineación vertical de texto y botón), los ítems de contacto `.item-contacto` y el contenido interno de `.tarjeta`.
  - **Razón:** Flexbox es ideal para alinear o distribuir espacio entre elementos en una sola dirección (horizontal o vertical).

---

### 4. ¿Qué regla pertenece al diseño móvil y cómo se amplía mediante Breakpoints?
- **Regla del diseño móvil (Mobile-First):**
  - Todos los estilos escritos fuera de `@media` son los **estilos base** diseñados para pantallas móviles pequeñas (`< 768px`). Por ejemplo:
    - `.grid-servicios { grid-template-columns: 1fr; }` (las tarjetas se muestran en 1 sola columna vertical).
    - `.nav-menu` (se oculta en móviles y se despliega verticalmente mediante el checkbox hack sin JS).
- **Cómo se amplía mediante Media Queries (Breakpoints):**
  - Se utiliza `min-width` para expandir el diseño a pantallas más grandes:
    - **En Pantallas Medianas / Tabletas (`@media (min-width: 768px)`):** El botón de menú móvil se oculta (`.menu-btn { display: none; }`), la navegación pasa a ser horizontal fija (`.nav-menu { display: flex; flex-direction: row; }`), y las grillas aumentan a 2 y 3 columnas (`grid-template-columns: repeat(2, 1fr)`).
    - **En Pantallas Grandes / Escritorio (`@media (min-width: 1024px)`):** La grilla de servicios se expande a 4 columnas horizontales (`grid-template-columns: repeat(4, 1fr)`).
