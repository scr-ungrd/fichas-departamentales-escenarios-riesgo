# Portal de Fichas Departamentales de Riesgo — Quarto site

Landing page (Quarto static site) for UNGRD's departmental risk-characterization
sheets. Live at https://scr-ungrd.github.io/fichas-departamentales-escenarios-riesgo/
(repo: `scr-ungrd/fichas-departamentales-escenarios-riesgo`).

## Design system (2026-08-02 redesign)

This site's visual language was brought in line with its sibling site
`catalogo-scr` (`/Users/mauricio/Documents/Data-science-local/SCR/catalogo-scr/`,
own CLAUDE.md there) — same institution, same brand manual, meant to read as
one system:

- **Typography switched from Lato/Roboto (Google Fonts) to Helvetica
  Neue/Arial.** The UNGRD brand manual only allows Helvetica (alt. Arial/
  Calibri) — the Google Fonts import was a pre-existing non-compliance,
  not a deliberate choice, and is now removed.
- **Navbar is the same translucent light "masthead" as catalogo-scr, in
  both color modes.** `images/logo-ungrd.png` has its wordmark baked in as
  dark navy on transparent — no reversed/white version exists — so the bar
  can't go dark in dark mode without repeating the illegible-logo problem
  catalogo-scr already hit and fixed. Nav-link colors are hardcoded hex
  (`#232A60` / `#E54D23` / `#BF3D1A`, this site's own palette), not
  swapped by the dark-mode CSS variables, for the same reason documented
  in catalogo-scr's CLAUDE.md.
- **Hero uses catalogo-scr's light/contained pattern** (badge + title +
  description + stats row + cover image), replacing the previous
  full-bleed dark-gradient hero with its own CTA button. The stats shown
  (`1` ficha disponible / `32` departamentos de Colombia) are the only
  content change beyond re-theming — factual, not fabricated: 32 is the
  target scope stated in `README.md`.
- Kept this project's own color tokens (`--ungrd-blue: #232A60`,
  `--ungrd-orange: #E54D23`, etc.) — deliberately did **not** overwrite them
  with catalogo-scr's literal hex values. The two sites share a design
  *pattern*, not a single palette; each already had its own on-brand
  secondary color before this redesign.

## Scope: only Córdoba is live, by design

The portal targets all 32 departments (see `README.md`), but only Córdoba
has a published ficha and an active card. `images/fichas/` also has
`antioquia-portada.png` and `cundinamarca-portada.png`, and the old
`custom.scss` had `.dept-card--draft` / `.dept-card--soon` variants for
them — but the actual markup only ever rendered Córdoba (an earlier commit,
"simplify home page", removed the rest). The 2026-08-02 redesign preserved
that scope decision (explicitly asked, kept "solo Córdoba") and **removed
the now-fully-dead CSS** for the draft/soon card states, the old
full-bleed showcase section, and an unused "Metodología" section
(step-cards, region headers) that had no corresponding HTML either —
none of it was reachable from `index.qmd`. If/when more departments launch,
re-introduce a draft/soon card style deliberately rather than assuming the
old dead CSS was still correct — it predates this whole redesign.

## Deployment

GitHub Actions renders and publishes to `gh-pages` on push to `main` (same
pattern as catalogo-scr). Local dev: `quarto preview` — this repo isn't
usually running a preview server between sessions.

## Barra de navegación institucional (2026-11-23) — reemplaza la "masthead" clara

Lo que este archivo dice arriba sobre una barra clara translúcida "porque no existe
un logo UNGRD en blanco" ya no aplica: ahora existe `images/logo-ungrd-blanco.svg`
(firma UNGRD a una tinta en negativo, según el Manual de Identidad Visual UNGRD 2024,
p. 11; el relleno interior de la mano usa el azul de la barra para dejar ver el
contorno). Las cinco páginas de inicio de la SCR (HUB, Catálogo, Fichas,
Investigaciones y Cuadernos Reproducibles) comparten la misma barra, con
Cuadernos Reproducibles como modelo:

- Fondo azul `#213362` con franja amarilla `#ffcd00` de 4 px abajo, en modo claro y oscuro.
- Orden: firma UNGRD | nombre del proyecto en dos líneas (la segunda en negrita y
  subrayada) · secciones del sitio · "Acerca de" · íconos (HUB, GitHub, Traducir) ·
  buscador · botón de tema en el extremo derecho. Sin ícono de casa: el logo y el
  nombre llevan a la portada.
- El nombre se escribe `"línea 1|línea 2"` en `navbar.title` de `_quarto.yml`; un
  script al final de `_footer.html` lo parte en dos líneas.
- Los estilos están en el bloque "BARRA DE NAVEGACIÓN INSTITUCIONAL" al final de
  `custom.scss`, que se impone a la sección NAVBAR antigua (se dejó por historia).
- Pie de página: mismo modelo (azul con franja amarilla, título, descripción,
  "Este sitio" y aviso de derechos), en `_footer.html` vía `include-after-body`.
