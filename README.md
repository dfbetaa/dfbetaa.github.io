# Portfolio + CV — David Betancourth

Dos archivos. El CV master en formato Tec, y el portafolio virtual listo para deploy.

---

## 1. CV maestro (`CV_Master_David_Betancourth.docx`)

CV en formato Tec de Monterrey, 4 páginas, listo para tailoring por aplicación.

Secciones (en orden):

- Professional Profile
- Education (Hull + Tec, con relevant coursework para cada uno)
- Professional Experience (Quickline Social Values Intern, SAIMT President, IEEE Chair, Peer Mentor)
- Data Science & AI Projects (Whisper API, Video Game Sales, CNN Emergency Vehicles, Census, CSV-to-JSON)
- Industrial & Automation Projects (ABB, Schneider, MIT/KUKA, John Deere DAMM, John Deere Thermal, Carrier)
- Skills & Languages
- Certifications & Continuing Education

Tipografía: Calibri 10pt body, Fraunces feel mantenido en headers con el navy `#0B3D5C` como color institucional. Bullets con cuadritos navy en lugar de puntos. Diseño limpio, ATS-friendly pero con personalidad visual.

**Cómo usar este CV master:**

1. Es el "padre" del que se derivan todas las versiones tailored. No lo mandas tal cual.
2. Para cada aplicación, hacés copia y recortás: típicamente 1 página, dejando solo los proyectos y skills más relevantes al puesto.
3. Si la aplicación es consulting → priorizá las métricas de negocio (ROI, throughput, % reduction). Si es ML/AI → priorizá los DS projects arriba. Si es industrial → invertí el orden de las secciones de proyectos.

---

## 2. Portafolio virtual (`index.html`)

Single-file portfolio. Todo el HTML, CSS y JS en un solo archivo. Sin dependencias de build, sin npm, sin framework. Solo Google Fonts vía CDN.

### Stack visual

- **Display:** Fraunces (serif variable, soft optical sizing)
- **Body:** Manrope
- **Mono:** JetBrains Mono (para números, tags, labels técnicos)
- **Paleta light:** cream `#F4EFE6` / ink `#0E1216` / navy `#0B3D5C` / burnt orange `#C45D3A`
- **Paleta dark:** ink `#0E1216` / cream `#F4EFE6` (invertido), navy y orange ajustados para contraste

### Funcionalidades

- Hero animado con stagger reveal al cargar
- About en grid asimétrico
- Work section con filtros: All / Data Science & AI / Industrial & Automation / Featured
- Cards de proyecto expandibles (click para abrir bullets + métricas)
- Timeline de experience
- Skills agrupados por dominio
- Contact section
- **Dark mode toggle** (persiste en localStorage)
- Scroll reveal en cada sección (IntersectionObserver)
- Mobile responsive (breakpoints en 900px y 720px)

---

## 3. Deployment — GitHub Pages (recomendado, gratis, 5 minutos)

Tu CV ya apunta a `dfbetaa.github.io`, entonces necesitás crear ese repo específicamente.

```bash
# 1. Creá un nuevo repo en GitHub con este nombre EXACTO:
#    dfbetaa.github.io
#    Public. Sin README.

# 2. En tu compu, en una carpeta vacía:
git init
git branch -M main
git remote add origin https://github.com/dfbetaa/dfbetaa.github.io.git

# 3. Copiá el index.html a esa carpeta

# 4. Push:
git add index.html
git commit -m "Initial portfolio"
git push -u origin main
```

A los 30-60 segundos, el sitio está vivo en **https://dfbetaa.github.io**

### Custom domain (opcional, más profesional)

Si querés un dominio propio (ej. `davidbetancourth.com`):

1. Comprá el dominio en Namecheap, Cloudflare Registrar, o Google Domains (~$12/año)
2. En el repo `dfbetaa.github.io`, agregá un archivo llamado `CNAME` con una sola línea: `davidbetancourth.com`
3. En tu registrar, configurá los DNS records:
   - Type: `A`, Host: `@`, Value: `185.199.108.153`
   - Type: `A`, Host: `@`, Value: `185.199.109.153`
   - Type: `A`, Host: `@`, Value: `185.199.110.153`
   - Type: `A`, Host: `@`, Value: `185.199.111.153`
   - Type: `CNAME`, Host: `www`, Value: `dfbetaa.github.io`
4. En el repo en GitHub → Settings → Pages → Custom domain → poné `davidbetancourth.com` y marcá "Enforce HTTPS"
5. Actualizá el link del portfolio en tu CV master

---

## 4. Alternativas de hosting

Si no querés usar GitHub Pages:

- **Netlify:** arrastrás el `index.html` a netlify.com/drop → URL gratis al toque
- **Vercel:** `vercel deploy` desde CLI, 1 minuto
- **Cloudflare Pages:** similar a Netlify, también gratis

Todas dan HTTPS, CDN global, y deploys automáticos si conectás Git.

---

## 5. Mantenimiento

Cuando termines un proyecto nuevo (ej. la disertación de la MSc, o algún proyecto del Social Values Intern), agregalo en dos lugares:

**En el portfolio (`index.html`):** buscá el array `PROJECTS` cerca del final del archivo y agregá un objeto nuevo con la misma estructura:

```javascript
{
  id: "tu-id-corto",
  cat: "ai",                    // "ai" o "industrial"
  featured: true,                // o false
  title: "Nombre del proyecto",
  client: "Cliente · Modulo o contexto",
  year: "Mes 2026",
  tags: ["Tag1", "Tag2", "Tag3"],
  summary: "Resumen de 1-2 líneas para la vista colapsada.",
  bullets: [
    "<strong>Verbo:</strong> qué hiciste, herramienta, resultado medible.",
    "<strong>Otro verbo:</strong> ...",
    "<strong>Otro:</strong> ..."
  ],
  metrics: [
    { value: "X", suffix: "%", label: "Métrica 1" },
    { value: "Y", label: "Métrica 2" },
    { value: "Z", label: "Métrica 3" }
  ]
}
```

**En el CV master:** abrís el `.docx`, copiás el bloque de otro proyecto similar, lo modificás. Mantené el formato: header con título + fecha alineada derecha, subheader con cliente/módulo en itálica, 3 bullets con verbo en bold.

---

## 6. Checklist antes de aplicar a tu próximo puesto

- [ ] Verificá que `dfbetaa.github.io` carga bien en mobile (abrí desde el celular)
- [ ] Probá el dark mode toggle
- [ ] Tappeá un proyecto, confirmá que se expande
- [ ] Filtros funcionan (All / AI / Industrial / Featured)
- [ ] CV master tiene la fecha de "Expected Graduation" actualizada si cambia algo
- [ ] El link del portfolio en el CV apunta al dominio correcto

---

Cualquier ajuste de copy, paleta, agregar/quitar secciones, agregar imágenes de proyectos o un PDF embedido del CV en el portfolio: avisame y lo iteramos.
