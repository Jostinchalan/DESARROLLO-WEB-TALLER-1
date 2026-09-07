# Landing Page - Asistencia Técnica 💻🖨️
### Taller de Desarollo Web - Taller 1

Landing page semántica, responsive y modular desarrollada con **HTML5 y CSS3 Puro**, adaptable a dispositivos móviles, tabletas y computadoras de escritorio.

---

## 🚀 Características del Proyecto

- **HTML5 Semántico:** Uso de `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<address>` y `<footer>`.
- **CSS3 Modular con Design Tokens:** Variables globales separadas en `variables.css` para colores, tipografías, espaciados y bordes.
- **Layout Híbrido (Grid 2D & Flexbox 1D):**
  - **CSS Grid:** Grillas de servicios, ventajas y contacto.
  - **Flexbox:** Barra de navegación, encabezados, alineación de botones e ítems de tarjetas.
- **Estrategia Mobile-First:** Diseñado primero para dispositivos móviles y ampliado mediante Media Queries (`min-width: 768px` y `1024px`).
- **Interacción 100% CSS (Sin JavaScript):**
  - Menú desplegable móvil nativo mediante la técnica **Checkbox Hack**.
  - Desplazamiento suave (`scroll-behavior: smooth`).
  - Animaciones y efectos hover/focus en botones y tarjetas.
- **Accesibilidad & Iconos SVG:** Iconos vectoriales nativos escalables sin librerías externas.

---

## 📁 Estructura del Código

```
TALLER_DESARROLLO_B1/
├── index.html            # Estructura semántica HTML5
├── variables.css         # Custom Properties (:root) / Design Tokens
└── styles.css            # Estilos globales, Mobile-First, Grid & Flexbox
```

---

## 🛠️ Cómo Ejecutar el Proyecto

1. Clona este repositorio:
   ```bash
   git clone https://github.com/Jostinchalan/DESARROLLO-WEB-TALLER-1.git
   ```
2. Abre `index.html` en cualquier navegador web.
