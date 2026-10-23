# escanear-web

Escáner de checklist web en Python. Le pasás una URL y verifica automáticamente varios puntos de seguridad y SEO: HTTPS, headers de seguridad, cookies seguras, robots.txt, sitemap, favicon y metadatos. Convierte una checklist manual en un chequeo automático.

## Qué verifica

**Seguridad:**
- HTTPS y redirección de http a https
- Headers de seguridad: HSTS, Content-Security-Policy, X-Frame-Options, X-Content-Type-Options
- Cookies con flags Secure y HttpOnly

**SEO y metadatos:**
- `<title>`, meta description, Open Graph (preview al compartir)

**Archivos del sitio:**
- favicon, robots.txt, sitemap.xml

No cubre lo que necesita ojo humano (contraste de colores, CTA, validación de formularios, página 404): eso se revisa a mano.

## Cómo funciona

Pide las páginas como lo haría un navegador y mira las respuestas (headers y HTML). **No hace ataques**: solo lee lo que el sitio devuelve. Úsalo en tus propios sitios o con permiso.

## Requisitos

Solo Python 3 (usa `urllib`). Necesita conexión a internet.

## Uso

```bash
python3 escanear_web.py https://ejemplo.com
python3 escanear_web.py ejemplo.com          # le agrega https:// solo
```

## Roadmap

- [x] v1: chequear HTTPS, headers, cookies, SEO y archivos del sitio
- [ ] v2: puntaje final (X de Y puntos cumplidos)
- [ ] v3: guardar un reporte a archivo
- [ ] v4: chequear varias URLs de una lista
