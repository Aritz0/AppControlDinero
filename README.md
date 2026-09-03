# Balance — Libro Mayor Personal

App de finanzas personales (ingresos, gastos, categorías, panel con gráficos) en un solo archivo HTML, con datos sincronizados en Supabase. Ahora instalable como app en el móvil (PWA).

## Publicar en GitHub Pages

1. Sube esta carpeta completa (`index.html`, `manifest.json`, `sw.js`, `icons/`) a un repositorio de GitHub.
2. En el repo: **Settings → Pages → Source** → selecciona la rama `main` y la carpeta `/ (root)`.
3. Guarda. En 1-2 minutos tendrás una URL tipo `https://tu-usuario.github.io/tu-repo/`.
4. Abre esa URL desde el móvil. En Chrome/Safari, el navegador ofrecerá "Añadir a pantalla de inicio" o "Instalar app" — así queda con ícono propio, a pantalla completa.

## Notas

- La clave `SUPABASE_ANON_KEY` es la clave pública ("anon/publishable"), diseñada para exponerse en el cliente. La seguridad real depende de tener **Row Level Security (RLS)** activado en las tablas de Supabase para que cada usuario solo pueda leer/escribir sus propios datos.
- El service worker (`sw.js`) solo cachea el "shell" de la app (HTML, íconos) para que cargue rápido/offline; los datos siempre se piden a Supabase en vivo.
