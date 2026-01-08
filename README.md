# Blog personal en Jekyll

Este repo es una base sencilla para GitHub Pages con un tema zen.

## Arranque rapido

1. Cambia `title`, `description`, `url` y `author` en `_config.yml`.
2. Edita `about.md`.
3. Sube el repo a GitHub y activa Pages (branch `main`, carpeta `/`).

## Desarrollo local (opcional)

```bash
bundle install
bundle exec jekyll serve
```

## Importar desde WordPress

Tienes dos rutas. La mas completa es WXR (exportacion de WordPress), que trae categorias, etiquetas y adjuntos.

### Opcion A: Archivo WXR (recomendada)

1. En WordPress: Herramientas → Exportar → Todo el contenido.
2. Guarda el `.xml` en este repo (por ejemplo `import/wordpress.xml`).
3. Instala la gema de importacion y ejecuta:

```bash
gem install jekyll-import
jekyll import wordpress \
  --source import/wordpress.xml \
  --no-fetch-images false
```

Esto crea entradas en `_posts/` con categorias y etiquetas. Las imagenes se descargan al ejecutarse (requiere red).

### Opcion B: RSS/Atom

Si solo tienes un RSS, se puede convertir con:

```bash
gem install jekyll-import
jekyll import rss --source https://tu-blog.com/feed/ 
```

Esto importara posts y etiquetas si vienen en el feed, pero puede perder categorias y adjuntos.

## Notas sobre imagenes

- Si tienes muchas imagenes, es mejor usar la exportacion WXR y permitir descarga de adjuntos.
- Otra alternativa es copiar manualmente `wp-content/uploads` a `assets/uploads/` y ajustar rutas.

## Limpieza

Cuando tengas tus entradas reales, borra el ejemplo en `_posts/2024-01-01-bienvenido.md`.
