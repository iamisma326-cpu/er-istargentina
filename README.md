# BD IstArgentina — Mapa completo por módulos (64 tablas · 109 FKs)

Diagrama entidad-relación interactivo de la base de datos **IstArgentina** (IESTP "Argentina"),
generado con [archify](https://github.com/tt-a1i/archify) a partir del esquema real de PostgreSQL.

## Contenido

- `index.html` — visor interactivo completo (autocontenido, sin dependencias externas):
  - **64 tablas** agrupadas en 11 módulos
  - **109 FKs reales** extraídas de `information_schema`
  - Play Story con 5 capítulos (el story recorre el `focus` de cada capítulo)
  - Pan/zoom, temas claro/oscuro, export PNG/SVG/WebM, buscador

## Despliegue en Vercel

Es un sitio estático de un solo archivo: cualquier método de Vercel funciona.

### Opción A — desde GitHub (recomendado)

1. Empuja este repo a GitHub (ya está: `iamisma326-cpu/er-istargentina`).
2. En [vercel.com/new](https://vercel.com/new), importa el repo.
3. Framework preset: **Other** (no requiere build). Output directory: `./`
4. Deploy.

### Opción B — desde CLI

```bash
npm i -g vercel
vercel --prod
```

## Regeneración

El diagrama se regenera desde la BD con el script del repo origen:

```bash
python3 gen_layout_adyacencia.py   # extrae FKs, re-anneala layout, escribe JSON
node bin/archify.mjs deliver architecture er_istargentina_completa.json
```

Cualquier cambio de esquema en PostgreSQL se refleja con un solo comando.
