<p align="center">
  <img src="assets/logo-sereno.svg" width="96" height="96" alt="Logo de Sereno">
</p>

<h1 align="center">Sereno</h1>

<p align="center">
  Landing page de Sereno, una extensión de Chrome que detecta URLs de phishing antes de que la página cargue.<br>
  <a href="https://sereno-phishing.github.io/sereno-landing/"><strong>sereno-phishing.github.io/sereno-landing</strong></a>
</p>

## Sobre el proyecto

Sereno es el artefacto de la tesis *Extensión de navegador basado en ensemble Stacking y caché dinámico para la detección de URLs de phishing en tiempo real en e-commerce del sector servicios* (Ingeniería de Software, Universidad Peruana de Ciencias Aplicadas, 2026).

La extensión consulta un servidor que primero revisa un caché Redis de URLs ya marcadas como phishing. Si la URL no está ahí, un ensemble Stacking (Random Forest, XGBoost y LightGBM como modelos base, regresión logística como meta-modelo) emite el veredicto a partir de características léxicas y de host.

La extensión está en desarrollo. Esta página presenta el concepto; los sitios y datos que aparecen en las pantallas son de ejemplo, y las cifras de la sección de metas son objetivos de validación, no resultados.

## Contenido de la página

- Hero con las pantallas reales de la extensión (wireframes de Figma) en secuencia: evaluación pendiente, sitio seguro, advertencia y detalle del veredicto.
- Comparación a escala entre la vida media de una URL de phishing (5.46 h) y el tiempo de inclusión en listas negras (4.5 días), según Lee et al. (2025).
- Recorrido con scroll: cada paso cambia la pantalla fija de la derecha.
- Diagrama del flujo interno: caché Redis, rasgos de la URL, tres modelos base y meta-modelo.
- Galería del popup (historial, primer uso, estado, filtrar, borrar) y pantallas de administración (métricas, política por dominio, caché).
- Privacidad: qué se guarda (hash y dominio) y qué no, con cálculo del hash en el navegador.
- Metas de validación, origen del nombre y preguntas frecuentes.

## Idiomas y temas

- Español e inglés con el selector ES / EN. La primera visita usa el idioma del navegador y luego recuerda la elección.
- Tema oscuro y tema claro. El claro usa la paleta de la extensión (índigo `#4F46E5` sobre fondos claros). Por defecto sigue el tema del sistema.

## Estructura

```
.
├── index.html              # Página completa (HTML, CSS y JS sin dependencias)
├── assets/
│   ├── logo-sereno.svg     # Logo oficial, exportado desde Figma
│   └── screens/            # Pantallas de los wireframes de Figma (PNG)
└── .nojekyll
```

## Verla en local

No requiere compilación. Basta con abrir `index.html` en el navegador o servir la carpeta:

```bash
python -m http.server 8000
```

y entrar a `http://localhost:8000`.

## Publicación

Se publica con GitHub Pages desde la rama `main`, carpeta raíz. Cada push a `main` actualiza el sitio.

## Autores

- Andrés Torres García
- Sebastián Lobato Pozo

Asesora: Rosa Andrea Félix Corrales.
