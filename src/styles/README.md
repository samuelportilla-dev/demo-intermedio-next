# ⚠️ GUÍA ARQUITECTÓNICA DE ESTILOS (READ ME)

Este documento es VITAL para cualquier proceso de rebranding o mantenimiento. El sistema visual de este proyecto se divide en una **Capa Base (Estructural)** y una **Capa Premium (Aesthetic)**.

---

## 🏗️ 1. ARCHIVOS GLOBALES Y VARIABLES

### 📄 [global.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/global.css)
*   **Propósito:** Es el corazón del sistema. Define la identidad de marca a través de variables CSS (`:root`).
*   **Elementos Críticos:**
    *   `--color-principal`: Color de énfasis (Rojo La Nonna).
    *   `--color-secundario`: Color de contraste profundo (Azul oscuro).
    *   `.ambient-background`: Fondo orgánico con textura de pergamino y orbes animados.
    *   `.preloader`: Pantalla de carga global con barra de progreso.
    *   `.footer-premium`: Estructura del pie de página compartida.
    *   `.mega-drawer`: El contenedor base del carrito lateral.

---

## 🏠 2. HOME PAGE (INICIO) - COMPARATIVA CRÍTICA

En la página de inicio, estos archivos trabajan en equipo: uno pone los cimientos globales y el otro inyecta la experiencia cinematográfica.

### 📄 [home.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/home.css)
**Naturaleza:** Base de Componentes e Infraestructura (1160 líneas).
Este archivo es fundamental porque alberga componentes técnicos que se usan en todo el sitio.
*   **¿Qué controla exclusivamente?**
    *   **Componentes de Carga:** El `.preloader` y los `.skeleton` (efectos de carga de tarjetas).
    *   **Fondo Atmosférico:** La clase `.ambient-background` (pergamino y orbes).
    *   **Estructura Global:** Diseño del `.footer-premium` y la barra de desplazamiento (`scrollbar`).
    *   **Acción:** El `.boton-flotante-carrito` y las `.promo-card` de ofertas.
*   ⚠️ **ADVERTENCIA:** No borrar. Contiene la infraestructura técnica (fondo, preloader, footer).

### 📄 [home-premium.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/home-premium.css)
**Naturaleza:** Capa Visual de Alto Impacto / Editorial (540 líneas).
Define la estética "10K" y la narrativa visual del restaurante.
*   **¿Qué controla exclusivamente?**
    *   **Hero 10K:** Cabecera cinematográfica (`.hero-10k`) con zoom infinito.
    *   **Efectos Editoriales:** El texto infinito (`.marquee-container`) y el revelado `.clip-reveal-container`.
    *   **Narrativa Visual:** "Filosofía", "Sticky Scroll" (texto pegado) y secciones `.overlap-section`.
*   ⚠️ **ADVERTENCIA:** Responsable del efecto "WOW" y la coreografía visual inicial.

---

## 🍕 3. MENÚ Y EXPERIENCIA DE COMPRA (IMPORTANTE)

Aquí existe una distinción crítica entre dos archivos que a menudo se confunden:

### 📄 [menu.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/menu.css)
**Naturaleza:** Monolito Estructural / Legacy Premium (2500+ líneas).
Este archivo es el "pegamento" original. Contiene estilos que afectan a **múltiples páginas**.
*   **¿Qué controla exclusivamente?**
    *   **Navegación Global:** La clase `.global-nav` y el diseño del logo.
    *   **Sección Nosotros:** El sistema de cuadrícula `.masonry-grid`.
    *   **Sección Contacto:** El layout `.split-screen` y formularios.
    *   **Efectos Globales:** Animaciones genéricas de `.reveal`.
*   ⚠️ **ADVERTENCIA:** Borrar este archivo rompería el diseño de Inicio, Nosotros y Contacto.

### 📄 [menu-premium.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/menu-premium.css)
**Naturaleza:** Especialización de Interfaz / High-End UX (260 líneas).
Contiene el "motor de lujo" diseñado específicamente para la página `/menu`.
*   **¿Qué controla exclusivamente?**
    *   **Cinematic Header:** El slider `.cinematic-carousel-header`.
    *   **Smart Navigation:** El sistema `.menu-sidebar` (ScrollSpy) lateral.
    *   **3D Cards:** Efecto de levitación profunda de las tarjetas de producto (`.producto-card`).
    *   **Search 10K:** El buscador flotante `.search-sticky-container` con desenfoque.
    *   **Mobile Bottom Sheet:** La transformación de categorías en hoja deslizante (`.mini-menu-cats`).

---

## 📱 4. COMPONENTES COMPARTIDOS

### 📄 [nav.css](file:///c:/xampp/htdocs/demo-intermedio-Orded/src/styles/nav.css)
*   **Propósito:** Centraliza la navegación responsiva.
*   **Detalles Específicos:** Controla la transición entre la `.global-nav` de escritorio y la `.mobile-bottom-nav` (la barra de iconos inferior en celulares).

---

## 🛠️ NOTAS DE MANTENIMIENTO PARA EL REBRANDING

1.  **Jerarquía de Carga:** Los archivos `-premium.css` siempre deben cargarse después de los archivos base para asegurar los overrides.
2.  **Fuentes:** Cambia las tipografías en el `:root` de `global.css`.
3.  **GSAP:** No cambies los nombres de clases con `.reveal` o `.mini-menu-cats` sin actualizar los scripts de animación.
4.  **Mobile First:** `menu-premium.css` es altamente dependiente de media queries para el Bottom Sheet.
