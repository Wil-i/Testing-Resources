---
tags: [capitulo]
area: "[[Areas/Probador ágil/Probador ágil|Probador ágil]]"
capitulo: 3
paginas: "37–56"
duracion: "480 min"
---

# 3. Métodos, técnicas y herramientas de prueba ágiles

> Parte de [[Areas/Probador ágil/Probador ágil|Probador ágil]]

**Términos clave:** [[Índice de términos#Automatización de la ejecución de prueba|automatización de la ejecución de prueba]], [[Índice de términos#Contrato de prueba|contrato de prueba]], [[Índice de términos#Criterios de aceptación|criterios de aceptación]], [[Índice de términos#Desarrollo guiado por pruebas|desarrollo guiado por pruebas]], [[Índice de términos#Enfoque de prueba|enfoque de prueba]], [[Índice de términos#Estimación de la prueba|estimación de la prueba]], [[Índice de términos#Estrategia de prueba|estrategia de prueba]], [[Índice de términos#Marco de trabajo de pruebas unitarias|marco de trabajo de pruebas unitarias]], [[Índice de términos#Prueba de regresión|prueba de regresión]], [[Índice de términos#Prueba de rendimiento|prueba de rendimiento]], [[Índice de términos#Prueba exploratoria|prueba exploratoria]], [[Índice de términos#Riesgo de calidad|riesgo de calidad]], [[Índice de términos#Riesgo de producto|riesgo de producto]]

## Objetivos de aprendizaje
- **NB-AT-3.1.1 (K1)**: recordar los conceptos de desarrollo guiado por pruebas, por pruebas de aceptación y por el comportamiento.
- **NB-AT-3.1.2 (K1)**: recordar los conceptos de la pirámide de prueba.
- **NB-AT-3.1.3 (K2)**: resumir los cuadrantes de prueba y su relación con los niveles y tipos de prueba.
- **NB-AT-3.1.4 (K3)**: practicar el rol de probador en un equipo Scrum para un proyecto ágil dado.
- **NB-AT-3.2.1 (K3)**: evaluar los riesgos de calidad en un proyecto ágil.
- **NB-AT-3.2.2 (K3)**: estimar el esfuerzo de prueba a partir del contenido de la iteración y de los riesgos de calidad.
- **NB-AT-3.3.1 (K3)**: interpretar la información relevante para apoyar las actividades de prueba.
- **NB-AT-3.3.2 (K2)**: explicar a los implicados del negocio cómo definir criterios de aceptación que se puedan probar.
- **NB-AT-3.3.3 (K3)**: dada una historia de usuario, escribir casos de prueba de aceptación en un desarrollo guiado por pruebas.
- **NB-AT-3.3.4 (K3)**: escribir casos de prueba para el comportamiento funcional y no funcional con técnicas de caja negra a partir de historias de usuario dadas.
- **NB-AT-3.3.5 (K3)**: realizar pruebas exploratorias para apoyar la prueba de un proyecto ágil.
- **NB-AT-3.4.1 (K1)**: recordar las herramientas disponibles para el probador según su propósito y las actividades del proyecto ágil.

La traducción repite el código NB-AT-3.1.1 en los cuatro objetivos de 3.1; aquí se numeran 3.1.1 a 3.1.4 según su orden.

## 3.1 Métodos de prueba ágil

Prácticas válidas en cualquier proyecto, ágil o no, que los equipos ágiles introducen pronto y que el probador ayuda a guiar: escribir las pruebas antes para expresar el comportamiento esperado, centrarse en prevenir, detectar y eliminar defectos pronto, y ejecutar el tipo de prueba adecuado en el momento y nivel correctos.

### 3.1.1 Desarrollo guiado por pruebas, por pruebas de aceptación y por el comportamiento

Tres técnicas complementarias que aplican el principio de prueba temprana: las pruebas se definen antes de escribir el código.

**Ciclo del desarrollo guiado por pruebas (TDD):**
1. Añadir una prueba que capture la idea del programador sobre un pequeño fragmento de código.
2. Ejecutarla: debe fallar porque el código aún no existe.
3. Escribir código y reejecutar en bucle cerrado hasta que pase.
4. Refactorizar y volver a ejecutar para confirmar que sigue pasando.
5. Repetir con el siguiente fragmento, ejecutando las pruebas previas y las nuevas.

| Técnica | Qué guía el desarrollo | Nivel típico | Rasgos principales |
|---|---|---|---|
| Desarrollo guiado por pruebas (TDD) | Casos de prueba automatizados escritos por el programador. | Unitario, centrado en el código (también integración o sistema). | Popularizado por XP, usado también en otras metodologías y a veces en secuenciales; enfoca en resultados esperados claros; las pruebas se usan en integración continua. |
| Desarrollo guiado por pruebas de aceptación (ATDD) | Criterios de aceptación y pruebas definidos al crear las historias (ver apartado 1.2.2 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]). | Sistema o aceptación. | Colaborativo entre negocio, desarrollo y prueba; crea pruebas reutilizables para regresión; herramientas que se conectan a las capas de datos y servicios, a menudo en integración continua; proceso detallado en 3.3.2. |
| Desarrollo guiado por el comportamiento (BDD) | Comportamiento esperado del software. | Pruebas unitarias centradas en necesidades del negocio. | Pruebas más fáciles de entender para todos; criterios en formato **dado / cuando / entonces** (contexto inicial, evento, resultados); el marco genera código que los desarrolladores usan para crear casos. |

### 3.1.2 La pirámide de prueba

- Niveles desde la base a la cima: unidad, integración, sistema y aceptación.
- Muchas pruebas en los niveles bajos y cada vez menos hacia arriba.
- Unitarias y de integración: automatizadas con herramientas basadas en API. Sistema y aceptación: automatizadas con herramientas basadas en la interfaz gráfica.
- Se basa en el principio de control de calidad y prueba temprana: eliminar los defectos lo antes posible.

### 3.1.3 Cuadrantes de prueba, niveles de prueba y tipos de prueba

El modelo de cuadrantes alinea niveles con tipos de prueba adecuados, asegura que no falte ninguno importante y da un vocabulario común a desarrollo, prueba y negocio. Las pruebas se orientan al negocio (usuario) o a la tecnología (desarrollador), y apoyan al equipo o critican el producto; pueden ser manuales, automatizadas, mixtas o manuales con apoyo de herramientas.

| Cuadrante | Nivel | Orientación | Propósito | Contenido típico | Ejecución |
|---|---|---|---|---|---|
| Q1 | Unitario | Tecnología | Apoya a los desarrolladores | Pruebas unitarias | Automatizadas, en integración continua |
| Q2 | Sistema | Negocio | Confirma el comportamiento | Pruebas funcionales, ejemplos, pruebas de historia, prototipos de experiencia de usuario, simulaciones; comprueban criterios de aceptación y alimentan la regresión | Manuales o automatizadas |
| Q3 | Aceptación de sistema o de usuario | Negocio | Critica el producto con escenarios y datos realistas | Exploratorias, escenarios, flujos de proceso, usabilidad, aceptación de usuario, alfa y beta | Normalmente manuales |
| Q4 | Aceptación de sistema u operativa | Tecnología | Critica el producto | Rendimiento, carga, estrés, escalabilidad, seguridad, mantenibilidad, gestión de memoria, compatibilidad e interoperabilidad, migración de datos, infraestructura, recuperación | Normalmente automatizadas |

En una iteración pueden necesitarse pruebas de uno o de todos los cuadrantes; el modelo se aplica a la prueba dinámica más que a la estática.

### 3.1.4 El rol de un probador

Rol del probador en un ciclo de vida Scrum.

**Trabajo en equipo.** Buenas prácticas de los equipos Scrum:

| Práctica | Qué implica para la prueba |
|---|---|
| Interdisciplinario | Cada miembro aporta competencias distintas; el equipo trabaja junto en estrategia, planificación, especificación, ejecución, evaluación e informe de la prueba. |
| Autoorganizado | Puede haber solo desarrolladores, pero lo ideal es contar con uno o más probadores (ver sección 2.1.5 del [[Areas/Probador ágil/Cap. 2 - Principios, prácticas y procesos de prueba ágil|capítulo 2]]). |
| Ubicación común | El probador se sienta con desarrolladores y propietario de producto. |
| Colaborativo | Con su equipo, otros equipos, implicados, propietario de producto y Scrum Master. |
| Empoderado | Las decisiones técnicas de diseño y prueba las toma el equipo, con el propietario de producto y otros equipos si hace falta. |
| Comprometido | Cuestionar y evaluar el producto frente a expectativas y necesidades de clientes y usuarios. |
| Transparente | Avance de desarrollo y prueba visible en el tablero de tareas ágil (ver sección 2.2.1 del [[Areas/Probador ágil/Cap. 2 - Principios, prácticas y procesos de prueba ágil|capítulo 2]]). |
| Creíble | Estrategia, implementación y ejecución de la prueba creíbles, informando a los implicados sobre el proceso. |
| Abierto a la retroalimentación | Las retrospectivas permiten aprender de éxitos y fallos. |
| Resiliente | La prueba debe responder al cambio. |

**Esprint cero.** Primera iteración, de preparación (ver apartado 1.2.5 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]). El probador colabora en:
- Identificar el alcance del proyecto (trabajo acumulado del producto).
- Crear una arquitectura inicial y prototipos de alto nivel.
- Planificar, adquirir e instalar herramientas (gestión de pruebas y defectos, automatización, integración continua).
- Crear una estrategia de prueba inicial para todos los niveles: alcance, riesgos técnicos, tipos de prueba (3.1.3) y objetivos de cobertura.
- Hacer un análisis inicial de riesgos de calidad (3.2.1).
- Definir métricas del proceso, del avance y de la calidad del producto.
- Especificar la definición de hecho.
- Crear el tablero de tareas (ver apartado 2.2.1 del [[Areas/Probador ágil/Cap. 2 - Principios, prácticas y procesos de prueba ágil|capítulo 2]]).
- Definir cuándo continuar o detener la prueba antes de entregar al cliente.

