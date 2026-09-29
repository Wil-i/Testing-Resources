---
tags: [capitulo]
area: "[[Areas/Probador ágil/Probador ágil|Probador ágil]]"
capitulo: 1
paginas: "12–25"
duracion: "150 min"
---

# 1. Desarrollo ágil de software

> Parte de [[Areas/Probador ágil/Probador ágil|Probador ágil]]

**Términos clave:** [[Índice de términos#Automatización de la prueba|automatización de la prueba]], [[Índice de términos#Base de prueba|base de prueba]], [[Índice de términos#Ciclo de vida del software|ciclo de vida del software]], [[Índice de términos#Desarrollo ágil de software|desarrollo ágil de software]], [[Índice de términos#Desarrollo guiado por pruebas|desarrollo guiado por pruebas]], [[Índice de términos#Historia de usuario|historia de usuario]], [[Índice de términos#Manifiesto ágil|manifiesto ágil]], [[Índice de términos#Modelo de desarrollo incremental|modelo de desarrollo incremental]], [[Índice de términos#Modelo de desarrollo iterativo|modelo de desarrollo iterativo]], [[Índice de términos#Oráculo de prueba|oráculo de prueba]]

## Objetivos de aprendizaje
- **NB-AT-1.1.1 (K1)**: recordar el concepto básico del desarrollo ágil a partir del Manifiesto Ágil.
- **NB-AT-1.1.2 (K2)**: comprender las ventajas del enfoque de equipo completo.
- **NB-AT-1.1.3 (K2)**: comprender los beneficios de la retroalimentación temprana y frecuente.
- **NB-AT-1.2.1 (K2)**: recordar los enfoques de desarrollo ágil de software.
- **NB-AT-1.2.2 (K3)**: redactar, junto con desarrolladores y representantes de negocio, historias de usuario que se puedan probar.
- **NB-AT-1.2.3 (K2)**: comprender cómo usar las retrospectivas como mecanismo de mejora del proceso.
- **NB-AT-1.2.4 (K2)**: comprender el uso y el objetivo de la integración continua.
- **NB-AT-1.2.5 (K2)**: conocer las diferencias entre planificación de la iteración y de la entrega, y cómo aporta valor el probador en cada una.

## 1.1 Fundamentos del desarrollo ágil de software

El probador ágil trabaja distinto que en un proyecto tradicional: debe conocer los valores y principios ágiles y formar parte, con desarrolladores y representantes de negocio, de un equipo que se comunica desde el inicio y con frecuencia para eliminar defectos pronto.

### 1.1.1 El desarrollo ágil de software y el Manifiesto Ágil

El Manifiesto Ágil (2001) reúne los valores comunes de las metodologías ágiles más difundidas. Valora más lo de la izquierda, sin negar el valor de lo de la derecha:

| Se valora más... | ...que | Por qué |
|---|---|---|
| Individuos e interacciones | Procesos y herramientas | El software lo construyen personas; la comunicación continua hace más eficaz al equipo. |
| Software funcionando | Documentación extensiva | Aporta más valor al cliente, permite retroalimentación rápida y adelanta el tiempo de comercialización; útil en negocios cambiantes o que innovan. |
| Colaboración con el cliente | Negociación contractual | Al cliente le cuesta especificar lo que necesita; colaborar con él de forma regular mejora la comprensión y el éxito. |
| Respuesta ante el cambio | Seguir un plan | Mercado, legislación, competencia y tecnología cambian; se necesita flexibilidad en las prácticas. |

Los **doce principios** desarrollan esos valores. En síntesis:
- Satisfacer al cliente con entregas tempranas y continuas de software con valor, aceptando cambios de requisitos incluso tarde.
- Entregar software funcionando con frecuencia (de dos semanas a dos meses, cuanto más corto mejor); es la medida principal del progreso.
- Negocio y desarrollo trabajan juntos a diario; los proyectos se apoyan en personas motivadas, con entorno y confianza.
- La conversación cara a cara es la forma más eficiente de comunicar.
- Ritmo sostenible e indefinido (desarrollo sostenible).
- Excelencia técnica, buen diseño y simplicidad (maximizar el trabajo no realizado).
- Arquitecturas, requisitos y diseños emergen de equipos autoorganizados.
- El equipo reflexiona a intervalos regulares y ajusta su comportamiento.

Cada metodología ágil propone prácticas concretas para aplicarlos.

### 1.1.2 Enfoque de equipo completo

- Involucra a todas las personas con los conocimientos necesarios, incluidos representantes del cliente e implicados del negocio que deciden las prestaciones.
- Equipos pequeños (se citan casos de éxito de tres a nueve personas), idealmente en el mismo espacio (ubicación común).
- Se apoya en las reuniones de pie diarias, donde se informa el avance y los impedimentos (ver sección 2.2.1 del [[Areas/Probador ágil/Cap. 2 - Principios, prácticas y procesos de prueba ágil|capítulo 2]]).
- Beneficios: mejor comunicación y colaboración, aprovechamiento de las distintas competencias y calidad como responsabilidad de todos.
- El probador colabora con negocio para crear pruebas de aceptación adecuadas y con desarrollo para acordar la estrategia de prueba y los enfoques de automatización; así transfiere conocimiento de prueba al resto del equipo.
- **Poder de tres**: probadores, desarrolladores y representantes de negocio participan juntos en todas las discusiones sobre prestaciones.

### 1.1.3 Retroalimentación temprana y frecuente

- Las iteraciones cortas dan retroalimentación continua sobre la calidad; la integración continua (1.2.4) es una vía rápida para obtenerla.
- En el desarrollo secuencial el cliente ve el producto casi al final, cuando corregir es tarde; en ágil los cambios se incorporan durante el proceso.
- Ayuda a priorizar las prestaciones de mayor valor o riesgo y hace transparente la capacidad del equipo.
- Beneficios:
  - Evita malentendidos de requisitos que serían caros de corregir tarde.
  - Aclara las peticiones del cliente al ponerlas pronto a su disposición.
  - Descubre, aísla y resuelve problemas de calidad de forma temprana.
  - Informa al equipo sobre su productividad y capacidad de entrega.
  - Mantiene un impulso constante del proyecto.

## 1.2 Características de los enfoques ágiles

Prácticas comunes a la mayoría de organizaciones ágiles: historias de usuario colaborativas, retrospectivas, integración continua y planificación de la entrega y de cada iteración.

### 1.2.1 Enfoques de desarrollo ágil de software

El programa toma tres representantes: Programación Extrema, Scrum y Kanban.

**Programación Extrema (XP)**
- Cinco valores: comunicación, simplicidad, retroalimentación, valor y respeto.
- Principios adicionales: humanidad, economía, beneficio mutuo, autosimilitud, mejora, diversidad, reflexión, flujo, oportunidad, redundancia, fallo, calidad, pasos de bebé y responsabilidad aceptada.
- Trece prácticas principales: sentarse juntos, equipo completo, espacio de trabajo informativo, trabajo energizado, programación en pareja, historias, ciclo semanal, ciclo trimestral, holgura, construcción en diez minutos, integración continua, programar probando primero y diseño incremental.
- Influye en muchos enfoques actuales; los equipos Scrum suelen incorporar prácticas XP.

**Scrum** (marco de gestión ágil)

| Instrumento o práctica | Qué es |
|---|---|
| Esprint | Iteración de duración fija, normalmente de dos a cuatro semanas. |
| Incremento de producto | Resultado potencialmente entregable de cada esprint. |
| Trabajo acumulado del producto | Lista priorizada que gestiona el propietario de producto; evoluciona entre esprints (refinamiento del trabajo acumulado). |
| Trabajo acumulado del esprint | Elementos de máxima prioridad que el propio equipo elige al inicio del esprint (principio de extracción, no de inserción). |
| Definición de hecho | Criterios que el equipo acuerda para considerar entregable el esprint. |
| Acotamiento del tiempo | Solo entra lo que se espera terminar; lo no terminado vuelve al trabajo acumulado del producto. También aplica a reuniones. |
| Transparencia | El estado del esprint, incluidos los resultados de prueba, se actualiza a diario en el scrum diario y es visible para todos. |

Roles:
- **Scrum Master**: vela por que se apliquen las prácticas y reglas y elimina impedimentos; es un entrenador, no el líder.
- **Propietario de producto**: representa al cliente y crea, mantiene y prioriza el trabajo acumulado del producto; tampoco es el líder.
- **Equipo de desarrollo**: desarrolla y prueba; es autoorganizado (sin jefe) e interfuncional (ver secciones 2.3.2 del [[Areas/Probador ágil/Cap. 2 - Principios, prácticas y procesos de prueba ágil|capítulo 2]] y 3.1.4 del [[Areas/Probador ágil/Cap. 3 - Métodos, técnicas y herramientas|capítulo 3]]).

**Kanban** (enfoque de gestión usado a veces en proyectos ágiles): busca visualizar y optimizar el flujo de trabajo en la cadena de valor con tres instrumentos:
- **Tablero Kanban**: cada columna es una estación (actividades relacionadas, como desarrollo o prueba); los tickets avanzan de izquierda a derecha.
- **Limitación del trabajo en curso**: número máximo de tickets por estación o por tablero; cuando una estación tiene capacidad, extrae un ticket de la anterior.
- **Plazo de ejecución**: se minimiza el plazo medio de todo el flujo.

| Aspecto | Scrum | Kanban |
|---|---|---|
| Visualización de tareas activas | Sí, aporta transparencia | Sí, aporta transparencia |
| Trabajo pendiente | Trabajo acumulado del esprint | Lista de trabajo acumulado; entra al tablero cuando hay capacidad |
| Iteraciones | Obligatorias (esprints) | Opcionales |
| Entrega | Por esprint | Elemento por elemento |
| Acotamiento del tiempo | Sincroniza todas las tareas del esprint | Opcional |

### 1.2.2 Creación colaborativa de historias de usuario

- Las especificaciones deficientes causan muchos fracasos: usuarios que no conocen sus necesidades, falta de visión global, prestaciones redundantes o contradictorias, errores de comunicación.
- En ágil, las historias recogen los requisitos desde la perspectiva de desarrollo, prueba y negocio, con revisiones informales frecuentes mientras se escriben (en secuencial, revisiones formales después).
- Cada historia cubre aspectos funcionales y no funcionales e incluye **criterios de aceptación** definidos en colaboración; una tarea está terminada cuando se cumplen.
- El probador aporta detalles faltantes y requisitos no funcionales, hace preguntas abiertas, propone cómo probar y confirma los criterios.
- Técnicas de autoría: tormenta de ideas, mapas mentales y la técnica **INVEST**:

| Letra | Español | Inglés |
|---|---|---|
| I | Independiente | Independent |
| N | Negociable | Negotiable |
| V | Valioso | Valuable |
| E | Estimable | Estimable |
| S | Pequeño | Small |
| T | Capacidad de ser probado | Testable |

- **Concepto 3C**: una historia es la suma de:
  - *Tarjeta*: soporte físico con el requisito, su criticidad, la duración prevista de desarrollo y prueba y los criterios de aceptación; debe ser precisa porque alimenta el trabajo acumulado del producto.
  - *Conversación*: explica cómo se usará el software, escrita o verbal; empieza en la planificación de la entrega y sigue al programar la historia. El probador aporta un punto de vista distinto.
  - *Confirmación*: los criterios de aceptación acordados confirman que la historia está hecha, con pruebas positivas y negativas; pueden participar desarrolladores y especialistas en rendimiento, seguridad o interoperabilidad.
- La documentación de las historias varía según el equipo, pero debe ser concisa, suficiente y necesaria.

### 1.2.3 Retrospectivas

- Reunión al final de cada iteración sobre qué funcionó, qué mejorar y cómo mantener los éxitos; abarca proceso, personas, organización, relaciones y herramientas.
- Con seguimiento adecuado, son clave para la autoorganización y la mejora continua.
- Mejoras relacionadas con la prueba: efectividad, productividad, calidad de los casos, satisfacción del equipo y capacidad de ser probado de aplicaciones, historias, prestaciones o interfaces. El análisis de la causa raíz de los defectos impulsa mejoras.
- Conviene aplicar pocas mejoras por iteración para sostener el ritmo.
- Asisten el equipo y los representantes de negocio; un facilitador organiza y dirige. El probador aporta su perspectiva y debe tener un papel importante.
- Requieren confianza mutua y comparten los atributos de éxito de cualquier revisión (CTFL, sección 3.2).

### 1.2.4 Integración continua

Fusiona e integra los cambios al menos una vez al día en un proceso único, automatizado y repetible que une gestión de la configuración, compilación, construcción, despliegue y prueba. Tras la codificación y el registro en el repositorio compartido, ejecuta automáticamente:

| Actividad | Qué hace |
|---|---|
| Análisis estático de código | Analiza el código e informa resultados. |
| Compilación | Compila y enlaza, generando los ejecutables. |
| Prueba unitaria | Ejecuta las pruebas unitarias, mide cobertura e informa. |
| Despliegue | Instala la construcción en un entorno de prueba. |
| Prueba de integración | Ejecuta las pruebas de integración e informa. |
| Informe (panel de control) | Publica el estado en un lugar visible o lo envía al equipo. |

- Permite pruebas automatizadas regulares y retroalimentación rápida visible para todos. La regresión automatizada puede correr durante toda la iteración y cubrir historias de iteraciones previas, liberando al probador para probar a mano lo nuevo, los cambios y las confirmaciones de correcciones.
- Las herramientas de construcción aplican un control de la calidad continuo (pruebas estáticas y dinámicas, perfilado de rendimiento, documentación del código) en lugar de dejarlo para el final, y pueden enlazarse con despliegue automático a entornos de desarrollo, prueba, preproducción o producción.

| Ventajas | Riesgos y desafíos |
|---|---|
| Detección temprana y análisis más fácil de problemas de integración y cambios en conflicto. | Hay que introducir y mantener las herramientas. |
| Retroalimentación periódica sobre si el código funciona. | Hay que definir y establecer el proceso. |
| La versión probada está a un día de la que se desarrolla. | La automatización exige recursos y puede ser compleja. |
| Menor riesgo de regresión al refactorizar. | Se necesita cobertura profunda para obtener beneficios. |
| Confianza en una base sólida diaria; progreso visible. | Exceso de confianza en pruebas unitarias y pocas pruebas de sistema y aceptación. |
| Elimina el riesgo de calendario de la integración "big bang". | |
| Software ejecutable siempre disponible para probar, demostrar o formar; menos prueba manual repetitiva. | |

Requiere herramientas de prueba, de automatización de la construcción y de control de versiones.

### 1.2.5 Planificación de entregas e iteraciones

| Aspecto | Planificación de la entrega | Planificación de la iteración |
|---|---|---|
| Horizonte | Lanzamiento del producto, a menudo meses antes del inicio. | Una sola iteración. |
| Objeto | Define y redefine el trabajo acumulado del producto; divide historias grandes en otras más pequeñas. | Trabajo acumulado de la iteración: selección, elaboración, análisis de riesgo y estimación de historias. |
| Nivel | Alto nivel; base del enfoque y del plan de prueba para todas las iteraciones. | Detallado; las historias se dividen en tareas según la velocidad del equipo. |
| Aporte del probador | Definir historias que se puedan probar, con sus criterios de aceptación; participar en el análisis de riesgos de proyecto y calidad; estimar el esfuerzo de prueba; definir niveles de prueba; planificar la prueba de la entrega. | Análisis detallado de riesgos; determinar la capacidad de ser probado; crear pruebas de aceptación; descomponer historias en tareas (sobre todo de prueba); estimar esas tareas; identificar aspectos funcionales y no funcionales; apoyar la automatización en varios niveles. |

- En la planificación de la entrega, negocio establece y prioriza las historias con el equipo y se identifican riesgos y se estima a alto nivel (ver sección 3.2 del [[Areas/Probador ágil/Cap. 3 - Métodos, técnicas y herramientas|capítulo 3]]).
- En la de iteración, el equipo puede rechazar una historia demasiado vaga y pasar a la siguiente; negocio debe responder las dudas para saber qué implementar y cómo probar.
- Los planes cambian por factores internos (capacidad, velocidad, temas técnicos) o externos (mercados, competidores, amenazas); una historia puede resultar más compleja de lo estimado. El probador necesita visión global de la entrega, una base de prueba y un oráculo de prueba adecuados en cada iteración, aceptando a la vez el cambio.
- Aspectos de prueba que deben planificarse:
  - Alcance, extensión y objetivos de la prueba, y sus razones.
  - Quién realizará las actividades de prueba.
  - Entorno y datos de prueba necesarios, cuándo y con qué cambios.
  - Momento, secuencia, dependencias y prerrequisitos de las actividades funcionales y no funcionales, y su relación con el desarrollo.
  - Riesgos de proyecto y de calidad a tratar (ver sección 3.2.1 del [[Areas/Probador ágil/Cap. 3 - Métodos, técnicas y herramientas|capítulo 3]]).
- La estimación del equipo debe incluir el tiempo y el esfuerzo de las actividades de prueba.
