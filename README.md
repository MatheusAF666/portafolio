# 🎯 Portafolio Profesional - Vue.js + JSON Editable

Un portafolio moderno, responsivo y completamente personalizable para desarrolladores y profesionales del tech. Construido con Vue.js 3, alimentado por un archivo JSON editable.

## ✨ Características Principales

✅ **100% Personalizable** - Edita `src/data/portfolio.json` para cambiar TODO el contenido  
✅ **Responsivo** - Mobile-first: 360px → 1440px  
✅ **Moderno y Limpio** - Diseño profesional con animaciones sutiles  
✅ **SEO Optimizado** - Meta tags, Open Graph, estructura semántica  
✅ **Accesible** - WCAG AA compliant  
✅ **Rápido** - Optimizado para performance  

---

## 📋 Secciones Incluidas

1. **Hero** - Avatar + nombre + rol + tagline + CTAs
2. **Sobre Mí** - Bio + valores diferenciales
3. **Habilidades** - Grid de skills con iconos y niveles
4. **Experiencia** - Timeline visual con logros cuantificados
5. **Proyectos** - Galería con imágenes, demo, repo links
6. **Formación** - Educación y certificaciones
7. **Contacto** - Email + redes sociales

---

## 🚀 Inicio Rápido

### 1. Instalar dependencias
```bash
npm install
```

### 2. Iniciar servidor de desarrollo
```bash
npm run dev
```

