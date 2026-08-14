# La Serie 2:7 — Contexto del proyecto y Especificación de marca

> Documento maestro de referencia para las presentaciones del discipulado
> **"La Serie 2:7 — Creciendo firmes en la familia de Dios"** (NavPress, Libro 1).
> Aplica a **todas las sesiones**. Última actualización: junio 2026.

---

## 1. Contexto del proyecto

**Qué es.** Presentaciones para guiar, sesión por sesión, el curso de discipulado *La Serie 2:7* en un **grupo virtual por Zoom**.

**Objetivo.** Que cada sesión sea **llevadera**: las diapositivas muestran solo **lo general de cada sección** (el bosquejo de alto nivel), y el líder amplía hablando. No se vuelca el texto completo del libro.

**Formato de uso.**
- El líder comparte las diapositivas en pantalla por Zoom y expone.
- Idioma: **español**.
- Versión bíblica de las citas: **NTV** (Nueva Traducción Viviente), que es la que usa el libro
  (p. ej. Col 2:7 → *"Arráiguense profundamente en él…"*).

**Entregables por sesión.**
1. **Presentación** — baraja de diapositivas en 16:9 (~14 slides).
2. **Handout** — resumen de 1 página (carta, vertical) para enviar al grupo después.

Ambos se entregan en **HTML**; el **PDF lo exporta el usuario** desde el navegador (ver §6).

---

## 2. Flujo de trabajo (cómo se arma cada sesión)

1. El usuario coloca las fotos del libro en una subcarpeta `fotos-sesion-N/`, numeradas (`1.heic`, `2.heic`, …).
2. Las fotos suelen venir en **HEIC**; se convierten a JPG para leerlas:
   ```bash
   sips -s format jpeg entrada.heic --out salida.jpg
   ```
3. Se lee el contenido y se identifica el **bosquejo** de la sesión y sus secciones principales.
4. Se aprueba la **estructura** (cuántos slides y qué va en cada uno) antes de construir.
5. Se construyen los dos HTML siguiendo esta especificación de marca.
6. El usuario revisa en el navegador y exporta a PDF con **Cmd+P**.

---

## 3. Filosofía de diseño

**Minimalismo editorial sobrio**, fiel al estilo NavPress / La Serie 2:7: papel color crema, tinta carbón, un solo color de acento (**teal**), mucho espacio en blanco, tipografía clásica. Serio, cálido y limpio — tipo cuaderno de estudio, **no** corporativo ni recargado.

Principios:
- **Un acento, no varios.** El teal manda; el dorado es un detalle ocasional.
- **Poco texto por slide.** Título grande + 3–6 puntos. El resto lo dice el expositor.
- **Legible al proyectar.** El texto debe verse bien en pantalla y por Zoom. Cuando hay poco contenido, **agranda la tipografía para llenar el espacio** en vez de dejar huecos. Tamaños mínimos de referencia para las presentaciones 16:9 (subir si sobra espacio):
  - Bullets / cuerpo: **≥ 21px** (detalle secundario ≥ 18px).
  - Listas numeradas: título de ítem **≥ 24px**, detalle **≥ 20px**.
  - Tarjetas (`.colcard`): título ≥ 25px, cuerpo ≥ 20px.
  - Filas de tabla de versículos (`.vrow`): tema ≥ 24px, cita ≥ 22px.
  - Nota / callout: ≥ 19px. Cita bíblica centrada: **≥ 36px**.
- **La Escritura es protagonista.** Los versículos van en serif, grandes y centrados.
- **Detalles discretos.** Grano de papel sutil y lavados de color muy tenues para dar textura sin distraer.

---

## 4. Especificación de marca (Brand Spec)

### 4.1 Paleta de colores

