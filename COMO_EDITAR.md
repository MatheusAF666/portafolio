# 📝 Guía: Cómo Editar Tu Portafolio

Esta es una **guía paso a paso** para personalizar tu portafolio editando el archivo `src/data/portfolio.json`.

---

## 🎯 Primeros Pasos

1. **Abre el archivo:** `src/data/portfolio.json`
2. **Edita los campos** que aparecen abajo
3. **Guarda** (Ctrl+S)
4. **Recarga tu navegador** - los cambios aparecen al instante

---

## 👤 Sección PROFILE (Tu Perfil)

Este es el primer campo que la gente ve. ¡Hazlo memorable!

### Campo: `name`
**Qué cambiar:** Tu nombre completo

```json
"name": "Tu Nombre"
```

**Ejemplos:**
- "Juan Pérez"
- "María García López"
- "Carlos Martínez" 

---

### Campo: `role`
**Qué cambiar:** Tu rol / título profesional

```json
"role": "Full Stack Developer"
```

**Ejemplos:**
- "Frontend Developer"
- "Ingeniero de Software"
- "React Specialist"
- "Senior Backend Developer"

---

### Campo: `tagline`
**Qué cambiar:** Una frase corta sobre lo que haces (1 línea)

```json
"tagline": "Transformo ideas en soluciones web escalables y modernas"
```

**Ejemplos:**
- "Creando apps que resuelven problemas reales"
- "Especializado en experiencias web excepcionales"
- "Code + Design = Magic"

---

### Campo: `avatar`
**Qué cambiar:** URL de tu foto o avatar

```json
"avatar": "https://via.placeholder.com/200x200"
```

