# Guía base — Calculadora Web de Estadística Inferencial

Rol: Desarrollador Front-End Senior + experto en Estadística Inferencial. Esta guía rige todos los módulos del curso para mantener coherencia estética y de código.

## Stack (sin build, sin backend)
- HTML5 + Tailwind CSS (CDN) + JavaScript Vanilla ES6+.
- Chart.js (CDN) para gráficos; KaTeX (CDN) para fórmulas.
- 100 % del lado del cliente. Desplegable tal cual en Vercel / Netlify / GitHub Pages (archivos estáticos).

## Arquitectura
- Entrega en un único `index.html` (CSS y JS incrustados), por pedido del usuario. Router por hash (`#tamano`, `#afijacion`, …); cada tema es una `<section id="sec-...">` con su objeto JS (`S1`, `S2`, …) que expone `init / compute / summary / clear / example`.
- Utilidades compartidas al inicio del script: `readField` (validación), `fmt`, `tex` (KaTeX), `renderSteps`, `upsertChart`, `Normal` (pdf, cdf, inv). Reutilizarlas en módulos nuevos.
- Sin frameworks ni bundlers.

## UI/UX
- Dashboard minimalista, paleta académica Slate / Indigo / Blue.
- Sidebar responsiva (colapsable en móvil) para navegar módulos y temas.
- Inputs con validación en tiempo real: sin negativos donde no aplique, sin divisiones por cero, porcentajes/probabilidades en rango, mensajes de error junto al campo.
- Tarjetas KPI para resultados clave (n, Z/t crítico, estadístico de prueba, p-valor, decisión).
- Sección "Procedimiento paso a paso" con ecuaciones en KaTeX.
- Gráficos Chart.js: curvas de distribución con regiones críticas sombreadas, pastel/barras para estratos, etc.
- Botones en cada calculadora: "Copiar / Exportar resumen" y "Limpiar datos".

## Convenciones
- Interfaz y textos en español.
- Cada módulo expone la misma estructura: entradas → KPIs → gráfico → procedimiento → acciones.
