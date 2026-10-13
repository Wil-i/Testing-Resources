---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 3
paginas: "37–43"
duracion: "80 min"
---

# 3. Prueba estática

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Anomalía|anomalía]], [[Índice de términos#Prueba dinámica|prueba dinámica]], [[Índice de términos#Revisión formal|revisión formal]], [[Índice de términos#Revisión informal|revisión informal]], [[Índice de términos#Inspección|inspección]], [[Índice de términos#Revisión|revisión]], [[Índice de términos#Análisis estático|análisis estático]], [[Índice de términos#Prueba estática|prueba estática]], [[Índice de términos#Revisión técnica|revisión técnica]], [[Índice de términos#Revisión guiada|revisión guiada]]

## Objetivos de aprendizaje
- **FL-3.1.1 (K1)**: reconocer los tipos de productos que pueden evaluarse con las distintas técnicas de prueba estática.
- **FL-3.1.2 (K2)**: explicar el valor de la prueba estática.
- **FL-3.1.3 (K2)**: comparar y contrastar la prueba estática y la dinámica.
- **FL-3.2.1 (K1)**: identificar las ventajas de la retroalimentación temprana y frecuente de los implicados.
- **FL-3.2.2 (K2)**: resumir las actividades del proceso de revisión.
- **FL-3.2.3 (K1)**: recordar las responsabilidades de los roles principales en una revisión.
- **FL-3.2.4 (K2)**: comparar y contrastar los tipos de revisión.
- **FL-3.2.5 (K1)**: recordar los factores que contribuyen al éxito de una revisión.

## 3.1 Prueba estática: fundamentos

- A diferencia de la prueba dinámica, no requiere ejecutar el software. El código, las especificaciones de procesos o de arquitectura y otros productos se evalúan con un examen manual (revisiones) o con ayuda de herramientas (análisis estático).
- Objetivos: mejorar la calidad, detectar defectos y evaluar características como legibilidad, completitud, corrección, capacidad de ser probado y consistencia. Sirve tanto para verificar como para validar.
- Probadores, representantes de negocio y desarrolladores colaboran en el mapeo de ejemplos, la redacción colaborativa de historias de usuario y el refinamiento del trabajo acumulado para que las historias cumplan criterios definidos, como la definición de preparado (ver sección 5.1.3 del [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]]). Las técnicas de revisión aseguran historias completas, comprensibles y con criterios de aceptación comprobables; con buenas preguntas, el probador explora, cuestiona y mejora las historias.
- **Análisis estático**:
  - Identifica problemas antes de la prueba dinámica y con menos esfuerzo, porque no necesita casos de prueba y suele usar herramientas (ver [[Areas/Fundamentos de prueba/Cap. 6 - Herramientas de prueba|capítulo 6]]).
  - Suele integrarse en los marcos de IC (ver sección 2.1.4 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]).
  - Además de defectos de código, evalúa mantenibilidad y seguridad; los correctores ortográficos y las herramientas de legibilidad también son análisis estático.

### 3.1.1 Productos de trabajo que pueden examinarse con prueba estática

- Casi cualquier producto de trabajo: especificaciones de requisitos, código fuente, planes y casos de prueba, elementos del trabajo acumulado del producto, contratos de prueba, documentación del proyecto y modelos.
- **Revisión**: vale para cualquier producto que pueda leerse y comprenderse.
- **Análisis estático**: el producto necesita una estructura que permita comprobarlo (modelos, código o texto con sintaxis formal).
- No son apropiados los productos difíciles de interpretar por personas y que no deben analizar las herramientas, como el código ejecutable de terceros por razones legales.

### 3.1.2 Valor de la prueba estática

