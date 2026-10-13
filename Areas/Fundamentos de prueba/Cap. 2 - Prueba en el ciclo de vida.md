---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 2
paginas: "27–36"
duracion: "130 min"
---

# 2. Prueba a lo largo del ciclo de vida de desarrollo de software

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Prueba de aceptación|prueba de aceptación]], [[Índice de términos#Prueba de caja negra|prueba de caja negra]], [[Índice de términos#Prueba de integración de componentes|prueba de integración de componentes]], [[Índice de términos#Prueba de componentes|prueba de componentes]], [[Índice de términos#Prueba de confirmación|prueba de confirmación]], [[Índice de términos#Prueba funcional|prueba funcional]], [[Índice de términos#Prueba de integración|prueba de integración]], [[Índice de términos#Prueba de mantenimiento|prueba de mantenimiento]], [[Índice de términos#Prueba no funcional|prueba no funcional]], [[Índice de términos#Prueba de regresión|prueba de regresión]], [[Índice de términos#Desplazamiento a la izquierda|desplazamiento a la izquierda]], [[Índice de términos#Prueba de integración de sistemas|prueba de integración de sistemas]], [[Índice de términos#Prueba de sistema|prueba de sistema]], [[Índice de términos#Nivel de prueba|nivel de prueba]], [[Índice de términos#Objeto de prueba|objeto de prueba]], [[Índice de términos#Tipo de prueba|tipo de prueba]], [[Índice de términos#Prueba de caja blanca|prueba de caja blanca]]

## Objetivos de aprendizaje
- **FL-2.1.1 (K2)**: explicar el impacto del ciclo de vida de desarrollo elegido en la prueba.
- **FL-2.1.2 (K1)**: recordar las buenas prácticas de prueba válidas para cualquier ciclo de vida.
- **FL-2.1.3 (K1)**: recordar ejemplos de enfoques de desarrollo de probar primero.
- **FL-2.1.4 (K2)**: resumir cómo puede influir DevOps en la prueba.
- **FL-2.1.5 (K2)**: explicar el enfoque de desplazamiento a la izquierda.
- **FL-2.1.6 (K2)**: explicar cómo usar las retrospectivas como mecanismo de mejora del proceso.
- **FL-2.2.1 (K2)**: distinguir los niveles de prueba.
- **FL-2.2.2 (K2)**: distinguir los tipos de prueba.
- **FL-2.2.3 (K2)**: distinguir la prueba de confirmación de la prueba de regresión.
- **FL-2.3.1 (K2)**: resumir la prueba de mantenimiento y sus desencadenantes.

## 2.1 La prueba en el contexto de un ciclo de vida de desarrollo de software

Un modelo de ciclo de vida de desarrollo de software (CVDS) es una representación abstracta y de alto nivel del proceso de desarrollo: define cómo se relacionan, lógica y cronológicamente, las fases y los tipos de actividad.

| Familia de modelos | Ejemplos |
|---|---|
| Desarrollo secuencial | Cascada, modelo V |
| Desarrollo iterativo | Espiral, prototipado |
| Desarrollo incremental | Proceso Unificado |

Algunas actividades se describen además con métodos y prácticas ágiles más detallados: desarrollo guiado por pruebas de aceptación (DGPA), por el comportamiento (DGC), diseño guiado por dominios (DGD), Programación Extrema (XP), desarrollo guiado por prestaciones, Kanban, Lean IT, Scrum y desarrollo guiado por pruebas (DGP). La traducción usa la sigla DGP tanto para el desarrollo guiado por prestaciones como para el guiado por pruebas.

### 2.1.1 Impacto del ciclo de vida de desarrollo en la prueba

Para tener éxito, la prueba se adapta al CVDS. Su elección repercute en el alcance y la cronología de las actividades (niveles y tipos de prueba), el detalle de la documentación, las técnicas y el enfoque, el alcance de la automatización y el rol y las responsabilidades del probador.

| Modelo | Implicaciones para la prueba |
|---|---|
| Secuencial | Al principio el probador participa en la revisión de requisitos, el análisis y el diseño de prueba; el código ejecutable llega en fases posteriores, así que la prueba dinámica no puede hacerse al inicio. |
| Iterativo e incremental | Cada iteración entrega un prototipo funcional o un incremento, por lo que en cada una puede haber prueba estática y dinámica en todos los niveles; las entregas frecuentes exigen retroalimentación rápida y regresión extensa. |
| Ágil | Se asume que habrá cambios durante todo el proyecto: se prefiere documentación ligera y mucha automatización para facilitar la regresión, y la prueba manual se hace sobre todo con técnicas basadas en la experiencia (ver sección 4.4 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]), que no requieren un análisis y diseño previos extensos. |

### 2.1.2 Ciclo de vida y buenas prácticas de prueba

Con cualquier modelo de CVDS:
- Cada actividad de desarrollo tiene su actividad de prueba correspondiente, de modo que todo el desarrollo queda sujeto a control de la calidad.
- Cada nivel de prueba (2.2.1) tiene objetivos propios y distintos, para que la prueba sea suficientemente completa sin redundancias.
- El análisis y el diseño de prueba de un nivel empiezan durante la fase de desarrollo correspondiente, aplicando el principio de prueba temprana (ver sección 1.3 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]).
- Los probadores revisan los productos de trabajo en cuanto hay borradores, lo que apoya la estrategia de desplazamiento a la izquierda (2.1.5).

