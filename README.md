# Testing-Resources

Wiki de testing organizada como vault de [Obsidian](https://obsidian.md). Ábrela con **Obsidian → Open folder as vault** sobre la raíz de este repo y empieza por [[Home]].

## Estructura

| Carpeta | Uso |
|---|---|
| `00-Inbox/` | Chunks o markdown crudos recién adjuntados, sin procesar |
| `10-Fundamentos/` | Conceptos base y terminología |
| `20-Tipos-de-prueba/` | Una nota por tipo de prueba |
| `30-Herramientas/` | Frameworks, librerías, entornos |
| `40-Guias/` | Procedimientos, checklists, casos prácticos |
| `90-Plantillas/` | Plantillas de Obsidian (`Nota.md`) |
| `99-Adjuntos/` | Imágenes y archivos embebidos |

## Flujo para alimentar la wiki

1. Deja el chunk en `00-Inbox/` tal cual llega.
2. Procésalo: divídelo en notas atómicas (una idea por nota), muévelas a su carpeta y aplica la plantilla.
3. Enlaza con `[[wikilinks]]` y agrega cada nota nueva a su sección en `Home.md`.
4. Borra el chunk del Inbox cuando todo su contenido esté distribuido.

## Convenciones

- **Nombres de archivo:** título legible en español, sin prefijos numéricos (`Pruebas de regresión.md`).
- **Frontmatter:** `tags`, `estado` (`borrador` | `revisado`), `fuente`, `creado`.
- **Enlaces:** wikilinks, no rutas relativas; Obsidian los actualiza al renombrar.
- **Datos:** nada de credenciales, cadenas de conexión ni datos personales en ejemplos; usa marcadores (`<USUARIO>`, `<TOKEN>`).
