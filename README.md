# PracticaBootstrap — Proyección Personal 2026

## Autora
**Corina Alejandra Acosta Oliva**  
Ingeniería en Tecnologías de la Información — Universidad de las Fuerzas Armadas ESPE — Ecuador 🇪🇨

---

## Descripción General

Sitio web de portafolio académico desarrollado con **Bootstrap 5.3** como **tercera etapa** del proceso de aprendizaje en desarrollo web:

| Etapa | Práctica | Enfoque |
|-------|----------|---------|
| 1 | PracticaHTML | Estructura semántica con HTML5 puro |
| 2 | PracticaCSS | Estilos propios con CSS3 y Flexbox/Grid |
| 3 | **PracticaBootstrap** ← | Framework Bootstrap 5, diseño Mobile First |

La página principal (`proyeccion.html`) presenta la **proyección personal, académica y profesional** de la autora: hacia dónde se proyecta, qué desea llegar a ser, qué habilidades quiere fortalecer y qué metas espera alcanzar en el área de **Ciberseguridad y Forense Digital**.

---

## Tecnologías Utilizadas

- **HTML5** semántico (`header`, `nav`, `main`, `section`, `article`, `aside`, `figure`, `footer`)
- **Bootstrap 5.3** — Grid, Components, Utilities, Scrollspy
- **CSS3** personalizado con variables CSS (`css/custom.css`)
- **Font Awesome 6.5** — Iconografía completa
- **JavaScript vanilla** — Inicialización de Scrollspy

---

## Estructura de Carpetas

```
PracticaBootstrap/
├── index.html                    # Página principal del portafolio
├── proyeccion.html               # Página de proyección personal (PRINCIPAL)
├── README.md                     # Este archivo
│
├── css/
│   └── custom.css                # Estilos propios (paleta ESPE turquesa)
│
├── pages/
│   ├── sobremi/
│   │   └── sobremi.html          # Perfil académico
│   ├── horario/
│   │   └── horario.html          # Horario de clases
│   ├── contenido/
│   │   └── contenido.html        # Contenido académico
│   ├── multimedia/
│   │   └── multimedia.html       # Presentación multimedia
│   ├── proyectos/
│   │   └── proyectos.html        # Portafolio de proyectos
│   ├── cto/
│   │   ├── contacto.html         # Formulario de contacto
│   │   └── buzon.html            # Buzón de sugerencias
│   ├── buscar/
│   │   └── buscar.html           # Búsqueda
│   ├── login/
│   │   └── login.html            # Inicio de sesión
│   ├── habilidades.html          # Subpágina: Habilidades a desarrollar
│   ├── metas.html                # Subpágina: Metas académicas
│   └── proyectos-futuros.html    # Subpágina: Proyectos futuros
│
└── multimedia/
    ├── img/
    │   ├── mifoto.jpg
    │   ├── banner-espe.png
    │   └── mundito.ico
    ├── audio/
    └── video/
```

---

## Instrucciones para Visualizar el Sitio

1. Clonar o descargar el repositorio en tu equipo local
2. Abrir el archivo `proyeccion.html` directamente en un navegador moderno (Chrome, Firefox, Edge)
3. Alternativamente, desde `index.html` navegar al enlace **Proyección** en la barra de navegación
4. Para una experiencia completa, usar las **DevTools** del navegador y activar el modo responsive para ver la adaptación Mobile First

> No se requiere servidor web — todos los recursos son locales o CDN (Bootstrap, Font Awesome).

---

## Capturas de Pantalla

> *Agregar capturas de pantalla aquí:*

### Vista Móvil (< 576px)
*(Insertar captura del hero + navbar colapsada + cards en columna única)*

### Vista Tablet (768px)
*(Insertar captura del carrusel de visión + grid de cards en 2 columnas)*

### Vista Escritorio (≥ 992px)
*(Insertar captura del aside con scrollspy + contenido en 9 columnas)*

---

## Componentes Bootstrap Utilizados

