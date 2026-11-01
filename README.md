# 🚀 Angular en GitHub Pages con despliegue automático

Proyecto de aprendizaje para publicar una página **¡Hola Mundo!** hecha con Angular en **GitHub Pages**, con **CI/CD** mediante GitHub Actions: cada `git push` a `main` compila y publica el sitio solo.

> 📘 La guía completa, paso a paso y con ilustraciones, está en [`manual-github-pages-angular.pdf`](manual-github-pages-angular.pdf).

## 🧭 Cómo funciona

```
Tu PC ──git push──▶ GitHub (main) ──dispara──▶ Actions (build) ──deploy──▶ GitHub Pages
```

1. Editas el código en Angular y haces `git push`.
2. GitHub Actions instala dependencias y ejecuta `ng build`.
3. La carpeta de salida (`dist/hola-mundo/browser`) se publica en Pages.

Sitio publicado en: `https://vlv-515.github.io/learn_github_pages_ci_cd/`

## 📚 Qué aprenderás

- Qué es GitHub Pages y qué tipo de sitios puede hospedar.
- Crear una app Angular y entender su carpeta de salida.
- Por qué existe el `base href` y cómo configurarlo.
- Activar Pages con **Source = GitHub Actions**.
- Escribir un workflow (`.github/workflows/deploy.yml`) línea por línea.
- Resolver los errores más comunes (página en blanco, 404, permisos, `npm ci`).

## 🛠️ Requisitos

| Herramienta | Versión probada |
|-------------|-----------------|
| Node.js | 22 |
| npm | 10 |
| Angular CLI | 21 |
| Git + cuenta de GitHub | — |

## ⚡ Inicio rápido

```bash
# 1. Crear la app en la raíz del repo
ng new hola-mundo --directory . --defaults --skip-git

# 2. Probar en local
ng serve   # http://localhost:4200

# 3. Compilar como lo hace el pipeline
ng build --base-href /learn_github_pages_ci_cd/
```

Luego en GitHub: **Settings → Pages → Source → GitHub Actions**, agrega el workflow del manual y haz `git push`.

> ⚠️ Si `npm install` falla con `Cannot read properties of null (reading 'edgesOut')` (bug de npm 10), crea un `.npmrc` con `legacy-peer-deps=true`. El manual lo explica.

## 🔁 Ciclo de trabajo diario

```bash
git add .
git commit -m "feat: mi cambio"
git push   # Actions compila y publica en 1-2 minutos
```

## 📄 Contenido del repositorio

| Archivo | Descripción |
|---------|-------------|
| `manual-github-pages-angular.pdf` | Manual completo en español (22 páginas) |
| `README.md` | Este archivo |

---

Hecho para aprender. ¡Que tus despliegues siempre salgan en verde! ✅