**Integración.** Para entregar valor continuo (idealmente en cada esprint), la estrategia de integración considera diseño y prueba e identifica todas las dependencias entre funciones y características.

**Planificación de la prueba.** Empieza en la planificación de la entrega y se actualiza en cada esprint, cubriendo los temas de la sección 1.2.5 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]. Las tareas del tablero deben durar uno o dos días, y los problemas de prueba se siguen para mantener un flujo constante.

**Prácticas de prueba ágil:**
- *Trabajo en pareja*: dos miembros (probador y desarrollador, dos probadores o probador y propietario de producto) comparten puesto para una prueba u otra tarea.
- *Diseño de prueba incremental*: casos y contratos se construyen poco a poco a partir de historias y otras bases de prueba, de lo simple a lo complejo.
- *Mapas mentales*: para identificar sesiones de prueba, mostrar estrategias y describir datos de prueba.

## 3.2 Evaluación de los riesgos de calidad y estimación del esfuerzo de prueba

El objetivo de reducir el riesgo de calidad a un nivel aceptable antes de la entrega es el mismo que en proyectos tradicionales, y las técnicas son similares, pero se adaptan a iteraciones cortas y a un ritmo de cambio alto.

### 3.2.1 Evaluación de los riesgos de calidad en proyectos ágiles