| Token | HEX | Uso |
|-------|-----|-----|
| `--paper` | `#F6F2E9` | Fondo principal (crema) |
| `--paper-2` | `#FBF8F1` | Tarjetas / superficies elevadas |
| `--ink` | `#22282A` | Texto principal (carbón) |
| `--ink-soft` | `#5A625F` | Texto secundario |
| `--ink-faint` | `#8C938E` | Etiquetas, pies de página |
| `--teal` | `#1E5B57` | **Acento principal** (títulos de sección, marcas, citas) |
| `--teal-bright` | `#2E837B` | Acento secundario / hover |
| `--teal-wash` | `#E7EEEB` | Fondos suaves (símbolos, versículo destacado) |
| `--gold` | `#B0894E` | Detalle ocasional (regla, sello, "lo más crítico") |
| `--line` | `rgba(30,91,87,.20)` | Líneas divisorias (teal) |
| `--line-soft` | `rgba(34,40,42,.12)` | Líneas tenues |

### 4.2 Tipografía

Dos familias de Google Fonts:

- **Spectral** (serif) — Escrituras, títulos de portada, sellos y números decorativos.
  Pesos: 400, 500, 600 (+ itálicas 400/500).
- **Libre Franklin** (sans) — títulos de slide, cuerpo, listas, etiquetas.
  Pesos: 400, 500, 600, 700.

```html
<link href="https://fonts.googleapis.com/css2?family=Spectral:ital,wght@0,400;0,500;0,600;1,400;1,500&family=Libre+Franklin:wght@400;500;600;700&display=swap" rel="stylesheet">
```

**Escala tipográfica (referencia):**

| Elemento | Fuente | Tamaño | Notas |
|----------|--------|--------|-------|
| Portada — sello "2:7" | Spectral 600 | 150px | |
| Portada — título | Spectral 500 | 60px | |
| Título de slide (`.title`) | Spectral 500 | 52px | (44–46px si el texto es largo) |
| Cita bíblica (`.quote`) | Spectral 400 *itálica* | 42px | centrada |
| Eyebrow / etiqueta de sección | Libre Franklin 600 | 13px | MAYÚSCULAS, `letter-spacing .24em` |
| Lead / intro | Libre Franklin 400 | 19px | |
| Ítem de lista — título | Libre Franklin 600 | 21px | |
| Ítem de lista — detalle | Libre Franklin 400 | 16.5px | |
| Bullets | Libre Franklin 400 | 18px | |
| Pie de página / running header | Libre Franklin | 11.5px | MAYÚSCULAS, `.16em` |

### 4.3 Dimensiones

- **Diapositivas:** 16:9 → **1280 × 720 px** en pantalla. Para impresión: `@page { size: 13.333in 7.5in }` (formato 16:9 estándar de PowerPoint), márgenes 0.
- **Handout:** **Carta vertical** (8.5 × 11 in), `@page { size: Letter; margin: 0 }`, con padding interno ~0.7in.
- Padding interno de slide: `74px 92px 64px`.

### 4.4 Componentes (catálogo)

Clases CSS reutilizables ya definidas en `sesion-1-presentacion.html`:

- **`.cover`** — portada: kicker, sello "2:7" gigante con regla dorada, título, "Sesión N", franja decorativa a la derecha y cita al pie.
- **`.topbar`** — encabezado corrido: "La Serie 2:7 · Sesión N" a la izquierda, sello "2:7" a la derecha.
- **`.footer`** — pie corrido: nombre del libro + nombre de la sección.
- **`.eyebrow`** — etiqueta de sección en teal con guion previo.
- **`.title`** — título grande en serif.
- **`.list` / `.item` / `.num`** — lista numerada con círculo teal (para metas, pasos, tareas).
- **`.grid` + `.bullets`** — dos columnas de viñetas (rombos teal) para listas comparativas o densas.
- **`.colcard`** — tarjeta con título serif teal (p. ej. "Qué marcar" / "Dónde empezar").
- **`.scripture` / `.quote`** — slide de versículo centrado; `.em` resalta palabras clave en teal.
- **`.marks` / `.mk`** — cuadrícula de símbolos de marcado de la Biblia (corchetes, diagonal, círculo, etc.).
- **`.vtable` / `.vrow`** — tabla tema → cita bíblica (las "5 Garantías").
- **`.callout`** — banda de color con etiqueta (teal por defecto; dorado para "lo más crítico").
- **`.steps` / `.step`** — pasos en columnas (p. ej. Ora → Reflexiona → Marca).
- **`.note`** — nota en itálica serif con borde teal a la izquierda.
- **`.closing`** — slide de cierre centrado con sello y regla dorada.

