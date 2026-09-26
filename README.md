<p align="center">
  <img src="assets/logo-sereno.svg" width="96" height="96" alt="Logo de Sereno">
</p>

<h1 align="center">Sereno</h1>

<p align="center">
  Landing page de Sereno, una extensión de Chrome que detecta URLs de phishing antes de que la página cargue.<br>
  <a href="https://andrest04.github.io/sereno-landing/"><strong>andrest04.github.io/sereno-landing</strong></a>
</p>

## Sobre el proyecto

Sereno es el artefacto de la tesis *Extensión de navegador basado en ensemble Stacking y caché dinámico para la detección de URLs de phishing en tiempo real en e-commerce del sector servicios* (Ingeniería de Software, Universidad Peruana de Ciencias Aplicadas, 2026).

La extensión consulta un servidor que primero revisa un caché Redis de URLs ya marcadas como phishing. Si la URL no está ahí, un ensemble Stacking (Random Forest, XGBoost y LightGBM como modelos base, regresión logística como meta-modelo) emite el veredicto a partir de características léxicas y de host.

La extensión está en desarrollo. Esta página presenta el concepto; los enlaces, puntajes y tiempos de la demo son datos de ejemplo, y las cifras de la sección de metas son objetivos de validación, no resultados.

## Contenido de la página

- Demo interactiva del veredicto: sitio seguro, phishing detectado por el ensemble y phishing respondido desde el caché.
- Los cuatro pasos de la evaluación, del clic al aviso.
- Comparación a escala entre la vida media de una URL de phishing (5.46 h) y el tiempo de inclusión en listas negras (4.5 días), según Lee et al. (2025).
- Funciones para usuarios y administradores.
- Privacidad: qué se guarda (hash y dominio) y qué no, con cálculo del hash en el navegador.
- Metas de validación: F1 ≥ 0.97, tiempo promedio ≤ 200 ms y SUS ≥ 68.

## Estructura

```
.
├── index.html            # Página completa (HTML, CSS y JS sin dependencias)
├── assets/
│   └── logo-sereno.svg   # Logo oficial, exportado desde Figma
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