- Reto: seleccionar, asignar y priorizar las condiciones de prueba, dimensionar el esfuerzo de cada una y secuenciar las pruebas; la identificación, el análisis y la mitigación de riesgos ayudan a fijar un número aceptable de casos.
- **Riesgo**: posibilidad de un resultado o evento negativo. Su nivel combina probabilidad e impacto.
  - Si afecta sobre todo a la calidad del producto: riesgo de calidad o de producto.
  - Si afecta sobre todo al éxito del proyecto: riesgo de proyecto o de planificación.
- Momentos del análisis:
  - Planificación de la entrega: negocio da una visión de alto nivel y todo el equipo ayuda a identificar y evaluar.
  - Planificación de la iteración: todo el equipo identifica y evalúa.
- Ejemplos: cálculos erróneos en informes (funcional, exactitud); respuesta lenta (no funcional, eficiencia y tiempo de respuesta); pantallas difíciles de entender (no funcional, usabilidad).
- Las tareas con más riesgo empiezan antes y reciben más esfuerzo de prueba.

Pasos de ejemplo en la planificación de la iteración:
1. Reunir al equipo ágil, incluidos los probadores.
2. Listar los elementos del trabajo acumulado de la iteración (por ejemplo, en el tablero).
3. Identificar los riesgos de calidad de cada elemento según las características de calidad pertinentes.
4. Evaluar cada riesgo: categorizarlo y fijar su nivel por impacto y probabilidad.
5. Dimensionar la prueba en proporción al nivel de riesgo.
6. Elegir las técnicas de prueba para mitigar cada riesgo según su nivel y característica de calidad.

