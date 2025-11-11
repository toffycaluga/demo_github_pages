# Landing Demo para GitHub Pages (2 versiones en ramas)

Este repositorio contiene **dos landings simples** para que practiques publicación en **GitHub Pages** y trabajo colaborativo con **Git**.  
Cada landing vive en una **rama distinta**:

- `version-1`: Landing personal **minimalista** (HTML + Bootstrap + styles.css)
- `version-2`: Landing **colorida** con sección *Hero* (HTML + Bootstrap + styles.css)

> Objetivo docente: que los estudiantes publiquen una página en GitHub Pages y comprendan el flujo con ramas, commits y merges.

---

## 🗂 Estructura del proyecto

```
landing-demo/
├── index.html
└── styles.css
```

Cada rama contiene su **propia** versión de `index.html` y `styles.css`.

---

## ✅ Requisitos previos

- Cuenta en **GitHub**.
- **Git** instalado en tu equipo.
- Un editor de texto (VSCode recomendado).

---

## 🚀 Pasos rápidos (resumen)

1) **Clona** este repo y entra a la carpeta.  
2) Cambia a la rama que quieras mostrar (`version-1` o `version-2`).  
3) **Publica** en GitHub Pages (puedes publicar desde `main` o directamente desde una rama).  
4) Verifica tu sitio en: `https://TU_USUARIO.github.io` (sitio de usuario) o `https://TU_USUARIO.github.io/NOMBRE_REPO` (sitio de proyecto).

> Abajo están los pasos detallados y dos **estrategias** de publicación: A) centralizar en `main` o B) publicar cada rama.

---

## 🧭 Paso a paso detallado

### 1. Clonar el repositorio

```bash
git clone <URL_DEL_REPO>
cd landing-demo
git status
```

### 2. Explorar ramas disponibles

```bash
git branch -a
# Deberías ver: remotes/origin/version-1 y remotes/origin/version-2
```

### 3. Revisar cada versión localmente

#### Opción 1: trabajar en la rama `version-1`
```bash
git checkout version-1
code .              # abre VSCode (opcional)
# Abre index.html en tu navegador para previsualizar
```

#### Opción 2: trabajar en la rama `version-2`
```bash
git checkout version-2
code .
# Abre index.html en tu navegador para previsualizar
```

> Consejo: Si necesitas correr un servidor local sencillo:  
> - Con Python 3: `python -m http.server 8080` y abre `http://localhost:8080`
> - Con VSCode: extensión "Live Server".

---

## 🌐 Publicación en GitHub Pages

GitHub Pages tiene **dos modalidades**:

- **Sitio de usuario**: repositorio **exactamente** con nombre `TU_USUARIO.github.io`.  
  URL: `https://TU_USUARIO.github.io`  
- **Sitio de proyecto**: cualquier otro repositorio.  
  URL: `https://TU_USUARIO.github.io/NOMBRE_REPO`

> Para clases/taller, el **sitio de proyecto** suele ser suficiente.

---

## 🧩 Estrategia A — Publicar desde `main` (recomendada para alumnos)

### A.1 Crear/usar la rama `main`
```bash
# Crea main si no existe
git checkout -b main
git push -u origin main
```

### A.2 Elegir qué landing publicar en `main`

> Si aparece un **conflicto**, resuélvelo en `index.html` y `styles.css`, guarda, `git add .`, `git commit`, y vuelve a `git push origin main`.

### A.3 Activar GitHub Pages en el repo
1. Ve a **Settings → Pages**  
2. En **Source**, elige **Deploy from a branch**  
3. Branch: `main` y **/ (root)**  
4. Guarda (Save).

### A.4 Verifica la URL
- Sitio de usuario: `https://TU_USUARIO.github.io`  
- Sitio de proyecto: `https://TU_USUARIO.github.io/NOMBRE_REPO`

> Nota: La primera publicación puede tardar 1–3 minutos. Presiona **F5** para refrescar.

---

## 🧩 Estrategia B — Publicar **una rama específica** (útil para comparar versiones)

GitHub Pages permite publicar **desde una rama distinta a `main`**.

### B.1 Publicar `version-1`
1. **Settings → Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `version-1` — **/ (root)**
4. Guarda.

### B.2 Publicar `version-2` (cambiar la fuente)
1. **Settings → Pages**
2. Cambia **Branch** a: `version-2` — **/ (root)**
3. Guarda.

> Con esta estrategia, solo una **rama a la vez** quedará pública (la que elijas en Settings).  
> Útil para mostrar rápidamente diferencias sin hacer merges.


---

## 🧪 Comandos de verificación útiles

```bash
git status           # estado de tu working tree
git branch -vv       # ramas locales con tracking
git remote -v        # orígenes configurados
git log --oneline --graph --decorate --all  # vista de historial
```

---

## 🧯 Problemas comunes (y soluciones)

- **404 en la URL de Pages**: espera 1–3 min; revisa que Source apunte a `main` (o a la rama elegida) y a **root**.  
- **Cambios no se ven**: confirma que hiciste `git push origin <rama>` y que esa rama es la fuente en Settings → Pages.  
- **Ramas no aparecen en Pages**: asegurarse de haber **hecho push** de esas ramas al remoto.  
- **Conflictos al mergear**: abre los archivos marcados, quita los marcadores `<<<<<<<`, `=======`, `>>>>>>>`, deja la versión final y haz:
  ```bash
  git add .
  git commit -m "Resolver conflictos para publicar"
  git push origin main
  ```
- **Repositorio vacío en `main`**: crea/mergea contenido, sube con `git push origin main` y reintenta.

---

## ❓FAQ

**¿Puedo publicar ambas ramas a la vez?**  
No en el mismo repositorio de Pages. Usa `main` o elige una rama por vez en Settings → Pages.

**¿Mi sitio queda público?**  
Sí. Cualquiera con la URL puede verlo.

---

⌨️ con ❤️ por [Abraham Lillo](https://github.com/toffycaluga)