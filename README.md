# Testing-Resources

Wiki de testing organizada como vault de [Obsidian](https://obsidian.md). Ábrela con **Obsidian → Open folder as vault** sobre la raíz de este repo y empieza por [[Home]].

## Estructura

| Ruta | Uso |
|---|---|
| `00-Inbox/` | Documento crudo recién adjuntado, antes de procesarlo |
| `Areas/<Área>/` | Una carpeta por área: nodo principal `<Área>.md` + una nota `Cap. N - <Título corto>.md` por capítulo de contenido |
| `Índice de términos.md` | Glosario transversal de todas las áreas, con dónde se usa cada término |
| `Referencias/` | Fuentes de consulta completas (glosarios, normas); quedan fuera del grafo y no son áreas |
| `90-Plantillas/` | Plantillas de Obsidian: `Nota.md` (nodo principal) y `Capitulo.md` (sub-nodo de capítulo) |
| `99-Adjuntos/` | Imágenes y archivos embebidos |

## Flujo para alimentar la wiki

1. Deja el documento en `00-Inbox/`.
2. Crea `Areas/<Área>/`: **1 documento = 1 nodo principal + 1 sub-nodo por capítulo de contenido**. Usa `Nota.md` para el nodo principal y `Capitulo.md` para cada capítulo.
3. La introducción, las referencias y los apéndices no tienen nota propia: se condensan en el nodo principal. El nodo principal lleva solo una vista previa de cada capítulo, no su contenido.
4. Agrega los términos al `Índice de términos.md`: los nuevos con su definición y "Usado en"; los existentes, ampliando "Usado en" con los capítulos del área nueva. Si el término existe en una referencia de `Referencias/` (p. ej. [[Referencias/Glosario ISTQB 4.8.1]]), toma de ahí la definición oficial y enlaza su entrada.
5. En el nodo principal, agrega en `## Relaciones` solo los enlaces con dependencia real, cada uno con su motivo.
6. Agrega el área a `Home.md` y borra el original del Inbox.

## Reglas del grafo

- **1 documento = 1 nodo principal + sub-nodos por capítulo.** No se crean notas auxiliares, de concepto ni de categoría fuera de ese esquema.
- **Cada capítulo enlaza a su nodo principal** (propiedad `area` y línea "Parte de").
- **Enlaces entre capítulos solo cuando la fuente los cita** ("ver apartado 4.3", "véase el capítulo 1"). Nada de enlaces especulativos.
- **El material de referencia sin capítulos (glosarios, normas) va a `Referencias/`, no a `Areas/`.** Es fuente de consulta, no un área; sus términos pasan al índice solo cuando un área los usa.
- **El índice de términos y Home viven fuera de `Areas/`**, así no aparecen en el grafo ni se convierten en nodos centrales artificiales.
- **Enlaces con ruta completa y alias**: `[[Areas/<Área>/Cap. N - <Título>|capítulo N]]`, para evitar colisiones de nombres entre áreas.
- **Nada de enlaces a notas que no existen.** Un `[[wikilink]]` sin destino crea un nodo fantasma. Si el área relacionada aún no está, la relación se agrega cuando llegue su documento.
- **Toda relación lleva su motivo**: `- [[Areas/Pruebas de integración/Pruebas de integración|Pruebas de integración]]: la regresión reutiliza sus casos`. Si no se puede escribir el motivo, no hay relación.
- **Relaciones en ambos sentidos cuando aplique**: al crear un área nueva se revisan las existentes por si deben enlazarla.
- El grafo (`.obsidian/graph.json`) muestra solo `Areas/`, sin tags, adjuntos ni enlaces sin resolver.

## Convenciones

- **Nombre de archivo:** el nombre del área en español para el nodo principal (`Pruebas de regresión.md`) y `Cap. N - <Título corto>.md` para los capítulos, sin `: ? * " < > |`.
- **Frontmatter:** nodo principal con `tags: [area]`, `fuente` (documento de origen), `creado`; capítulo con `tags: [capitulo]`, `area`, `capitulo`, `paginas`, `duracion`.
- **Datos:** nada de credenciales, cadenas de conexión ni datos personales en ejemplos; usa marcadores (`<USUARIO>`, `<TOKEN>`).