### 4.5 Detalles visuales

- **Grano de papel:** textura SVG `feTurbulence` muy tenue (`opacity ~.035`, `mix-blend-mode: multiply`) sobre cada slide.
- **Lavados de color:** dos `radial-gradient` muy suaves (teal arriba-derecha, dorado abajo-izquierda).
- **Sello "2:7":** marca recurrente en serif teal; gigante en portada/cierre, pequeño en el topbar.
- **Animación de entrada (solo pantalla):** los elementos con clase `.anim` aparecen con un *stagger* (`@keyframes rise`); se desactiva en impresión.

### 4.6 Navegación (modo pantalla)

- Flechas **← →**, barra espaciadora, `PageUp/PageDown`, `Home/End`.
- Controles en pantalla (anterior / contador / siguiente) y barra de progreso superior.
- El escenario se escala automáticamente para encajar en cualquier ventana.

---

## 5. Estructura de archivos y convención de nombres

```
Discipulado/
├── CONTEXTO-Y-MARCA.md            ← este documento
├── 1/
│   ├── fotos-sesion-1/            ← fotos HEIC del libro (insumo)
│   ├── sesion-1-presentacion.html ← diapositivas 16:9
│   └── sesion-1-handout.html      ← resumen de 1 página
├── 2/
│   ├── fotos-sesion-2/
│   ├── sesion-2-presentacion.html
│   └── sesion-2-handout.html
└── …
```

Convención: `sesion-N-presentacion.html` y `sesion-N-handout.html`, dentro de la carpeta `N/`.

---

## 6. Cómo exportar a PDF (lo hace el usuario)

> El PDF **no** se genera automáticamente; el usuario lo exporta desde el navegador para tener control total del formato.

1. Abrir el HTML en el navegador (doble clic).
2. **Cmd + P** → Destino: **Guardar como PDF**.
3. Activar **"Gráficos de fondo" / "Background graphics"** ✅ (esencial para los colores y el fondo crema).
4. Márgenes: **Ninguno**.
5. La orientación sale sola por el CSS: la **presentación en horizontal 16:9**, el **handout en vertical (carta)**.

---

## 7. Estado actual

- ✅ **Sesión 1** — `sesion-1-presentacion.html` (14 slides) + `sesion-1-handout.html`.
- ⏳ **Detalles pendientes de confirmar (Sesión 1):**
  1. Se afirmó que *"el grupo se cierra después de la sesión 2"* — confirmar redacción.
  2. Los **símbolos de marcado** se representaron con glifos aproximados (`⟋` diagonal, `⫽` paralelas al margen); ajustar si en el libro se dibujan distinto.

### Contenido de la Sesión 1 (secciones)
Portada · Bienvenida (oración + conocer al grupo) · Bosquejo · Colosenses 2:7 · Propósito de la serie (3 metas) · Cómo funciona el grupo · Leer y marcar la Biblia (por qué) · Cómo marcar (6 símbolos) · Qué y dónde leer · Ejercicio Romanos 12 · Memorización: las 5 Garantías · Cómo memorizar · Tarea para la sesión 2 · Cierre.

**Las 5 "Garantías" (paquete *Comenzando con Cristo*, Los Navegantes):**
| # | Garantía | Cita |
|---|----------|------|
| 1 | Salvación | 1 Juan 5:11-12 |
| 2 | Oración respondida | Juan 16:24 |
| 3 | Victoria | 1 Corintios 10:13 |
| 4 | Perdón | 1 Juan 1:9 |
| 5 | Guía | Proverbios 3:5-6 |