Después se diseñan, implementan y ejecutan las pruebas. El análisis se ajusta periódicamente (riesgos nuevos, reevaluación de niveles, efectividad de la mitigación). También se puede mitigar antes de ejecutar, por ejemplo revisando a fondo historias problemáticas.

### 3.2.2 Estimación del esfuerzo de prueba en función del contenido y el riesgo

- En la planificación de la entrega se estima el esfuerzo total, incluido el de prueba. Técnica habitual: **póquer de planificación**, basada en el consenso.
- Funcionamiento:
  - El propietario de producto o el cliente lee una historia a los estimadores.
  - Cada uno tiene cartas con valores tipo Fibonacci (0, 1, 2, 3, 5, 8, 13, 21...) u otra escala (por ejemplo, tallas de camisa); representan puntos de historia, días de esfuerzo u otra unidad. Fibonacci refleja que la incertidumbre crece con el tamaño.
  - Se discute la prestación (esfuerzo de desarrollo y prueba, complejidad, alcance de la prueba); conviene incluir el nivel de riesgo del elemento además de su prioridad.
  - Cada uno elige una carta en privado y se revelan a la vez. Si coinciden, esa es la estimación; si no, se discuten las diferencias y se repite hasta acordar, por consenso o con reglas (mediana, valor más alto) que limiten las rondas.
- Una estimación alta suele indicar que la historia no se entiende o que debe dividirse.
- Las discusiones dan estimaciones fiables y mejoran el conocimiento colectivo.

## 3.3 Técnicas en proyectos ágiles

Las técnicas y niveles tradicionales siguen siendo aplicables, con variaciones en técnicas, terminología y documentación.

### 3.3.1 Criterios de aceptación, cobertura adecuada y otra información para probar

- Los requisitos iniciales son historias breves con formato predefinido (ver apartado 1.2.2 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]); los no funcionales (usabilidad, rendimiento) pueden ser historias propias o ligadas a funcionales, y seguir estándares como ISO 25000 o sectoriales.
- Bases de prueba: historias de usuario (principal); experiencia de proyectos previos; funciones y características existentes; código, arquitectura y diseño; perfiles de usuario; información de defectos actuales y anteriores; taxonomía de defectos; estándares aplicables (por ejemplo, DO-178B en aeronáutica); riesgos de calidad (3.2.1).
- Para que se puedan probar, los criterios de aceptación deben abordar, cuando aplique:

| Tema | Qué describe |
|---|---|
| Comportamiento funcional | Comportamiento observable ante acciones del usuario bajo ciertas configuraciones. |
| Características de calidad | Cómo realiza el sistema el comportamiento (atributos de calidad o requisitos no funcionales: rendimiento, fiabilidad, usabilidad...). |
| Escenarios (casos de uso) | Secuencia de acciones entre un actor externo y el sistema para lograr un objetivo. |
| Reglas de negocio | Actividades posibles solo bajo condiciones definidas por procedimientos y restricciones externas. |
| Interfaces externas | Conexiones del sistema con el exterior (usuario, otros sistemas...). |
| Restricciones | Limitaciones de diseño e implementación; en software embebido, también físicas (tamaño, peso, conexiones). |
| Definiciones de datos | Formato, tipo, valores permitidos y por defecto de elementos de datos de negocio. |