### 2.1.3 La prueba como impulsor del desarrollo de software

DGP, DGPA y DGC son enfoques similares en los que las pruebas se definen antes de escribir el código y guían el desarrollo. Aplican el principio de prueba temprana (ver sección 1.3 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]), siguen el desplazamiento a la izquierda (2.1.5) y apoyan un modelo de desarrollo iterativo.

| Enfoque | Cómo funciona |
|---|---|
| Desarrollo guiado por prueba (DGP, *TDD*) | La codificación la dirigen casos de prueba, no un diseño extenso: primero se escriben las pruebas, luego el código que las satisface y por último se refactorizan pruebas y código. |
| Desarrollo guiado por prueba de aceptación (DGPA, *ATDD*) | Obtiene pruebas de los criterios de aceptación durante el diseño del sistema; las pruebas se escriben antes de desarrollar la parte de la aplicación que debe satisfacerlas (ver sección 4.5.3 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]). |
| Desarrollo guiado por comportamiento (DGC, *BDD*) | Expresa el comportamiento deseado con casos en lenguaje natural sencillo, comprensible para los implicados, normalmente con el formato Dado/Cuando/Entonces (*Given/When/Then*); después se traducen automáticamente en pruebas ejecutables. |

En los tres casos las pruebas pueden mantenerse como pruebas automatizadas que protegen la calidad del código en adaptaciones y refactorizaciones futuras.

### 2.1.4 DevOps y la prueba

DevOps es un enfoque organizativo que busca sinergias haciendo que desarrollo (incluida la prueba) y operaciones trabajen hacia objetivos comunes. Exige un cambio cultural que valore por igual ambas funciones y promueve la autonomía de los equipos, la retroalimentación rápida, las cadenas de herramientas integradas y prácticas como la integración continua (IC) y la entrega continua (EC). Así los equipos construyen, prueban y entregan código de calidad más rápido mediante un canal de entrega DevOps.

| Ventajas para la prueba | Riesgos y desafíos |
|---|---|
| Retroalimentación rápida sobre la calidad del código y sobre si los cambios perjudican al código existente. | Hay que definir y establecer el canal (tubería) de entrega. |
| La IC promueve el desplazamiento a la izquierda: los desarrolladores entregan código acompañado de pruebas de componente y análisis estático. | Hay que introducir y mantener las herramientas de IC/EC. |
| Los procesos automatizados de IC/EC facilitan entornos de prueba estables. | La automatización de la prueba requiere recursos adicionales y puede ser difícil de establecer y mantener. |
| Mayor visibilidad de las características de calidad no funcionales (rendimiento, fiabilidad). | |
| La automatización del canal reduce la prueba manual repetitiva. | |
| La escala de la regresión automatizada minimiza el riesgo de regresión. | |

Aun con un alto nivel de automatización, la prueba manual (sobre todo desde la perspectiva del usuario) sigue siendo necesaria.

### 2.1.5 Enfoque de desplazamiento a la izquierda