| # | Componente | Sección en proyeccion.html |
|---|-----------|--------------------------|
| 1 | **Navbar** colapsable + Dropdown | Encabezado — todas las páginas |
| 2 | **Container / Grid** (col-12/md/lg) | Layout completo |
| 3 | **Cards** con imagen, badges y botones | Perfil Destacado (§3) |
| 4 | **Carousel** principal | Visión Profesional (§1) |
| 5 | **Accordion** + **Carousel** anidado | Especializaciones (§2) |
| 6 | **Progress Bars** (múltiples colores) | Habilidades (§4) |
| 7 | **Table** + **Progress Bars** combinadas | Plan de Desarrollo (§5) |
| 8 | **Accordion** + Cards internas | Metas y Certificaciones (§6) |
| 9 | **Grid de Cards** responsivas | Proyectos Soñados (§7) |
| 10 | **List Group** (timeline) | Línea de Tiempo (§8) |
| 11 | **List Group** + **Tab Content** conectados | Áreas de Interés (§9) |
| 12 | **Modal** + **Form** | Contacto Rápido |
| 13 | **Alert** informativa | Inicio del main |
| 14 | **Badges** en cards, acordeones y navbar | Múltiples secciones |
| 15 | **Buttons** (primary, outline, light) | Perfil, Modal, Hero |
| 16 | **Scrollspy** en `<aside>` lateral | Navegación lateral |

---

## Combinaciones de Componentes Destacadas

### 1. Acordeón que contiene un Carrusel (Sección §2)
El componente más complejo: un `Accordion` con tres ítems, donde **cada ítem contiene un `Carousel` independiente** (`data-bs-ride="false"` para control manual). Al expandir un área de especialización, aparece un carrusel de 3 slides con información, herramientas y certificaciones de esa área.

```html
<div class="accordion" id="especialidadesAccordion">
  <div class="accordion-item">
    <button data-bs-toggle="collapse" data-bs-target="#esp1">Ciberseguridad</button>
    <div id="esp1" class="accordion-collapse collapse show">
      <!-- CARRUSEL DENTRO DEL ACORDEÓN -->
      <div id="cyberCarousel" class="carousel slide" data-bs-ride="false">
        <div class="carousel-inner">
          <div class="carousel-item active">...</div>
          <div class="carousel-item">...</div>
        </div>
      </div>
    </div>
  </div>
</div>
```

### 2. Tabla + Progress Bars (Sección §5)
Una `<table>` con 8 filas de habilidades donde la **última columna de cada fila contiene una `progress-bar`**. Esto permite visualizar el nivel actual de cada habilidad directamente en la tabla.

```html
<table class="table table-striped table-hover">
  <tr>
    <td>HTML5 / CSS3</td>
    <td><span class="badge bg-info">Frontend</span></td>
    <td>Avanzado</td>
    <td>
      <div class="progress" style="height:20px;">
        <div class="progress-bar" style="width:85%;">85%</div>
      </div>
    </td>
  </tr>
</table>
```

### 3. List Group conectado a Tab Content (Sección §9)
Un `list-group` actúa como menú de navegación por pestañas (`data-bs-toggle="list"`): al hacer clic en cada ítem del grupo, el contenido informativo correspondiente aparece en el `tab-content` adyacente con animación `fade`.

```html
<!-- Grupo de lista (menú) -->
<div class="list-group" id="interest-list-tab" role="tablist">
  <a class="list-group-item active" data-bs-toggle="list" href="#int-cyber">Ciberseguridad</a>
  <a class="list-group-item" data-bs-toggle="list" href="#int-forense">Forense Digital</a>
</div>
<!-- Secciones informativas conectadas -->
<div class="tab-content">
  <div class="tab-pane fade show active" id="int-cyber">Contenido de Ciberseguridad</div>
  <div class="tab-pane fade" id="int-forense">Contenido de Forense Digital</div>
</div>
```

### 4. Formulario dentro de Modal
El botón "Contacto Rápido" en el hero abre un `modal` que contiene un `form` completo con `input`, `select` y `textarea`, todo validado con Bootstrap.

---

## Personalizaciones CSS Propias (`css/custom.css`)

### Paleta de Colores ESPE
```css
:root {
  --color-turquesa: #008B8B;   /* Color principal */
  --color-oscuro:   #006f6f;   /* Hover / dark variant */
  --color-fondo:    #f0f8ff;   /* Fondo general */
  --color-fondo-alt:#e0ffff;   /* Secciones alternadas */
}
```

