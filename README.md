# Presentación Slidev: Ciberseguridad + Red Team + IA

Proyecto Slidev minimalista con formato Feynman, notas laterales, tabla y animaciones.

## Requisitos

- Node.js (>= 18)
- npm

## Instalación

```bash
cd /home/javier/Documentos/GitHub/ciber-ia
npm ci
```

## Desarrollo

```bash
npm run dev
```

Abre navegador en `http://localhost:3030`.

## Exportar

```bash
npm run build
npm run export
```

El HTML generado queda en `dist/`.

## Publicar en la web (GitHub Pages)

1. Crear repo en GitHub (por ejemplo `ciber-ia`).
2. Empujar `main`:

```bash
git add .
git commit -m "Add slidev presentation"
git push origin main
```

3. Generar salida estática:

```bash
npm run build
```

4. Habilitar GitHub Pages en `gh-pages` branch (o `/docs`):

```bash
npx gh-pages -d dist
```

5. Visitar `https://<tu-usuario>.github.io/<repo>`

## Publicar en Netlify

1. Conectar repo desde Netlify.
2. Build command: `npm run build`.
3. Publish directory: `dist`.

## Recomendación de despliegue automatizado

- Añade `actions/ci.yml` para CI/CD.
- Rebuild on push to `main`.