El principio de prueba temprana (ver sección 1.3 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]) se llama a veces desplazamiento a la izquierda: probar antes en el CVDS, sin esperar a que el código esté implementado o integrado, pero sin descuidar la prueba de las etapas posteriores.

Buenas prácticas para lograrlo:
- Revisar las especificaciones desde la perspectiva de la prueba, lo que suele revelar ambigüedades, incompletitud e inconsistencias.
- Escribir los casos de prueba antes que el código y ejecutar el código en un arnés de prueba durante la implementación.
- Usar IC y, mejor aún, EC: retroalimentación rápida y pruebas de componente automatizadas que acompañan al código enviado al repositorio.
- Completar el análisis estático antes de la prueba dinámica o como parte de un proceso automatizado.
- Empezar la prueba no funcional desde el nivel de componente cuando sea posible, en lugar de esperar a tener el sistema completo y un entorno representativo.

Puede requerir más formación, esfuerzo o coste al principio, a cambio de ahorros posteriores, y necesita que los implicados estén convencidos del concepto.

### 2.1.6 Retrospectivas y mejora del proceso

- También llamadas reuniones post proyecto o retrospectivas de proyecto; se celebran al final de un proyecto o iteración, en un hito de entrega o cuando hagan falta. Su cronología y organización dependen del modelo de CVDS.
- Participan probadores y otros perfiles (desarrolladores, arquitectos, propietario de producto, analistas de negocio) y debaten:
  - Qué funcionó y debe conservarse.
  - Qué no funcionó y puede mejorarse.
  - Cómo incorporar las mejoras y mantener los éxitos.
- Los resultados se registran y suelen formar parte del informe de compleción de la prueba (ver sección 5.3.2 del [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]]). Son clave para la mejora continua, siempre que se haga seguimiento de las mejoras recomendadas.
- Beneficios habituales para la prueba: más efectividad y eficiencia, mejores productos de prueba, cohesión y aprendizaje del equipo, mejor base de prueba (requisitos más completos y de más calidad) y mejor cooperación entre desarrollo y prueba.

## 2.2 Niveles de prueba y tipos de prueba

- **Niveles de prueba**: grupos de actividades que se organizan y gestionan juntos. Cada nivel es una instancia del proceso de prueba aplicada al software en una etapa de desarrollo, desde componentes aislados hasta sistemas completos o sistemas de sistemas. En los modelos secuenciales, los criterios de salida de un nivel suelen formar parte de los de entrada del siguiente (en algunos iterativos no); una actividad de desarrollo puede abarcar varios niveles y los niveles pueden solaparse en el tiempo.
- **Tipos de prueba**: grupos de actividades relacionadas con características de calidad específicas; la mayoría puede hacerse en todos los niveles.

### 2.2.1 Niveles de prueba

| Nivel | Foco | Responsables y soporte |
|---|---|---|
| Componente (prueba unitaria) | Componentes de forma aislada. | Normalmente los desarrolladores, en su entorno; suele requerir arneses de prueba o marcos de prueba unitaria. |
| Integración de componentes (integración de unidades) | Interfaces e interacciones entre componentes. | Depende mucho de la estrategia de integración: ascendente, descendente o big-bang. |
| Sistema | Comportamiento y capacidades del sistema o producto completo: prueba funcional de tareas de extremo a extremo y prueba no funcional de características de calidad. | Algunas características (como la usabilidad) se prueban mejor en el sistema completo y en un entorno representativo; pueden usarse simulaciones de subsistemas. Puede hacerla un equipo independiente; se relaciona con la especificación del sistema. |
| Integración de sistemas | Interfaces del sistema sujeto a prueba con otros sistemas y servicios externos. | Requiere entornos adecuados, preferiblemente parecidos al de operación. |
| Aceptación | Validación y demostración de que el sistema está listo para desplegarse, es decir, que satisface las necesidades de negocio del usuario. | Idealmente, los usuarios destinatarios. Formas principales: aceptación de usuario (PAU), operativa, contractual y de regulación, alfa y beta. |

Para no solapar actividades, los niveles se distinguen por atributos (lista no exhaustiva): objeto de prueba, objetivos de prueba, base de prueba, defectos y fallos, y enfoque y responsabilidades.