**Opciones:**
1. **Link externo (más fácil):**
   - Sube foto a [Imgur](https://imgur.com/)
   - Copia URL: `https://i.imgur.com/ABC123.jpg`
   - Pega en JSON

2. **Archivo local (avanzado):**
   - Pon imagen en `public/images/mi-foto.jpg`
   - En JSON: `"avatar": "/images/mi-foto.jpg"`

**Tamaño recomendado:** 250×250px (cuadrado)

---

### Campo: `bio` y `bio2`
**Qué cambiar:** Dos párrafos sobre ti (tono profesional)

```json
"bio": "Soy desarrollador full stack apasionado...",
"bio2": "Creo código limpio, mantenible y optimizado..."
```

**Consejos:**
- 2-3 frases cada párrafo
- Tone práctico, no demasiado formal
- Menciona tu especialidad (Vue, Laravel, React, etc.)

---

### Campo: `email`
**Qué cambiar:** Tu correo

```json
"email": "tu@email.com"
```

---

## 📊 Sección STATS (Métricas)

Tres números destacados que muestran tu experiencia. Edita los campos `number` y `label`.

```json
"stats": [
  { "number": "5+", "label": "Apps Publicadas" },
  { "number": "20+", "label": "Proyectos Completados" },
  { "number": "15+", "label": "Clientes Satisfechos" }
]
```

**Ejemplos alternos:**
- "3+ años experiencia"
- "150+ horas mentoring"
- "10 startups lanzadas"
- "+1M usuarios alcanzados"

---

## ⭐ Sección VALUES (Qué te Diferencia)

Una lista de 4 cosas que te hacen especial.

```json
"values": [
  "Código limpio y mantenible",
  "Enfoque mobile-first",
  "Optimización de performance",
  "Experiencia de usuario excepcional"
]
```

**Ejemplos:**
- "Siempre cumplo plazos"
- "Mentoría a juniors"
- "Certificado en accesibilidad web"
- "Stack moderno: Vue 3 + Laravel"

---

## 🛠️ Sección SKILLS (Habilidades)

Un grid de tus habilidades técnicas. Cada skill tiene:
- `name` - Nombre (Vue.js, Laravel, etc.)
- `level` - Nivel (Avanzado, Intermedio, Básico)
- `category` -grupo (Frontend, Backend, DevOps, Tools)
- `icon` - Emoji o símbolo 

```json
{
  "name": "Vue.js",
  "level": "Avanzado",
  "category": "Frontend",
  "icon": "💚"
}
```

**Emojis útiles:**
- Frontend: 💚 (Vue), ⚛️ (React), 🟡 (JavaScript)
- Backend: 🔴 (Laravel), 🐘 (PHP), 🗄️ (MySQL)
- DevOps: 🐳 (Docker), 📦 (Git)
- Design: 🎨 (UI/UX), 🎭 (Figma)

---

## 💼 Sección EXPERIENCE (Experiencia Laboral)

Para cada trabajo anterior, incluye:

```json
{
  "company": "Tech Startup XYZ",
  "role": "Full Stack Developer",
  "period": "2022 - Presente",
  "description": "Desarrollo de aplicaciones web escalables",
  "achievements": [
    "Aumenté la velocidad de carga en 45% optimizando componentes Vue.js",
    "Implementé sistema de autenticación JWT reduciendo vulnerabilidades",
    "Lideré migración de jQuery a Vue.js en 8 páginas"
  ]
}
```

**Cómo escribir logros:**
- Usa números: 45%, +25%, 3x más rápido
- Empieza con verbo: "Implementé", "Aumenté", "Lideré"
- Máximo 3 logros por puesto

---

## 🚀 Sección PROJECTS (Tus Proyectos)

Lo más importante. Cada proyecto necesita:

```json
{
  "id": 1,
  "title": "Blog Profesional Multiusuario",
  "description": "Plataforma completa de blogging...",
  "role": "Full Stack (80% Frontend, 20% Backend)",
  "technologies": ["Vue.js 3", "Laravel 10", "MySQL"],
  "image": "https://via.placeholder.com/600x400",
  "metrics": {
    "label": "Resultado",
    "value": "+150% usuarios en primer mes"
  },
  "learnings": "Implementé infinite scroll y caché con Redis...",
  "demoUrl": "https://blog-demo.example.com",
  "repoUrl": "https://github.com/username/blog"
}
```

**Detalles:**
- `title`: Nombre del proyecto
- `description`: Qué problema resuelve (2-3 frases)
- `role`: Tu participación (ej: "Full Stack 90%", "Solo Frontend")
- `technologies`: Stack (máx 5 tags)
- `image`: Captura de pantalla (600×400px mínimo)
- `metrics`: Número de impacto (% aumento, usuarios, dinero)
- `learnings`: Qué aprendiste técnicamente
- `demoUrl`: Link a sitio en vivo (opcional)
- `repoUrl`: Link a GitHub (opcional)

**Mínimo:** 3 proyectos
**Recomendado:** 3-6 proyectos

---

## 🎓 Sección EDUCATION (Formación)

Grados, certificados de plataformas online, etc.

```json
{
  "institution": "Universidad Tecnológica",
  "title": "Grado en Ingeniería Informática",
  "year": "2016 - 2020",
  "certificateUrl": null
}
```

**Ejemplos:**
- Grados universitarios
- Bootcamps (ej: "Bootcamp Full Stack")
- Certificados online (Udemy, Coursera, etc.)

Si tienes certificado digital, pon URL en `certificateUrl`:
```json
"certificateUrl": "https://example.com/cert/123456"
```

---

## 📞 Sección CONTACT (Contacto)

Tus redes y formas de contacto.

```json
"contact": {
  "email": "tu@email.com",
  "linkedin": "https://linkedin.com/in/username",
  "github": "https://github.com/username",
  "twitter": "https://twitter.com/username",
  "cv": "/documents/CV-2024.pdf"
}
```

**Cómo obtener URLs:**
- **LinkedIn:** Ve a tu perfil, copia URL del navegador
- **GitHub:** github.com/tuusuario
- **Twitter:** twitter.com/tuhandle
- **CV:** Sube PDF a `public/documents/CV-2024.pdf` y usa ruta `/documents/CV-2024.pdf`

---

## 🎨 Cambiar Colores

Abre `src/views/Home.vue` y busca `::root { --primary...`

```css
:root {
  --primary: #0f172a;      /* Títulos */
  --accent: #0ea5e9;       /* Botones, links */
  --background: #f8fafc;   /* Fondos */
  --text: #1e293b;         /* Texto */
}
```

**Ejemplos:**
```css
/* Verde profesional */
--accent: #10b981;

/* Púrpura moderno */
--accent: #a855f7;

/* Naranja energético */
--accent: #f97316;
```

---

## ✅ Checklist Final

- [ ] Actualizé nombre, rol, tagline
- [ ] Puse una foto en avatar
- [ ] Edité bio en 2 párrafos
- [ ] Añadí 4 skills adicionales
- [ ] Agregué experiencia laboral (mín. 2)
- [ ] Puse 3+ proyectos con imágenes
- [ ] Actualicé educación
- [ ] Verifiqué links (email, redes)
- [ ] Guardé archivo
- [ ] Recargué navegador

---

## 🚀 Próximo Paso

Una vez **gustado con el contenido**, despliega en Netlify o Vercel:

1. Ve a [netlify.com](https://netlify.com)
2. Arrastra carpeta `dist/` (después de `npm run build`)
3. ¡Online en 30 segundos!

---

¿Dudas? Lee el archivo `README.md` para guía completa. 😊
