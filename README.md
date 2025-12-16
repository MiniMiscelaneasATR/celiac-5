**Proyecto: Recetario Celíaco — Arquitectura modular (BEM + SCSS)**

- **Descripción breve:**
  Proyecto de ejemplo que organiza estilos con la metodología BEM y usa SCSS (Sass) para facilitar mantenimiento y escalabilidad. Los estilos compilados están en `ASSETS/CSS/main.css` y `index.html` ya los carga.

**Por qué elegiR BEM**
- **Claridad y alcance:** BEM (Bloque__Elemento--Modificador) hace explícito a qué componente pertenece cada clase, evitando colisiones y facilitando búsquedas.
- **Escalabilidad:** Es fácil añadir componentes o reutilizar bloques sin romper estilos existentes.
- **Colaboración:** Equipos grandes o futuros contribuidores entienden rápidamente la estructura y convención de nombres.

**Por qué elegiR SCSS (Sass)**
- **Organización por partials:** SCSS permite dividir estilos en partials (`SRC/_variables.scss`, `SRC/components/_recipe-card.scss`, etc.) para responsabilidad única y lectura sencilla.
- **Nesting y modularidad:** El anidado hace natural representar BEM en el código (`.recipe-card { &__title { ... } }`).
- **Futuro crecimiento:** Sass facilita mixins, funciones y variables Sass si luego se decide migrar desde custom properties a variables Sass.

**Estructura principal (relevante)**
- `SRC/` — Archivos SCSS fuente y partials (`SRC/main.scss` importa `SRC/_index.scss` que "@forward" los partials).
- `ASSETS/CSS/main.css` — CSS compilado listo para producción/desarrollo.
- `index.html` — Enlaza `ASSETS/CSS/main.css` y contiene la estructura HTML con clases BEM.

**Comandos útiles (Windows, `cmd.exe`)**
- Instalar dependencias:
```
npm install
```
- Compilar SCSS (legible):
```
npm run build-css
```
- Compilar SCSS minificado (producción):
```
npm run build-css-prod
```
- Watch / Auto-recompilación durante desarrollo:
```
npm start
```

**Siguientes pasos recomendados**
- Añadir `postcss` + `autoprefixer` y un paso de minificación en el pipeline de build.
- Separar más componentes si el proyecto crece (crear `SRC/components/*` adicionales).
- Añadir pruebas visuales o storybook para componentes UI si se vuelve un sistema de diseño.