### 2.2.2 Tipos de prueba

| Tipo | Qué evalúa | Objetivo principal |
|---|---|---|
| Funcional | Las funciones del componente o sistema: "qué" debe hacer. | Comprobar completitud, corrección y pertinencia funcionales. |
| No funcional | Atributos distintos de los funcionales: "lo bien que se comporta" el sistema. | Comprobar las características de calidad no funcionales. |
| Caja negra | Se basa en la especificación; obtiene pruebas de documentación externa al objeto (ver sección 4.2 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]). | Comprobar el comportamiento frente a la especificación. |
| Caja blanca | Se basa en la estructura: código, arquitectura, flujos de trabajo y de datos (ver sección 4.3 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]). | Cubrir la estructura subyacente hasta un nivel aceptable. |

- Características no funcionales según ISO/IEC 25010: eficiencia de desempeño, compatibilidad, usabilidad, fiabilidad, seguridad, mantenibilidad y portabilidad.
- Sobre la prueba no funcional:
  - A veces conviene empezarla pronto (en revisiones, en la prueba de componente o de sistema).
  - Muchas pruebas no funcionales reutilizan pruebas funcionales y comprueban además una restricción (que una función termine en cierto tiempo o pueda portarse a otra plataforma).
  - Descubrir tarde defectos no funcionales puede amenazar seriamente el proyecto.
  - Puede necesitar entornos muy específicos, como un laboratorio de usabilidad.
- Los cuatro tipos se aplican en todos los niveles, con distinto foco en cada uno, y cualquier técnica puede servir para obtener condiciones y casos de cualquier tipo.

### 2.2.3 Prueba de confirmación y prueba de regresión

Cuando se cambia un componente o sistema (para añadir una prestación o corregir un defecto), la prueba debe incluir confirmación y regresión.

| Aspecto | Prueba de confirmación | Prueba de regresión |
|---|---|---|
| Propósito | Confirmar que el defecto original se corrigió con éxito. | Confirmar que un cambio, incluida una corrección ya confirmada, no causó consecuencias adversas. |
| Cómo se hace | Según el riesgo: reejecutar los casos que fallaron por el defecto y/o añadir pruebas que cubran los cambios de la corrección. Con poco tiempo o dinero, basta repetir los pasos que reproducían el fallo y comprobar que ya no ocurre. | Ejecutar juegos de regresión; conviene un análisis de impacto previo, que muestra qué partes pueden verse afectadas, para optimizar el alcance. |
| Alcance | El defecto corregido. | El componente cambiado, otros componentes del sistema, sistemas conectados e incluso el entorno. |

- Los juegos de regresión se ejecutan muchas veces y crecen con cada iteración o entrega: son firmes candidatos a la automatización, que debe empezar pronto. Con IC, como en DevOps (2.1.4), conviene incluir regresión automatizada, posiblemente en varios niveles.
- Ambas pruebas se necesitan en todos los niveles en los que se corrijan defectos o se hagan cambios.

## 2.3 Prueba de mantenimiento

- El mantenimiento puede ser correctivo, adaptativo a cambios del entorno o para mejorar el rendimiento o la mantenibilidad (ISO/IEC 14764); implica entregas o despliegues planificados y no planificados (correcciones en caliente).
- Un análisis de impacto previo ayuda a decidir si conviene hacer el cambio según sus consecuencias en otras áreas.
- Probar cambios en un sistema en producción incluye evaluar si el cambio se implementó con éxito y comprobar posibles regresiones en las partes no modificadas, que suelen ser la mayoría.
- El alcance depende del riesgo del cambio, del tamaño del sistema existente y de la magnitud del cambio.

| Desencadenante | Ejemplos y pruebas asociadas |
|---|---|
| Modificaciones | Mejoras planificadas (basadas en entregas), cambios correctivos o correcciones en caliente. |
| Actualizaciones o migraciones del entorno de operación | Paso de una plataforma a otra: pruebas del nuevo entorno y del software modificado, o pruebas de conversión de datos al migrar datos de otra aplicación. |
| Retirada | Fin de la vida útil: probar el archivado de datos si se exigen largos periodos de retención, y los procedimientos de recuperación y restauración por si se necesitan datos archivados. |
