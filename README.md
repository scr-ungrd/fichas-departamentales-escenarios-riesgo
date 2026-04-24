# Portal de Fichas Departamentales de Riesgo · UNGRD

![Versión](https://img.shields.io/badge/Versi%C3%B3n-2026-blue?style=for-the-badge)
![Quarto](https://img.shields.io/badge/Built%20with-Quarto-00B4D8?style=for-the-badge)
![UNGRD](https://img.shields.io/badge/Instituci%C3%B3n-UNGRD-orange?style=for-the-badge)

Este repositorio contiene el código fuente del **Portal Nacional de Fichas Departamentales de Riesgo**, una herramienta técnica desarrollada por la Subdirección de Conocimiento del Riesgo de la **Unidad Nacional para la Gestión del Riesgo de Desastres (UNGRD)**.

## 📌 Descripción

El portal centraliza las fichas de caracterización de escenarios de riesgo para los 32 departamentos de Colombia. Estas fichas son documentos técnicos de referencia fundamentales para la planificación territorial y la toma de decisiones basada en el conocimiento del riesgo (Ley 1523 de 2012).

### Características Principales:
- **Visualización por Regiones:** Acceso rápido a fichas de las regiones Caribe, Andina, Pacífica, Orinoquía y Amazonía.
- **Estado de Avance:** Seguimiento en tiempo real de las fichas publicadas, en construcción y proyectadas.
- **Diseño Responsivo:** Optimizado para consulta en diversos dispositivos y alineado con la identidad visual institucional.
- **Metodología Integrada:** Explicación clara de los pasos para la caracterización de escenarios (Amenazas, Exposición, Capacidades y Priorización).

## 🚀 Tecnologías Utilizadas

- [Quarto](https://quarto.org/): Sistema de publicación científica y técnica de código abierto.
- [Sass/SCSS](https://sass-lang.com/): Para el diseño y personalización de la interfaz de usuario.
- [Bootstrap Icons](https://icons.getbootstrap.com/): Librería de iconos vectoriales.
- [HTML/JS Canvas](https://developer.mozilla.org/es/docs/Web/HTML/Element/canvas): Para elementos interactivos.

## 📂 Estructura del Proyecto

```text
.
├── _quarto.yml          # Configuración global del sitio Quarto
├── index.qmd            # Página principal del portal (Hero, Metodología, Departamentos)
├── custom.scss          # Sistema de diseño y estilos personalizados
├── images/              # Activos visuales (logos, iconos, portadas)
└── README.md            # Documentación técnica del repositorio
```

## 🛠️ Configuración y Desarrollo

### Requisitos Previos
- Tener instalado [Quarto CLI](https://quarto.org/docs/get-started/).

### Previsualización Local
Para ejecutar el portal en un servidor de desarrollo local:

```bash
quarto preview
```

### Construcción del Sitio
Para generar los archivos estáticos listos para producción:

```bash
quarto render
```

## 📄 Licencia

Este proyecto es de propiedad institucional de la **Unidad Nacional para la Gestión del Riesgo de Desastres - UNGRD**. El uso de la información técnica aquí contenida debe citar la fuente oficial.

---
**Subdirección de Conocimiento del Riesgo**
*Bogotá D.C., Colombia · 2026*