- Otra información útil: cómo funciona y se usa el sistema, qué interfaces permiten probarlo, si las herramientas bastan y si el probador tiene los conocimientos necesarios. Surgirán necesidades nuevas (por ejemplo, cobertura de código) que se resuelven con el equipo.
- La información disponible determina cuándo algo está hecho. La **definición de hecho** se aplica en varios planos:

| Plano | Ejemplos de criterios |
|---|---|
| Prueba unitaria | 100 % de cobertura de decisión cuando sea posible, revisando caminos inviables; análisis estático de todo el código; sin defectos importantes abiertos; sin deuda técnica inaceptable conocida; código, pruebas y resultados revisados; todas las unitarias automatizadas; características importantes dentro de límites acordados. |
| Prueba de integración | Requisitos funcionales probados con pruebas positivas y negativas según tamaño, complejidad y riesgo; todas las interfaces entre unidades probadas; riesgos de calidad cubiertos según el alcance acordado; sin defectos importantes abiertos; defectos comunicados; regresión automatizada en repositorio común. |
| Prueba de sistema | Pruebas de extremo a extremo de historias, prestaciones y funciones; todas las personas usuarias cubiertas; características de calidad clave cubiertas; entornos similares a producción; riesgos cubiertos; regresión automatizada en repositorio común; defectos informados y quizá corregidos; sin defectos importantes abiertos. |
| Historia de usuario | Historias completas, entendidas y con criterios detallados que se puedan probar; elementos y pruebas de aceptación especificados y revisados; tareas de implementación y prueba identificadas y estimadas. |
| Prestación (una o varias historias o épicas) | Historias con criterios aprobadas por el cliente; diseño y código completos sin deuda técnica ni refactorización pendiente; unitarias con la cobertura definida; integración y sistema según criterios de cobertura; sin defectos importantes; documentación completa (notas de publicación, manuales, ayuda en línea). |
| Iteración | Prestaciones listas y probadas individualmente; defectos no críticos no resueltos añadidos y priorizados en el trabajo acumulado; integración completa probada; documentación aprobada. El software es potencialmente liberable, aunque no toda iteración termina en entrega. |
| Entrega | *Cobertura*: toda la base de prueba relevante cubierta, según novedad, complejidad, tamaño y riesgo. *Calidad*: intensidad y densidad de defectos y defectos restantes estimados dentro de límites; consecuencias y riesgo residual entendidos y aceptables. *Tiempo*: consideraciones de negocio de entregar o no en la fecha prevista. *Coste*: el coste de ciclo de vida estimado debe permitir un retorno de la inversión; gran parte procede del mantenimiento por defectos que llegan a producción. |

### 3.3.2 Aplicación del desarrollo guiado por pruebas de aceptación

- Enfoque de prueba primero: los casos, manuales o automatizados, se crean antes de implementar la historia, entre desarrollo, prueba y negocio.
- Pasos:
  1. **Taller de especificación**: analizar, discutir y redactar la historia, corrigiendo carencias, ambigüedades o errores.
  2. **Crear las pruebas**, en equipo o por el probador; una persona independiente (por ejemplo, de negocio) las valida.
- Las pruebas son ejemplos de las características de la historia (ejemplo y prueba se usan como sinónimos). Se empieza por ejemplos básicos y preguntas abiertas.
- Orden: primero pruebas positivas (camino feliz sin excepciones), luego negativas y atributos no funcionales (rendimiento, usabilidad).
- Se redactan en lenguaje natural comprensible para cualquier implicado, con precondiciones, entradas y salidas.
- Los ejemplos cubren todas las características de la historia sin añadir nada que no esté en ella, y no debe haber dos ejemplos que describan la misma característica.

