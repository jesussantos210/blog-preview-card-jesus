# Frontend Mentor - Solución de la tarjeta de vista previa del blog

Esta es una solución al [Desafío de la tarjeta de vista previa del blog en Frontend Mentor](https://www.frontendmentor.io/challenges/blog-preview-card-ckPajId1w). Los desafíos de Frontend Mentor me ayudan a mejorar mis habilidades de codificación construyendo proyectos realistas.

## Tabla de contenidos

- [Resumen](#resumen)
  - [El desafío](#el-desafío)
  - [Captura de pantalla](#captura-de-pantalla)
  - [Enlaces](#enlaces)
- [Mi proceso](#mi-proceso)
  - [Construido con](#construido-con)
  - [Lo que aprendí](#lo-que-aprendí)
  - [Desarrollo continuo](#desarrollo-continuo)
  - [Recursos útiles](#recursos-útiles)
- [Autor](#autor)
- [Agradecimientos](#agradecimientos)

## Resumen

### El desafío

Los usuarios deberían ser capaces de:

- Ver los estados `:hover` y `:focus` para todos los elementos interactivos de la página.

### Captura de pantalla

Así es como quedó mi solución final:

![Captura de pantalla del proyecto de la tarjeta de blog](../assets/images/targeta%20de%20desafio%20jesus.png)


### Enlaces

- **Repositorio en GitHub:** [https://github.com/jesussantos210/blog-preview-card-main](https://github.com/jesussantos210/blog-preview-card-main/tree/main/my%20card)

## Mi proceso

### Construido con

- Marcado HTML5 semántico
- Propiedades personalizadas de CSS (Variables)
- CSS Flexbox (para centrar la tarjeta y alinear elementos internos)
- Git / GitHub

### Lo que aprendí

Este proyecto fue un viaje de depuración (debugging) tanto como de maquetación.

**1. El Error de Sintaxis de las Variables CSS:**
Mi lección más importante fue sobre la precisión en la sintaxis. Mi tarjeta no tenía fondo blanco, bordes ni sombra porque estaba usando paréntesis dobles en mis variables CSS, lo cual rompía el código.

```css
/* Mi error: */
.learning-card {
    background-color: var((--color-neutral-white));
}

/* La solución correcta: */
.learning-card {
    background-color: var(--color-neutral-white);
}
```

**2. La Importancia de las Rutas Relativas (../):**
 Mis imágenes (el SVG de la cabecera y el avatar) no se cargaban. El problema era la estructura de carpetas: mis archivos `index.html` y `style.css` estaban en una carpeta (my card/), pero la carpeta `assets/` estaba un nivel fuera de ella. Aprendí que (../)  es esencial para "subir un nivel" en la estructura de carpetas antes de buscar el archivo.

```html
 <img src="assets/images/img-waller.jpg" alt="...">

<img src="../assets/images/img-walle.jpg" alt="...">
```

**3. display: inline-block vs. block:**
 La etiqueta "Aprendizaje" ocupaba todo el ancho de la tarjeta. Al cambiar su estilo a display: inline-block y width: fit-content, la etiqueta se ajustó perfectamente al texto.

**4. background-image vs.`<img>`:**
 Mi primer intento de mostrar la imagen SVG usaba una etiqueta `<img>`. Cuando la ruta falló, mostró el texto alt y rompió todo el diseño. Aprendí que para imágenes decorativas, es mucho más limpio y robusto usar un `<div>` vacío y controlar la imagen desde el CSS con background-image.

**5. El Navegador Miente (Caché):** Hubo varios momentos en que mi código estaba correcto, pero los cambios no se reflejaban. Aprendí que el navegador guarda una copia "antigua" (en caché) de mi `style.css.` Usar `Ctrl + Shift + R` (Recarga Forzada) fue esencial para ver los cambios reales.

**6. Sincronización de Git (Ramas Divergentes):** Subí una imagen directamente a GitHub y luego no aparecía en VS Code. Al intentar hacer `git pull`, recibí un error de "ramas divergentes". Aprendí que primero debo hacer `commit` de mis cambios locales (
`git commit -m "..."`) y luego usar `git pull --rebase` para combinar limpiamente los cambios de GitHub con los míos.

### Desarrollo continuo ###

Quiero seguir perfeccionando mi flujo de trabajo con Git para evitar conflictos. Además, me enfocaré en implementar diseños "mobile-first" desde el inicio para asegurar que mis proyectos sean responsivos.

### Recursos útiles ###

- [`MDN Web Docs`](https://developer.mozilla.org/es/) - Fue mi principal referencia para propiedades de CSS como `var()`, `display`, y `background-image`.

- [`Guía de Git`](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Fundamentos-de-Git) - Me ayudó a entender qué significaba el error de "ramas divergentes" y cómo solucionarlo con `rebase`.

## Autor ##

- Jesús Santos

- Frontend Mentor - [jesussantos210](https://www.frontendmentor.io/profile/jesussantos210)

- GitHub - [jesussantos210](https://github.com/jesussantos210)

## Agradecimientos ##

Quiero agradecer a la comunidad de [Frontend Mentor](https://www.frontendmentor.io/home) por proporcionar desafíos tan realistas.