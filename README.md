# Blog personal en Jekyll

Este repo es una base sencilla para GitHub Pages con un tema zen.

## Arranque rápido

1. Cambia `title`, `description`, `url` y `author` en `_config.yml`.
2. Edita `about.md`.
3. Sube el repo a GitHub y activa Pages (branch `main`, carpeta `/`).

## Desarrollo local (opcional)

```bash
bundle install
bundle exec jekyll serve
```

## Importar desde WordPress

Tienes dos rutas. La más completa es WXR (exportación de WordPress), que trae categorías, etiquetas y adjuntos.

### Opción A: Archivo WXR (recomendada)

1. En WordPress: Herramientas → Exportar → Todo el contenido.
2. Guarda el `.xml` en este repo (por ejemplo `import/wordpress.xml`).
3. Instala la gema de importación y ejecuta:

```bash
gem install jekyll-import
jekyll import wordpress \
  --source import/wordpress.xml \
  --no-fetch-images false
```

Esto crea entradas en `_posts/` con categorías y etiquetas. Las imágenes se descargan al ejecutarse (requiere red).

### Opción B: RSS/Atom

Si solo tienes un RSS, se puede convertir con:

```bash
gem install jekyll-import
jekyll import rss --source https://tu-blog.com/feed/ 
```

Esto importará posts y etiquetas si vienen en el feed, pero puede perder categorías y adjuntos.

## Notas sobre imágenes

- Si tienes muchas imágenes, es mejor usar la exportación WXR y permitir descarga de adjuntos.
- Otra alternativa es copiar manualmente `wp-content/uploads` a `assets/uploads/` y ajustar rutas.

## Limpieza

Cuando tengas tus entradas reales, borra el ejemplo en `_posts/2024-01-01-bienvenido.md`.
