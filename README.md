# Esteban4Dev — Portafolio

Portafolio personal de **Esteban4Dev**, Full Stack Developer y Ethical Hacker, estudiante de Ingeniería en Conectividad y Redes. Es una página estática, bilingüe (ES/EN), que muestra mis proyectos, certificaciones de Cisco, formación, experiencia y habilidades.

🔗 **Sitio en vivo:** https://me.esteban4dev.workers.dev/

## Características

- **Bilingüe (ES / EN)** con selector en el menú. Detecta el idioma del navegador y recuerda la elección.
- **Estado de Discord en tiempo real** (conectado, ausente, no molestar, qué escucha en Spotify o a qué juega), usando la API pública de [Lanyard](https://github.com/Phineas/lanyard).
- **Fondo animado de red** en el hero, dibujado con `<canvas>`. Se detiene si el sistema tiene activado "reducir movimiento".
- **Secciones:** Sobre mí, Proyectos, Certificaciones, Trayectoria (formación y experiencia), Habilidades y Contacto.
- **Responsive**, con menú desplegable en móvil, y con estilos de foco visibles y atributos `aria` para accesibilidad.
- **Sin dependencias ni paso de compilación:** todo vive en un solo archivo.

## Tecnologías

| Parte | Tecnología |
| --- | --- |
| Estructura y estilos | HTML5 y CSS3 (variables CSS, grid, flexbox) |
| Lógica | JavaScript vanilla |
| Tipografías | Space Grotesk, Inter e IBM Plex Mono (Google Fonts) |
| Estado de Discord | API de Lanyard |
| Hosting | Cloudflare Workers |

## Estructura del repositorio

```
.
├── index.html   # Página completa: HTML, CSS y JavaScript
└── README.md
```

## Ejecutar en local

No necesita instalar nada. Puedes abrir `index.html` directamente en el navegador, o levantar un servidor estático desde la carpeta del proyecto:

```bash
python3 -m http.server 8000
```

Luego entra a `http://localhost:8000`.

## Cómo editar el contenido

### Textos y traducciones

Los textos viven en el objeto `I18N` (al final de `index.html`), con una sección `es` y otra `en`. En el HTML, cada elemento traducible usa `data-i18n="clave"` (o `data-i18n-html` si lleva etiquetas). Si agregas un texto nuevo, crea la misma clave en **ambos** idiomas.

### Agregar un proyecto

1. Copia una tarjeta `.proj-card` dentro de la sección `#proyectos`.
2. Cambia el título y los enlaces.
3. Agrega la descripción como `projects.<nombre>` en `es` y en `en`.

### Agregar una certificación

Copia una tarjeta `.cert-card` dentro de `#certificaciones`. Para enlazar la verificación en Credly, agrega dentro de la tarjeta:

```html
<a class="cert-verify" href="URL_DE_CREDLY" target="_blank" rel="noopener" data-i18n="certs.verify">Verificar ↗</a>
```

Los módulos del curso **Hacker ético** están en el arreglo `HACKER_MODULES` (cada uno con su texto en español e inglés).

### Habilidades

Se generan desde el arreglo `SKILLS` en el JavaScript. Cada grupo tiene su nombre en `es` y `en`, y una lista de pares `[español, inglés]`.

### Colores

Los colores y tipografías están como variables CSS al inicio de la hoja de estilos (`:root`). El color de acento es `--accent`.

### Estado de Discord

Cambia la constante `DISCORD_ID` en el script por tu ID de usuario de Discord. Lanyard solo funciona si tu cuenta está en [su servidor de Discord](https://discord.gg/lanyard). Si la API no responde, la página muestra "estado de discord no disponible" y sigue funcionando normal.

## Despliegue

Al ser un sitio estático, funciona en cualquier hosting estático (Cloudflare, GitHub Pages, Netlify, Vercel). Actualmente está publicado en Cloudflare Workers: para actualizarlo basta con reemplazar `index.html` y volver a desplegar.

## Contacto

- GitHub: [Esteban4Dev](https://github.com/Esteban4Dev)
- LinkedIn: [esteban-undefined-54957844a](https://www.linkedin.com/in/esteban-undefined-54957844a/)
- Email: esteban4dev@tutamail.com · estebvan4dev@gmail.com
- Discord: `0x400804838f`