- Detecta defectos en las fases más tempranas del CVDS, cumpliendo el principio de prueba temprana (ver sección 1.3 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]).
- Encuentra defectos que la prueba dinámica no puede detectar: código inaccesible, patrones de diseño no implementados como se esperaba, defectos en productos no ejecutables.
- Permite evaluar la calidad de los productos y generar confianza en ellos; al verificar los requisitos, los implicados comprueban que describen sus necesidades reales.
- Al hacerse pronto, crea un entendimiento compartido y mejora la comunicación entre implicados; por eso conviene involucrar a muchos de ellos.
- Las revisiones cuestan, pero el coste total del proyecto suele ser mucho menor que sin ellas, porque se dedica menos tiempo y esfuerzo a corregir defectos en fases avanzadas.
- El análisis estático detecta defectos de código con más eficiencia que la prueba dinámica, lo que suele reducir tanto los defectos de código como el esfuerzo total de desarrollo.

### 3.1.3 Diferencias entre la prueba estática y la prueba dinámica

Son prácticas complementarias con objetivos parecidos (apoyar la detección de defectos, ver sección 1.1.1 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]), pero difieren:

| Aspecto | Prueba estática | Prueba dinámica |
|---|---|---|
| Cómo llega al defecto | Lo encuentra directamente. | Provoca fallos; el defecto asociado se determina con un análisis posterior. |
| Tipos de defecto | Hay defectos que solo encuentra la estática. | Hay defectos que solo encuentra la dinámica (con análisis de fallos). |
| Caminos de código | Detecta con más facilidad defectos en caminos poco ejecutados o difíciles de alcanzar. | Esos caminos le resultan difíciles de alcanzar. |
| Productos aplicables | También productos no ejecutables. | Solo productos ejecutables. |
| Características medibles | Las que no dependen de la ejecución, como la mantenibilidad. | Las que dependen de la ejecución, como la eficiencia de desempeño. |

Defectos típicos más fáciles o baratos de encontrar con prueba estática:

| Categoría | Ejemplos |
|---|---|
| Requisitos | Inconsistencias, ambigüedades, contradicciones, omisiones, imprecisiones, duplicaciones. |
| Diseño | Estructuras de base de datos ineficaces, modularidad deficiente. |
| Codificación | Variables con valores indefinidos o no declaradas, código inalcanzable o duplicado, complejidad excesiva. |
| Desviación de estándares | Incumplimiento de las convenciones de nombres de los estándares de codificación. |
| Especificación de interfaces | Número, tipo u orden de parámetros que no coinciden. |
| Seguridad | Vulnerabilidades específicas, como desbordamientos de memoria intermedia. |
| Cobertura de la base de prueba | Lagunas o imprecisiones, como un criterio de aceptación sin pruebas. |

## 3.2 Retroalimentación y proceso de revisión

### 3.2.1 Beneficios de la retroalimentación temprana y frecuente de los implicados

- Permite comunicar pronto posibles problemas de calidad.
- Con poca implicación de los implicados, el producto puede no responder a su visión original o actual; no entregar lo que se desea provoca retrabajo costoso, plazos incumplidos, búsqueda de culpables e incluso el fracaso del proyecto.
- La retroalimentación frecuente durante todo el CVDS evita malentendidos sobre los requisitos y adelanta la comprensión e implementación de sus cambios.
- Ayuda al equipo a entender mejor lo que construye y a concentrarse en las prestaciones que más valor aportan y que mejor responden a los riesgos identificados.

### 3.2.2 Actividades del proceso de revisión

La norma ISO/IEC 20246 define un proceso de revisión genérico, estructurado pero flexible, que se adapta a cada situación; cuanto más formal la revisión, más tareas de cada actividad se necesitan. Un producto muy grande puede requerir varias revisiones para cubrirlo entero.