### 3.3.3 Diseño de pruebas de caja negra funcionales y no funcionales

- El probador crea pruebas a la vez que se programa, a partir de las historias y sus criterios de aceptación; las exploratorias y otras basadas en la experiencia se crean después, durante la ejecución (3.3.4).
- Técnicas tradicionales aplicables: partición de equivalencia, análisis del valor frontera, tablas de decisión y transición de estado. Ejemplo: valores frontera cuando el cliente solo puede elegir un número limitado de artículos.
- Los requisitos no funcionales pueden escribirse como historias y probarse con las mismas técnicas; por ejemplo, un límite de tiempo de ejecución o un número máximo de operaciones fallidas.

### 3.3.4 Prueba exploratoria y prueba ágil

- Especialmente importante en ágil por el poco tiempo de análisis y el escaso detalle de las historias. Conviene combinarla con otras técnicas basadas en la experiencia dentro de una estrategia reactiva, y mezclarla con estrategias analíticas basadas en riesgos o requisitos, basadas en modelos y adversas a la regresión.
- Diseño y ejecución son simultáneos, guiados por un **contrato de prueba** que fija las condiciones a cubrir en una sesión acotada; los resultados de cada prueba orientan la siguiente. Se pueden usar técnicas de caja blanca y negra.

| Elemento del contrato | Contenido |
|---|---|
| Actor | Usuario previsto del sistema. |
| Propósito | Tema y objetivo concreto del actor (las condiciones de prueba). |
| Preparación | Lo necesario para empezar a ejecutar. |
| Prioridad | Importancia relativa, según la historia asociada o el nivel de riesgo. |
| Referencia | Especificaciones, riesgos u otras fuentes. |
| Datos | Datos necesarios. |
| Actividades | Ideas de lo que el actor podría hacer y lo interesante de probar (positivo y negativo). |
| Notas del oráculo | Cómo evaluar si el resultado es correcto. |
| Variaciones | Acciones y evaluaciones alternativas. |

- **Gestión de prueba basada en sesiones**: sesiones ininterrumpidas de 60 a 120 minutos, de tres tipos: estudio (cómo funciona), análisis (evaluar funcionalidad o características) y cobertura profunda (casos extremos, escenarios, interacciones).
- La calidad depende de hacer buenas preguntas: qué es lo más importante que averiguar, cómo puede fallar, qué pasa si..., qué debería pasar cuando..., si se cumplen necesidades y expectativas, si se puede instalar y desinstalar por todas las rutas de actualización.
- El probador usa creatividad, intuición y conocimiento del software, del negocio y de su uso. Heurísticas útiles: fronteras, CRUD (crear, leer, actualizar, borrar) e interrupciones (cierre de sesión, apagado, reinicio).
- Documentar al máximo para poder reconstruir cómo se encontró un problema:

| Qué registrar | Detalle |
|---|---|
| Cobertura de la prueba | Datos de entrada usados, cuánto se cubrió y cuánto falta. |
| Notas de evaluación | Observaciones, estabilidad, defectos, siguiente paso e ideas. |
| Lista de riesgos y estrategia | Riesgos cubiertos y pendientes; si se mantiene o ajusta la estrategia. |
| Cuestiones, preguntas y anomalías | Comportamientos inesperados y dudas sobre enfoque, entorno, datos, función, guion o sistema. |
| Comportamiento real | Evidencias: vídeo, capturas, archivos de salida. |

La información se resume en una herramienta de gestión del estado (de pruebas, de tareas o el tablero) para que los implicados entiendan el estado de toda la prueba.

## 3.4 Herramientas en proyectos ágiles

Las herramientas del nivel básico siguen siendo válidas, aunque algunas pesan más en ágil. Hay equipos que usan herramientas integrales (gestión del ciclo de vida de la aplicación o de tareas) con tableros, gráficos de quemado e historias, en lugar de herramientas separadas de prueba, requisitos e incidencias. La gestión de la configuración es clave por la cantidad de pruebas automatizadas. Las herramientas siguientes las usa todo el equipo para colaborar y compartir información.

