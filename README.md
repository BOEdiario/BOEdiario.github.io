# BOEdiario.github.io

## Desarrollo rápido (maquetación/diseño)

Este repo es un sitio **Hugo** con el tema **Broadsheet**. En producción, el contenido real se monta desde un repo externo (`BOEdiario/content`) vía `_external/content` (lo hace GitHub Actions). Para **maquetar en local**, este repo incluye un **contenido demo** para que `hugo server` funcione sin dependencias privadas.

### Requisitos (Arch Linux)

- **Hugo Extended** (obligatorio: SCSS/CSS pipeline del tema).
- **Dart Sass** (si tu build lo requiere; en CI se instala).

Instalación típica:

```bash
sudo pacman -S hugo
```

Si necesitas Sass en local, una opción rápida es:

```bash
sudo pacman -S dart-sass
```

Comprueba que es Extended:

```bash
hugo version
```

Debe aparecer `extended` en la salida. Si no, instala una variante “extended” equivalente para tu sistema.

### Arranque local

```bash
hugo server --config hugo.toml,hugo.dev.toml
```

Abre `http://localhost:1313/`.

### Contenido demo (para no depender de `_external/content`)

El contenido demo vive en:

- `_external/content/content/noticias/` (noticias de ejemplo)
- `_external/content/static/media/` (assets de ejemplo)

Si en tu máquina tienes el repo real de contenido, puedes clonar/colocar su estructura bajo `_external/content/` y Hugo lo usará automáticamente gracias a los mounts definidos en `hugo.toml`.