### Componentes personalizados
- **Navbar:** color `#008B8B`, dropdown oscuro `#006f6f`, hover con fondo semitransparente
- **Cards:** `border-radius: 12px`, sombra turquesa en hover (`transform: translateY(-5px)`)
- **Card Header:** fondo `#008B8B`, texto blanco, borde redondeado solo arriba
- **Accordion:** botón activo en turquesa con ícono blanco; fondo del cuerpo `#fafeff`
- **Progress bars:** color base turquesa, altura `1rem`, `border-radius: 10px`
- **Modal header:** fondo `#008B8B`, botón de cierre invertido a blanco
- **Footer:** fondo `#008B8B`, links en `#e0ffff`, hover con `translateY(-2px)`
- **Botones:** `btn-primary` en turquesa con `box-shadow` en hover
- **Formularios:** `focus` con `box-shadow` en turquesa semitransparente
- **Scroll suave:** `html { scroll-behavior: smooth; }` para anclas

### Estilos específicos de la página de proyección
- `.carousel-inner-accordion`: carruseles sin bordes redondeados visibles al estar dentro del acordeón
- `.carousel-btn-dark` / `.carousel-indicators-dark`: controles oscuros para carruseles sobre fondo claro
- `.skill-label`: etiquetas de barras de progreso en turquesa, `font-weight: 600`
- `.timeline-dot`: punto circular reutilizable para la línea de tiempo
- `#aside-nav .list-group-item`: borde izquierdo turquesa en hover/active (scrollspy)

---

## Análisis de la Adaptación Mobile First

El diseño sigue la metodología **Mobile First**: se define el layout para pantallas pequeñas primero y se amplía progresivamente con breakpoints.

### Breakpoints aplicados

| Elemento | Mobile (xs) | Tablet (md) | Desktop (lg) |
|----------|-------------|-------------|--------------|
| Aside de navegación | `d-none` (oculto) | `d-none` | `col-lg-3` visible |
| Contenido principal | `col-12` | `col-12` | `col-lg-9` |
| Cards de proyectos | `col-12` | `col-md-6` | `col-lg-3` |
| Tarjeta de perfil | `col-12` (imagen arriba) | `col-md-5` + `col-md-7` | igual |
| Figura (imagen) | Full width | 5/12 columnas | igual |
| Hero padding | `1.5rem` | `2.5rem` | `4rem` |
| Tabla de habilidades | Scroll horizontal | Normal | Normal |

### Verificaciones Mobile First realizadas
- ✅ El menú colapsa correctamente en pantalla pequeña (hamburguesa)
- ✅ Las imágenes son `img-fluid` y no desbordan su contenedor
- ✅ Las tarjetas pasan de 4 columnas a 1 columna en móvil
- ✅ La tabla tiene `table-responsive` para scroll horizontal en pantallas pequeñas
- ✅ Los formularios del modal son cómodos en pantallas táctiles (padding `0.6rem 1rem`)
- ✅ El carrusel reduce `min-height` en mobile mediante media query
- ✅ Los botones del hero usan `flex-wrap` para no desbordarse en pantallas pequeñas
- ✅ El aside de scrollspy se oculta en mobile (no consume espacio)

---

## Etiquetas Semánticas HTML5 Utilizadas

| Etiqueta | Uso en el proyecto |
|----------|--------------------|
| `<header>` | Hero banner de la página de proyección |
| `<nav>` | Barra de navegación principal |
| `<main>` | Contenido principal de cada página |
| `<section>` | Cada bloque temático (visión, habilidades, metas…) |
| `<article>` | Contenido de las cards y ítems de la lista de tiempo |
| `<aside>` | Panel lateral de scrollspy en proyeccion.html |
| `<figure>` | Imagen de perfil con `<figcaption>` |
| `<footer>` | Pie de página con enlaces y redes sociales |

---

## Conexión con el Portafolio Anterior

La página de proyección está vinculada con todas las páginas del portafolio mediante la navbar común:
- `proyeccion.html` → `pages/sobremi/sobremi.html` (botón "Sobre mí")
- `pages/sobremi/sobremi.html` → `proyeccion.html` (botón "Ver mi Proyección")
- Todas las páginas → `proyeccion.html` (enlace activo en navbar)

---

## Compatibilidad

- Chrome / Edge 90+
- Firefox 88+
- Safari 14+
- Navegadores móviles modernos (iOS Safari, Android Chrome)

---

*Última actualización: Junio 2026 — Fundamentos Web ESPE*