| Actividad | Qué ocurre |
|---|---|
| Planificación | Se define el alcance: propósito, producto a revisar, características de calidad a evaluar, áreas de foco, criterios de salida, información de apoyo (como estándares), esfuerzo y plazos. |
| Inicio de la revisión | Se asegura que todos estén preparados: acceso al producto, comprensión de su rol y responsabilidades y todo lo necesario para revisar. |
| Revisión individual | Cada revisor evalúa la calidad del producto y registra anomalías, recomendaciones y preguntas aplicando una o varias técnicas (por ejemplo, basadas en listas de comprobación o en escenarios; ISO/IEC 20246 las detalla). |
| Comunicación y análisis | Las anomalías no son necesariamente defectos: se analizan y se decide su estado, responsable y acciones, normalmente en una reunión de revisión donde también se decide el nivel de calidad del producto y el seguimiento necesario (puede requerirse una revisión de seguimiento). |
| Corrección e informe | Se crea un informe por cada defecto para seguir las acciones correctivas; al cumplirse los criterios de salida, el producto puede aceptarse; se informa de los resultados. |

### 3.2.3 Roles y responsabilidades en las revisiones

| Rol | Responsabilidad |
|---|---|
| Gestor | Decide qué se revisa y aporta recursos (personal y tiempo). |
| Autor | Crea y corrige el producto revisado. |
| Moderador (facilitador) | Asegura reuniones eficaces: mediación, gestión del tiempo y un entorno seguro donde todos puedan hablar libremente. |
| Escriba (registrador) | Recopila las anomalías de los revisores y registra la información de la revisión, como decisiones y anomalías nuevas halladas en la reunión. |
| Revisor | Revisa; puede ser alguien del proyecto, un experto en la materia u otro implicado. |
| Líder de la revisión | Responsabilidad global de la revisión: decide quién participa y organiza cuándo y dónde se hace. |

La norma ISO/IEC 20246 describe roles más detallados.

### 3.2.4 Tipos de revisión

- Van de informales a formales. El nivel de formalidad depende del CVDS, la madurez del proceso de desarrollo, la criticidad y complejidad del producto, los requisitos legales o reglamentarios y la necesidad de un rastro de auditoría.
- Un mismo producto puede pasar por varios tipos, por ejemplo una revisión informal y después otra más formal.
- Elegir bien el tipo es clave para los objetivos (3.2.5); además de los objetivos influyen las necesidades del proyecto, los recursos, el tipo de producto y sus riesgos, el dominio del negocio y la cultura de la empresa.

| Tipo | Formalidad y dirección | Objetivos | Rasgos |
|---|---|---|---|
| Informal | Sin proceso definido ni salida formal documentada. | Detectar anomalías. | — |
| Guiada | Dirigida por el autor. | Evaluar la calidad y generar confianza, formar a los revisores, lograr consenso, generar ideas, motivar y capacitar al autor, detectar anomalías. | La revisión individual previa es opcional. |
| Técnica | Revisores técnicamente cualificados, dirigida por un moderador. | Lograr consenso y decidir sobre un problema técnico; también detectar anomalías, evaluar la calidad, generar confianza e ideas y motivar al autor. | — |
| Inspección | La más formal: sigue el proceso genérico completo (3.2.2). | Encontrar el máximo de anomalías; además, evaluar la calidad, generar confianza y motivar al autor. | Se recogen métricas para mejorar el CVDS y la propia inspección; el autor no puede ser revisor ni escriba. |

### 3.2.5 Factores de éxito de las revisiones

- Objetivos claros y criterios de salida medibles; evaluar a los participantes nunca debe ser un objetivo.
- Elegir el tipo de revisión adecuado a los objetivos, al producto, a los participantes, a las necesidades del proyecto y al contexto.
- Revisar en fragmentos pequeños para que los revisores no pierdan la concentración en la revisión individual o en la reunión.
- Dar retroalimentación a implicados y autores para que mejoren el producto y sus actividades (3.2.1).
- Dar tiempo suficiente para preparar la revisión.
- Contar con el apoyo de la dirección.
- Integrar las revisiones en la cultura de la organización para promover el aprendizaje y la mejora del proceso.
- Formar a todos los participantes en su rol.
- Facilitar las reuniones.