Abre [http://localhost:5173](http://localhost:5173)

### 3. Personalizar contenido

**Edita `src/data/portfolio.json`:**

```json
{
  "profile": {
    "name": "Tu Nombre",
    "role": "Tu Rol",
    "tagline": "Tu lema breve",
    "avatar": "https://url-a-tu-foto.jpg",
    "email": "tu@email.com",
    "bio": "Tu biografía..."
  }
}
```

**¡Listo!** Los cambios se ven al instante.

---

## 📝 Editar Contenido - Guía Completa

### Campos en `portfolio.json`

#### Profile (Perfil)
```json
{
  "name": "Juan Pérez",
  "role": "Full Stack Developer",
  "tagline": "Transformo ideas en soluciones escalables",
  "avatar": "https://via.placeholder.com/200x200",
  "email": "juan@example.com",
  "bio": "Párrafo sobre ti...",
  "bio2": "Segundo párrafo sobre tu enfoque..."
}
```

#### Stats (Métricas Destacadas)
```json
{
  "stats": [
    { "number": "5+", "label": "Apps Publicadas" },
    { "number": "20+", "label": "Proyectos" },
    { "number": "15+", "label": "Clientes" }
  ]
}
```

#### Skills (Habilidades)
```json
{
  "skills": [
    {
      "name": "Vue.js",
      "level": "Avanzado",
      "category": "Frontend",
      "icon": "💚"
    },
    {
      "name": "Laravel",
      "level": "Avanzado", 
      "category": "Backend",
      "icon": "🔴"
    }
  ]
}
```

**Niveles:** Avanzado, Intermedio, Básico

#### Experience (Experiencia)
```json
{
  "company": "Tech Startup XYZ",
  "role": "Full Stack Developer",
  "period": "2022 - Presente",
  "description": "Resumen del rol",
  "achievements": [
    "Aumenté velocidad de carga 45% mediante optimizaciones React",
    "Implementé JWT auth reduciendo vulnerabilidades de seguridad",
    "Lideré migración de jQuery a Vue.js en 8 páginas"
  ]
}
```

**Tip:** Usa números cuantificables (%, tiempo, dinero)

#### Projects (Proyectos)
```json
{
  "id": 1,
  "title": "Blog Profesional",
  "description": "Plataforma de blogging con panel admin...",
  "role": "Full Stack (80% Frontend, 20% Backend)",
  "technologies": ["Vue.js 3", "Laravel 10", "MySQL"],
  "image": "https://via.placeholder.com/600x400",
  "metrics": {
    "label": "Resultado",
    "value": "+150% usuarios en primer mes"
  },
  "learnings": "Implementé infinite scroll y caché Redis...",
  "demoUrl": "https://blog-demo.example.com",
  "repoUrl": "https://github.com/username/blog"
}
```

**Requisitos:**
- Mínimo 3 proyectos
- Imagen: 600×400px
- Demo y Repo: opcionales

#### Education (Formación)
```json
{
  "institution": "Universidad / Plataforma",
  "title": "Grado / Certificado",
  "year": "2020",
  "certificateUrl": "https://example.com/cert"
}
```

#### Contact (Contacto)
```json
{
  "email": "tu@email.com",
  "linkedin": "https://linkedin.com/in/username",
  "github": "https://github.com/username",
  "twitter": "https://twitter.com/username",
  "cv": "/documents/CV-2024.pdf"
}
```

---

## 🎨 Personalizar Colores

En `src/views/Home.vue`, busca:

```css
:root {
  --primary: #0f172a;      /* Títulos - Azul oscuro */
  --accent: #0ea5e9;       /* Botones - Azul cyan */
  --background: #f8fafc;   /* Fondos - Gris claro */
  --text: #1e293b;         /* Texto - Gris oscuro */
}
```

**Ejemplos de paletas:**
- Verde: `--accent: #10b981`
- Púrpura: `--accent: #a855f7`
- Rojo: `--accent: #ef4444`

Cambia y ¡todos los colores se actualizan automáticamente!

---

## 📦 Build para Producción

```bash
npm run build
```

Genera carpeta `dist/` lista para desplegar.

---

## 🌐 Desplegar en Netlify

### Opción 1: Conectar GitHub (Recomendado)

1. **Sube a GitHub:**
```bash
git init
git add .
git commit -m "initial portfolio"
git remote add origin https://github.com/username/portafolio.git
git push -u origin main
```

2. **En Netlify:**
   - Ve a [netlify.com](https://netlify.com)
   - "New site from Git"
   - Conecta tu repo
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Deploy

**Bonus:** Cada push a GitHub = rebuild automático

### Opción 2: Arrastra y Suelta

1. `npm run build`
2. Arrastra carpeta `dist/` a [Netlify](https://app.netlify.com/drop)
3. ¡Online en 30 segundos!

---

## 🌐 Desplegar en Vercel

### Opción 1: Conectar GitHub

1. Sube a GitHub (ver pasos arriba)
2. Ve a [vercel.com](https://vercel.com)
3. "New Project" → Importa repo → Deploy

Tu sitio estará en: `https://portafolio-random.vercel.app`

### Opción 2: CLI

```bash
npm i -g vercel
vercel
```

---

## 📱 Puntos de Quiebre Responsivos

- **480px** - Mobile
- **768px** - Tablet
- **1024px** - Laptop
- **1440px** - Desktop grande

---

## 🔧 Estructura de Carpetas

```
portafolio/
├── src/
│   ├── data/
│   │   └── portfolio.json    ← EDITA AQUÍ
│   ├── views/
│   │   └── Home.vue
│   ├── App.vue
│   ├── main.js
│   └── style.css
├── public/
│   ├── documents/
│   │   └── CV-2024.pdf       ← TU CV
│   └── images/
│       └── mi-foto.jpg       ← TUS IMÁGENES
├── index.html
├── package.json
├── vite.config.js
└── README.md (tú estás aquí)
```

---

## 🐛 Troubleshooting

| Problema | Solución |
|----------|----------|
| Portfolio.json no carga | Verifica que exista `src/data/portfolio.json` |
| Imagen no aparece | Checa URL en JSON (http:// vs https://) |
| Build falla | Ejecuta `npm run build` localmente y mira errores |
| Estilos no actualizan | Recarga: `Ctrl+Shift+R` (Windows) o `Cmd+Shift+R` (Mac) |

---

## ✅ Checklist Antes de Desplegar

- [ ] Edité `portfolio.json` completamente
- [ ] Agregué avatar (250×250px)
- [ ] Añadí 3+ proyectos con imágenes
- [ ] Verifiqué enlaces (email, redes)
- [ ] Puse CV en `public/documents/`
- [ ] Probé en móvil (responsivo)
- [ ] Ejecuté `npm run build` sin errores
- [ ] Desplegué en Netlify o Vercel

---

## 📚 Recursos Útiles

- [Vue.js Docs](https://vuejs.org/)
- [Vite Docs](https://vitejs.dev/)
- [Coolors - Paletas](https://coolors.co/)
- [Squoosh - Optimizar imágenes](https://squoosh.app/)
- [Favicon Generator](https://favicon.io/)

---

**¡Listo para compartir!** Despliega y muestra tu portafolio al mundo.  
Actualiza `portfolio.json` cuando tengas nuevos proyectos o habilidades. 🚀

---

*Última actualización: Febrero 2024*
