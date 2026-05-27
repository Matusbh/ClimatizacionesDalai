# Climatizaciones Dalai — Web Corporativa

Sitio web corporativo para **Climatizaciones Dalai**, instalador profesional de aire acondicionado en Tenerife, Canarias. Construido con Astro a partir de una maqueta HTML aprobada por el cliente.

---

## 🌐 Ver en vivo

[https://climatizaciones-dalai.vercel.app](https://climatizaciones-dalai.vercel.app) — Vercel (actual)

[https://climatizacionesdalai.es](https://climatizacionesdalai.es) — Dominio definitivo (pendiente)

---

## Arquitectura del proyecto

```
ClimatizacionesDalai/
├── public/
│   ├── styles/
│   │   └── global.css          # Todos los estilos del sitio
│   ├── scripts/
│   │   └── main.js             # JavaScript vanilla (FAQ, scroll reveal, nav móvil)
│   ├── favicon.ico
│   └── favicon.svg
└── src/
    ├── components/
    │   ├── Nav.astro            # Navegación sticky con menú móvil
    │   ├── Hero.astro           # Sección hero con imagen de fondo y CTAs
    │   ├── Servicios.astro      # Tarjetas de instalación residencial y comercial
    │   ├── PorQueDalai.astro    # 4 USPs (instalador oficial, atención, cobertura, presupuesto)
    │   ├── Proceso.astro        # 4 pasos del proceso de instalación
    │   ├── Galeria.astro        # Grid de 6 imágenes de instalaciones
    │   ├── Cobertura.astro      # Zonas de cobertura en Tenerife
    │   ├── Testimonios.astro    # 3 testimonios de clientes
    │   ├── Faq.astro            # Accordion con 6 preguntas frecuentes
    │   ├── Contacto.astro       # Tarjetas de contacto (WhatsApp, tel, dirección, horario, IG, email)
    │   ├── Footer.astro         # Footer con navegación, contacto y links legales
    │   └── WhatsappFloat.astro  # Botón flotante de WhatsApp (fijo, animación pulso)
    ├── layouts/
    │   └── Layout.astro         # Layout base: head completo, SEO, Schema.org, fuentes, scripts
    └── pages/
        └── index.astro          # Página principal — ensambla todos los componentes
```

### Stack tecnológico

| Herramienta                    | Uso                                                                  |
| ------------------------------ | -------------------------------------------------------------------- |
| [Astro 6](https://astro.build) | Framework SSG — genera HTML estático sin JS innecesario              |
| CSS vanilla                    | Estilos escritos a mano, sin frameworks — `public/styles/global.css` |
| JavaScript vanilla             | Interacciones del cliente — `public/scripts/main.js`                 |
| Google Fonts                   | Tipografías: **Manrope** (titulares) + **Inter** (cuerpo)            |
| SVG inline                     | Todos los iconos son SVG inline, sin dependencias externas           |

---

## SEO implementado

### Metadatos básicos

- `<title>` con keyword principal: _Instalación de Aire Acondicionado en Tenerife | Climatizaciones Dalai_
- `<meta name="description">` de 150 caracteres optimizada para CTR
- `<meta name="theme-color">` con el azul corporativo `#1B3A8A` para móviles
- `<link rel="canonical">` apuntando al dominio principal
- `<html lang="es">` declarado correctamente

### Open Graph y Twitter Card

- `og:title`, `og:description`, `og:image` (1200×630), `og:url`, `og:type`
- `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`

### Schema.org — LocalBusiness (JSON-LD)

Markup estructurado completo para negocio local:

```json
{
  "@type": "LocalBusiness",
  "name": "Climatizaciones Dalai",
  "telephone": "+34671924110",
  "address": "Calle San Agustín 49, 38410 Los Realejos, Santa Cruz de Tenerife",
  "geo": { "latitude": 28.3868, "longitude": -16.5805 },
  "areaServed": "Tenerife, Canarias",
  "openingHoursSpecification": "Lun–Vie 9:00–18:00 / Sáb 9:00–14:00",
  "sameAs": ["https://www.instagram.com/climatizacionesdalai/"]
}
```

### SEO On-page

- Un único `<h1>` en el Hero con keyword principal y geolocalización
- `<h2>` en cada sección del sitio
- `alt` descriptivos en todas las imágenes con keywords locales naturales
- `loading="eager"` en la imagen del Hero, `loading="lazy"` en el resto
- Densidad natural de: _Tenerife_, _Los Realejos_, _norte de Tenerife_, _Canarias_
- Sección de preguntas frecuentes (FAQ) con 6 preguntas orientadas a búsquedas reales

### Keywords objetivo

| Keyword                                           | Prioridad |
| ------------------------------------------------- | --------- |
| instalación aire acondicionado Tenerife           | Alta      |
| instalador aire acondicionado Tenerife norte      | Alta      |
| aire acondicionado Los Realejos                   | Alta      |
| aire acondicionado La Orotava / Puerto de la Cruz | Alta      |
| presupuesto aire acondicionado Tenerife           | Media     |
| empresa climatización Tenerife                    | Media     |

---

## Diseño y UX

### Paleta de colores

| Token          | Valor     | Uso                                |
| -------------- | --------- | ---------------------------------- |
| `--blue`       | `#1B3A8A` | Color corporativo principal        |
| `--blue-dark`  | `#0F1F4D` | Fondos de sección oscuros          |
| `--orange`     | `#F97316` | Acento — CTAs y detalles puntuales |
| `--white`      | `#FFFFFF` | Fondo principal y texto sobre azul |
| `--gray-light` | `#F8F9FA` | Fondos de secciones alternas       |
| `--gray-text`  | `#4B5563` | Texto secundario                   |

### Tipografía

- **Titulares:** Manrope 700/800 — fuerte, técnico, confianza profesional
- **Cuerpo:** Inter 400/500 — legible, neutro, contrasta con Manrope

### Responsividad

- Mobile-first
- Breakpoint principal: `768px`
- Breakpoint secundario: `1024px` (tablets)
- Breakpoint extra pequeño: `480px`

### Interacciones

- Scroll reveal con `IntersectionObserver` — elementos y grupos con stagger
- FAQ accordion con animación de altura suave
- Nav sticky con `backdrop-filter: blur` y sombra al hacer scroll
- Menú hamburguesa animado en móvil
- Botón flotante de WhatsApp con animación de pulso
- `prefers-reduced-motion` respetado en todas las animaciones

---

## Conversión

| Elemento             | Comportamiento                          |
| -------------------- | --------------------------------------- |
| CTA principal Hero   | Abre WhatsApp con mensaje precargado    |
| CTA secundario Hero  | Scroll suave a #servicios               |
| Botones de servicios | Abre WhatsApp con mensaje precargado    |
| Sección Cobertura    | CTA a WhatsApp                          |
| Sección Contacto     | WhatsApp + teléfono + email + Instagram |
| Botón flotante       | Siempre visible, abre WhatsApp          |

---

## Comandos

```bash
# Instalar dependencias
pnpm install

# Servidor de desarrollo
pnpm dev

# Build de producción
pnpm build

# Previsualizar el build
pnpm preview
```

---

---

_Desarrollado por [Matus Behun](mailto:matusbehun03@gmail.com)_
