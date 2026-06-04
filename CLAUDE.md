# Plantilla Maestra — Presentaciones de Simuladores CompanyGame

> **Esta carpeta es una PLANTILLA.** Para una presentación nueva, cópiala completa,
> renómbrala (p. ej. `businessglobal-presentacion/`) y rellena los slides variables.
> Distribuidor: **Simuladores de Negocios Colombia** (Grupo Edutec).

## Cómo se construye una presentación nueva

1. **Copiar** esta carpeta y renombrarla con el nombre del simulador.
2. Decirle a Claude: *"Esta presentación es para el simulador **[NOMBRE]**"* y darle la
   información del simulador (manual, capturas, datos).
3. Claude **reemplaza los tokens `[[...]]`** y **rellena los slides variables**, conservando
   los slides fijos tal cual.
4. Guardar las imágenes específicas en `assets/` (portada, capturas `cm-XX.png`, `dec-XX.png`).

## Tokens a reemplazar (búscalos con `[[`)

| Token | Qué es | Ejemplo (FoodCompany) |
|-------|--------|------------------------|
| `[[SIMULADOR]]` | Nombre del simulador | FoodCompany |
| `[[SUBTITULO]]` | Subtítulo de portada | Simulador de Gestión de una Empresa del Sector Lácteo |
| `[[PARRAFO_CONTEXTO]]` | 2-3 frases de qué es | … dirige una compañía láctea … |
| `[[NIVEL]]` | Nivel / dificultad | Nivel 4 · Estratégico |
| `[[DURACION]]` | Duración | 16–32 horas |
| `[[LINEAS_PRODUCTO]]` | Badge de líneas/foco | 🥛🥣🧀 3 Líneas de Producto |
| `[[AREA_CONOCIMIENTO]]` | Área CompanyGame | Marketing y Ventas |
| `[[EMOJI]]` | Emoji de marca (cierre) | 🥛 |
| `[[SUBTITULO_*]]`, `[[TITULO_*]]`, `[[FACTORES_VALOR]]` | Títulos/subtítulos de slides variables | — |

## Estructura: 14 slides (NO cambiar la cantidad sin actualizar el contador del nav)

| # | Slide | Tipo | Notas |
|---|-------|------|-------|
| 1 | Portada + Contexto | **FIJO** (estructura) | Branding CompanyGame; cambia solo nombre/imagen vía tokens |
| 2 | Cartelera de Simuladores | **FIJO** | Usa `assets/cartelera.jpg` y `assets/avatares.png` (portafolio CompanyGame) |
| 3 | Ingreso a la Plataforma | **FIJO** | URL `plataforma.companygame.net`; idéntico en todas |
| 4 | ¿Qué es? | variable | Tarjetas `.card-grid cols4` |
| 5 | Cadena de Valor | variable | `.value-chain` + `.card-grid` |
| 6 | Producción / Insumos | variable | `.data-table` + tarjetas |
| 7 | Áreas de Decisión | variable | `.card-grid` |
| 8 | Segmentos y Competitividad | variable | `.two-col` + `.factor-accordion` |
| 9 | Cuadro de Mando | variable | `.cm-grid` (capturas `assets/cm-XX.png`) |
| 10 | Decisiones del Simulador | variable | `.dec-block` (capturas `assets/dec-XX.png`) |
| 11 | Valor de la Compañía | variable | `.factor-accordion` con % |
| 12 | Métodos de Implementación | **FIJO** | Genérico (deductivo/inductivo/mixto/alternos) |
| 13 | Preguntas Frecuentes | variable (semi) | Preguntas reutilizables; ajustar respuestas del simulador |
| 14 | Cierre / Gracias | **FIJO** | Contacto del distribuidor (email + WhatsApp + logo SDN) |

Cada slide variable trae un `<div class="reserved">` con instrucciones y un comentario
`<!-- VARIABLE · ... -->` que indica el componente recomendado.

## Componentes de estilo disponibles (ya en el CSS)

- **Tarjetas**: `.card-grid` / `.card-grid.cols4` + `.card` (variantes `bd-amber/green/teal/purple/red`)
- **Tabla**: `.data-table`
- **Flujo**: `.value-chain` + `.chain-box` (`cb-amber/green/teal`)
- **Acordeón de factores**: `.factor-accordion` + `.factor-item` (`factor-orange/amber/green/teal/purple/red/blue`)
- **Galería de informes**: `.cm-grid` + `.cm-card`
- **Bloques de decisión**: `.dec-block` (con `.dec-num`)
- **Acordeón FAQ**: `.accordion` + `.accordion-item`
- **Dos columnas**: `.two-col` · **Segmentos**: `.seg-row` · **Badges**: `.badge` (`badge-orange/green/teal/amber/purple`)
- **Lightbox** de imágenes: `onclick="openLightbox('assets/x.png','Título')"`

## Paleta (identidad CompanyGame/FoodCompany — ajustable por simulador)

```
--primary:#F58220  --primary-dark:#E06D10  --amber:#F9A825
--accent-green:#7BC143  --accent-teal:#00B4D8  --accent-purple:#9B59B6
--cg-blue:#1A5276
```
Si el simulador tiene identidad propia, cambia estas variables en `:root`.

## Datos fijos del distribuidor (no cambian entre simuladores)

- Plataforma de acceso: **https://plataforma.companygame.net/**
- Email: **fidelizacion@simuladoresdenegocios.co**
- WhatsApp: **301 790 3086** (`https://wa.me/573017903086`)
- Logo distribuidor: `assets/logo-sdn.png`

## Tecnología

HTML5 + CSS3 + JS vanilla, todo embebido en `index.html`. Sin frameworks. Navegación por
flechas/teclado/swipe ya implementada. No tocar el `<script>` salvo que cambie el nº de slides.