### 3.4.1 Herramientas de gestión y seguimiento de tareas

Tableros físicos (pizarra, corcho) o software de gestión del ciclo de vida y de tareas con tableros electrónicos, que sirven para:
- Registrar historias y sus tareas de desarrollo y prueba para no perder nada en el esprint.
- Recoger estimaciones y calcular el esfuerzo de cada historia para agilizar la planificación de la iteración.
- Asociar tareas de desarrollo y de prueba a la misma historia para ver el esfuerzo completo.
- Agregar las actualizaciones de estado y dar una instantánea automática de historia, iteración y entrega.
- Mostrar el estado con métricas, gráficos y paneles, útil también para equipos distribuidos.
- Integrarse con la gestión de la configuración (registro de código, construcciones y actualizaciones automáticas de tareas).

### 3.4.2 Herramientas de comunicación e intercambio de información

| Herramienta | Usos y beneficios |
|---|---|
| Wikis | Base de conocimiento compartida: diagramas y discusiones de prestaciones, prototipos, fotos de pizarras; herramientas y técnicas útiles; métricas, gráficos y paneles de estado (sobre todo si se integran con el servidor de construcción y la gestión de tareas); conversaciones compartidas con todo el equipo. |
| Mensajería instantánea, audioconferencia y videochat | Comunicación en tiempo real, participación de equipos distribuidos en las reuniones de pie y menor coste con voz sobre IP. |
| Compartir y capturar escritorio | En equipos distribuidos, demostraciones, revisiones de código y trabajo en pareja; grabar demostraciones al final de cada iteración para publicarlas en la wiki. |

Complementan la comunicación cara a cara, no la sustituyen.

### 3.4.3 Herramientas de construcción y distribución de software

La construcción y el despliegue diarios son una práctica clave y requieren herramientas de integración continua y de distribución de construcciones; sus usos, beneficios y riesgos se describen en la sección 1.2.4 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]].

### 3.4.4 Herramientas de gestión de la configuración

- Guardan código fuente y pruebas automatizadas, y a menudo también pruebas manuales y otros productos de prueba en el mismo repositorio que el código.
- Dan trazabilidad entre versiones del software y versiones de las pruebas, y permiten cambiar rápido sin perder historial.
- Tipos principales de control de versiones: centralizado y distribuido. La elección depende del tamaño, la estructura y la ubicación del equipo y de la integración con otras herramientas.

### 3.4.5 Herramientas de diseño de pruebas, implementación y ejecución

| Tipo | Aporte en ágil |
|---|---|
| Diseño de pruebas | Mapas mentales para definir rápido las pruebas de una prestación nueva. |
| Gestión de casos de prueba | Pueden formar parte de la herramienta de ciclo de vida o de tareas de todo el equipo. |
| Preparación y generación de datos de prueba | Poblar la base de datos con muchas combinaciones; adaptar la estructura de datos y los scripts a los cambios; algunas parten de datos de producción y eliminan o anonimizan los sensibles; otras validan grandes entradas o salidas. |
| Carga de datos de prueba | Carga fiable y eficiente frente a la manual; a menudo integrada en la generación o mediante carga masiva del gestor de base de datos. |
| Ejecución de pruebas automatizadas | Herramientas comerciales o de código abierto para enfoques de prueba primero (BDD, TDD, ATDD) que expresan el comportamiento en tablas o lenguaje natural con palabras clave. |
| Prueba exploratoria | Capturan las acciones de la sesión: ayudan a reportar defectos y a pasar la prueba al juego de regresión automatizada. |

### 3.4.6 Informática en la nube y herramientas de virtualización

- La virtualización convierte un recurso físico en muchos recursos menores; con máquinas virtuales o instancias en la nube hay más servidores para desarrollo y prueba, sin esperar hardware.
- Las instantáneas agilizan el aprovisionamiento y la restauración de servidores.
- Algunas herramientas de gestión de la prueba toman una instantánea del servidor al detectar una falta, para compartirla con los desarrolladores que la investigan.
