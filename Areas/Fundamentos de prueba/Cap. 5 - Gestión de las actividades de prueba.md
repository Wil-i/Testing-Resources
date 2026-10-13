---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 5
paginas: "58–72"
duracion: "335 min"
---

# 5. Gestión de las actividades de prueba

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Gestión de defectos|gestión de defectos]], [[Índice de términos#Informe de defecto|informe de defecto]], [[Índice de términos#Criterios de entrada|criterios de entrada]], [[Índice de términos#Criterios de salida|criterios de salida]], [[Índice de términos#Riesgo de producto|riesgo de producto]], [[Índice de términos#Riesgo de proyecto|riesgo de proyecto]], [[Índice de términos#Riesgo|riesgo]], [[Índice de términos#Análisis del riesgo|análisis del riesgo]], [[Índice de términos#Evaluación del riesgo|evaluación del riesgo]], [[Índice de términos#Control del riesgo|control del riesgo]], [[Índice de términos#Identificación del riesgo|identificación del riesgo]], [[Índice de términos#Nivel de riesgo|nivel de riesgo]], [[Índice de términos#Gestión del riesgo|gestión del riesgo]], [[Índice de términos#Mitigación del riesgo|mitigación del riesgo]], [[Índice de términos#Monitorización del riesgo|monitorización del riesgo]], [[Índice de términos#Prueba basada en el riesgo|pruebas basadas en el riesgo]], [[Índice de términos#Enfoque de prueba|enfoque de prueba]], [[Índice de términos#Informe de compleción de la prueba|informe de compleción de la prueba]], [[Índice de términos#Control de la prueba|control de la prueba]], [[Índice de términos#Monitorización de la prueba|monitorización de la prueba]], [[Índice de términos#Plan de prueba|plan de prueba]], [[Índice de términos#Planificación de prueba|planificación de prueba]], [[Índice de términos#Informe del avance de la prueba|informe del avance de la prueba]], [[Índice de términos#Pirámide de prueba|pirámide de prueba]], [[Índice de términos#Cuadrantes de prueba|cuadrantes de prueba]]

## Objetivos de aprendizaje
- **FL-5.1.1 (K2)**: dar ejemplos del propósito y el contenido de un plan de prueba.
- **FL-5.1.2 (K1)**: reconocer cómo aporta valor el probador a la planificación de la iteración y de la entrega.
- **FL-5.1.3 (K2)**: comparar y contrastar criterios de entrada y criterios de salida.
- **FL-5.1.4 (K3)**: usar técnicas de estimación para calcular el esfuerzo de prueba.
- **FL-5.1.5 (K3)**: aplicar la priorización de casos de prueba.
- **FL-5.1.6 (K1)**: recordar los conceptos de la pirámide de prueba.
- **FL-5.1.7 (K2)**: resumir los cuadrantes de prueba y su relación con los niveles y tipos de prueba.
- **FL-5.2.1 (K1)**: identificar el nivel de riesgo a partir de su probabilidad e impacto.
- **FL-5.2.2 (K2)**: distinguir entre riesgos de proyecto y riesgos de producto.
- **FL-5.2.3 (K2)**: explicar cómo el análisis del riesgo de producto influye en la minuciosidad y el alcance de la prueba.
- **FL-5.2.4 (K2)**: explicar qué medidas pueden tomarse ante los riesgos de producto analizados.
- **FL-5.3.1 (K1)**: recordar las métricas usadas en la prueba.
- **FL-5.3.2 (K2)**: resumir propósito, contenido y audiencias de los informes de prueba.
- **FL-5.3.3 (K2)**: dar ejemplos de cómo comunicar el estado de la prueba.
- **FL-5.4.1 (K2)**: resumir cómo la gestión de la configuración apoya la prueba.
- **FL-5.5.1 (K3)**: preparar un informe de defecto.

## 5.1 Planificación de la prueba

### 5.1.1 Propósito y contenido de un plan de prueba

Un plan de prueba describe los objetivos, los recursos y los procesos de un proyecto de prueba. Sirve para:
- Documentar los medios y el calendario para alcanzar los objetivos.
- Ayudar a que las actividades cumplan los criterios establecidos.
- Comunicarse con el equipo y otros implicados.
- Demostrar que la prueba se ajusta a la política y la estrategia de prueba existentes, o explicar por qué se desvía.

Planificar obliga a anticipar retos relacionados con riesgos, calendarios, personas, herramientas, costes y esfuerzo; elaborar el plan es una forma útil de pensar el esfuerzo necesario.

| Contenido habitual | Ejemplos |
|---|---|
| Contexto de la prueba | Alcance, objetivos, restricciones, base de prueba. |
| Supuestos y restricciones | Del proyecto de prueba. |
| Implicados | Roles, responsabilidades, relevancia para la prueba, necesidades de contratación y formación. |
| Comunicación | Formas y frecuencia, plantillas de documentación. |
| Registro de riesgos | Riesgos de producto y de proyecto. |
| Enfoque de prueba | Niveles, tipos y técnicas de prueba, entregables, criterios de entrada y salida, independencia, métricas a recoger, requisitos de datos y de entorno, desviaciones de la política y la estrategia de la organización. |
| Presupuesto y calendario | — |

Ampliación: ISO/IEC/IEEE 29119-3.

### 5.1.2 Contribución del probador a la planificación de la iteración y de la entrega

En los CVDS iterativos suele haber dos tipos de planificación:

| Aspecto | Planificación de la entrega | Planificación de la iteración |
|---|---|---|
| Horizonte | Se anticipa al lanzamiento de un producto. | Mira hacia el final de una única iteración. |
| Objeto | Define y redefine el trabajo acumulado del producto; puede refinar historias grandes en otras más pequeñas; sirve de base al enfoque y al plan de prueba de todas las iteraciones. | El trabajo acumulado de la iteración. |
| Aporte del probador | Redacta historias de usuario y criterios de aceptación comprobables, participa en el análisis de riesgos de calidad y de proyecto, estima el esfuerzo de prueba de las historias, determina el enfoque de prueba y planifica la prueba de la entrega. | Participa en el análisis detallado del riesgo de las historias, determina su capacidad de ser probadas, las desglosa en tareas (sobre todo de prueba), estima el esfuerzo de todas las tareas de prueba e identifica y refina aspectos funcionales y no funcionales del objeto de prueba. |

Para la redacción de historias y criterios, el programa remite a la sección 4.5 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]; para riesgos y estimación, a 5.2 y 5.1.4.

### 5.1.3 Criterios de entrada y criterios de salida

| Aspecto | Criterios de entrada | Criterios de salida |
|---|---|---|
| Definición | Precondiciones para emprender una actividad; si no se cumplen, la actividad será probablemente más difícil, lenta, cara y arriesgada. | Lo que debe lograrse para declarar completada una actividad. |
| Ejemplos típicos | Disponibilidad de recursos (personas, herramientas, entornos, datos, presupuesto, tiempo), de material de prueba (base de prueba, requisitos comprobables, historias, casos) y nivel de calidad inicial del objeto (por ejemplo, todas las pruebas de humo superadas). | Medidas de completitud (cobertura alcanzada, defectos sin resolver, densidad de defectos, casos fallidos) y criterios de compleción (pruebas planificadas ejecutadas, prueba estática realizada, defectos encontrados notificados, regresión automatizada). |
| En desarrollo ágil | **Definición de preparado**: lo que debe cumplir una historia para empezar su desarrollo o prueba. | **Definición de hecho**: métricas objetivas del equipo para considerar entregable un elemento. |

- Deben definirse para cada nivel de prueba y varían según sus objetivos.
- Quedarse sin tiempo o sin presupuesto puede ser un criterio de salida válido: es aceptable terminar sin cumplir otros criterios si los implicados revisaron y aceptaron el riesgo de pasar a producción sin más prueba.

### 5.1.4 Técnicas de estimación

La estimación del esfuerzo de prueba predice el trabajo necesario para cumplir los objetivos de un proyecto de prueba. Hay que dejar claro que se basa en supuestos y siempre tiene error. Las tareas pequeñas se estiman con más precisión, así que una tarea grande puede descomponerse en otras menores.

| Técnica | Base | Cómo funciona | Ejemplo |
|---|---|---|---|
| Estimación basada en proporciones | Métricas | Se obtienen proporciones "estándar" de proyectos anteriores de la organización (los datos históricos propios suelen ser la mejor fuente) y se aplican al nuevo proyecto. | Si la proporción desarrollo:prueba fue 3:2 y se esperan 600 días-persona de desarrollo, la prueba se estima en 400 días-persona. |
| Extrapolación | Métricas | Se mide lo antes posible en el proyecto actual y, con suficientes observaciones, se extrapola el trabajo restante (normalmente con un modelo matemático). Muy adecuada en CVDS iterativos. | El esfuerzo de la próxima iteración se estima como la media de las tres últimas. |
| Delphi de banda ancha | Experiencia (iterativa) | Cada experto estima por separado; si las estimaciones se desvían más allá de los límites acordados, se discuten y cada uno vuelve a estimar aislado, hasta llegar a un consenso. El **póquer de planificación**, habitual en ágil, es una variante con cartas numeradas que representan el esfuerzo. | — |
| Estimación de tres puntos | Expertos | Cada experto da una estimación optimista (a), una más probable (m) y una pesimista (b); la final es su media ponderada, normalmente E = (a + 4m + b) / 6, y permite calcular el error de medición SD = (b − a) / 6. | Con a = 6, m = 9 y b = 18 horas-persona: E = 10 y SD = 2, es decir, 10 ± 2 horas-persona (entre 8 y 12). |

### 5.1.5 Priorización de casos de prueba

Una vez reunidos casos y procedimientos en juegos de prueba, se organizan en un calendario de ejecución que fija su orden.

| Estrategia | Orden de ejecución |
|---|---|
| Basada en el riesgo | Según el análisis del riesgo (5.2.3): primero los casos que cubren los riesgos más importantes. |
| Basada en la cobertura | Primero los casos que logran más cobertura (por ejemplo, de sentencias). En la variante de **cobertura adicional**, primero el de mayor cobertura y después, cada vez, el que más cobertura adicional aporta. |
| Basada en requisitos | Según la prioridad de los requisitos, definida por los implicados y trazada hasta los casos: primero los de los requisitos más importantes. |

- Las dependencias pueden romper el orden ideal: si un caso de prioridad alta depende de otro de prioridad baja, este se ejecuta antes.
- También cuenta la disponibilidad de recursos: herramientas, entornos o personas disponibles solo en ciertos periodos.

### 5.1.6 Pirámide de prueba

- Modelo que muestra que las pruebas pueden tener distinta granularidad; ayuda al equipo a automatizar y a repartir el esfuerzo, mostrando que objetivos distintos se apoyan en distintos niveles de automatización. Cada capa representa un grupo de pruebas.
- Cuanto más alta la capa, menor es la granularidad y el aislamiento de las pruebas. Las de la capa inferior son pequeñas, aisladas y rápidas, y cada una comprueba poca funcionalidad, por lo que se necesitan muchas; las de la capa superior son complejas, de alto nivel y de extremo a extremo, más lentas, y cada una comprueba mucha funcionalidad, por lo que bastan pocas. (La traducción afirma que el tiempo de ejecución también disminuye con la altura, lo que contradice la descripción de la capa superior como más lenta.)
- El número y el nombre de las capas varían: el modelo original define pruebas unitarias, de servicio y de interfaz de usuario; otro modelo popular, pruebas unitarias (de componente), de integración (de componentes) y de extremo a extremo. Pueden usarse otros niveles de prueba (ver sección 2.2.1 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]).

### 5.1.7 Cuadrantes de prueba

- Agrupan los niveles de prueba con los tipos, actividades, técnicas y productos de trabajo apropiados en el desarrollo ágil.
- Ayudan a la gestión de la prueba a asegurar que el CVDS incluye todos los tipos y niveles adecuados y a entender que algunos tipos son más relevantes en ciertos niveles; además dan a desarrolladores, probadores y negocio una forma común de describir los tipos de prueba.
- Dos ejes: pruebas **orientadas al negocio** o **a la tecnología**, y pruebas que **apoyan al equipo** (guían el desarrollo) o que **critican el producto** (miden su comportamiento frente a las expectativas).

| Cuadrante | Orientación | Contenido | Ejecución |
|---|---|---|---|
| Q1 | Tecnología, apoya al equipo | Pruebas de componente y de integración de componentes. | Deberían automatizarse e incluirse en la IC. |
| Q2 | Negocio, apoya al equipo | Pruebas funcionales, ejemplos, pruebas de historias de usuario, prototipos de experiencia de usuario, pruebas de API y simulaciones; comprueban los criterios de aceptación. | Manuales o automatizadas. |
| Q3 | Negocio, critica el producto | Prueba exploratoria, de usabilidad y de aceptación de usuario. | Orientadas al usuario; suelen ser manuales. |
| Q4 | Tecnología, critica el producto | Pruebas de humo y no funcionales (salvo las de usabilidad). | Suelen automatizarse. |

## 5.2 Gestión del riesgo

- Factores internos y externos hacen incierto si una organización alcanzará sus objetivos y cuándo (ISO 31000). Gestionar el riesgo aumenta la probabilidad de lograrlos, mejora la calidad de los productos y la confianza de los implicados.
- Actividades principales:
  - **Análisis del riesgo**: identificación y evaluación del riesgo (5.2.3).
  - **Control del riesgo**: mitigación y monitorización del riesgo (5.2.4).
- El enfoque en el que las actividades de prueba se seleccionan, priorizan y gestionan según el análisis y el control del riesgo es la **prueba basada en el riesgo**.

### 5.2.1 Definición del riesgo y atributos del riesgo

- Riesgo: acontecimiento, peligro, amenaza o situación potencial cuya ocurrencia causa un efecto adverso.
- Se caracteriza por dos factores:
  - **Probabilidad del riesgo**: la probabilidad de que ocurra (mayor que cero y menor que uno).
  - **Impacto del riesgo** (daño): las consecuencias de que ocurra.
- Ambos expresan el **nivel de riesgo**: cuanto mayor, más importante es tratarlo.

### 5.2.2 Riesgos de proyecto y riesgos de producto

| Aspecto | Riesgos de proyecto | Riesgos de producto |
|---|---|---|
| Relacionados con | La gestión y el control del proyecto. | Las características de calidad del producto (por ejemplo, las del modelo ISO 25010). |
| Ejemplos | Organizativos (retrasos en la entrega de productos de trabajo, estimaciones inexactas, recortes de costes); de personal (competencias insuficientes, conflictos, problemas de comunicación, escasez de personal); técnicos (desviación del alcance, mal soporte de herramientas); de proveedores (incumplimiento de terceros, quiebra de la empresa de apoyo). | Funcionalidad ausente o incorrecta, cálculos erróneos, errores en ejecución, arquitectura deficiente, algoritmos ineficaces, tiempo de respuesta inadecuado, mala experiencia de usuario, vulnerabilidades de seguridad. |
| Consecuencias | Afectan al calendario, el presupuesto o el alcance, y con ello a la capacidad de alcanzar los objetivos del proyecto. | Insatisfacción del usuario; pérdida de ingresos, confianza o reputación; daños a terceros; altos costes de mantenimiento y sobrecarga del soporte; sanciones penales; en casos extremos, daños físicos, lesiones o muertes. |

### 5.2.3 Análisis del riesgo de producto

- Desde la prueba, su objetivo es crear conciencia del riesgo de producto para concentrar el esfuerzo y minimizar el riesgo residual. Lo ideal es empezarlo pronto en el CVDS.
- **Identificación del riesgo**: generar una lista exhaustiva de riesgos con técnicas como tormenta de ideas, talleres, entrevistas o diagramas causa-efecto.
- **Evaluación del riesgo**: categorizar los riesgos, determinar su probabilidad, impacto y nivel, priorizarlos y proponer cómo tratarlos. La categorización ayuda a asignar la mitigación, porque los riesgos de una misma categoría suelen mitigarse de forma parecida.
- La evaluación puede ser cuantitativa (nivel = probabilidad × impacto), cualitativa (nivel obtenido con una matriz de riesgo) o mixta.
- Sus resultados influyen en la minuciosidad y el alcance de la prueba; se usan para:
  - Determinar el alcance de la prueba.
  - Determinar los niveles concretos y proponer los tipos de prueba.
  - Determinar las técnicas y la cobertura que debe alcanzarse.
  - Estimar el esfuerzo de cada tarea.
  - Priorizar la prueba para encontrar cuanto antes los defectos críticos.
  - Decidir si conviene alguna actividad, además de la prueba, para reducir el riesgo.

### 5.2.4 Control del riesgo de producto

- Comprende todas las medidas que se toman ante los riesgos de producto identificados y evaluados:
  - **Mitigación del riesgo**: implementar las acciones propuestas en la evaluación para reducir el nivel de riesgo.
  - **Monitorización del riesgo**: asegurar que la mitigación es eficaz, obtener información para mejorar la evaluación e identificar riesgos emergentes.
- Opciones de respuesta tras el análisis: mitigación mediante la prueba, aceptación, transferencia o plan de contingencia.
- Medidas para mitigar riesgos de producto mediante la prueba:
  - Elegir probadores con la experiencia y las competencias adecuadas para el tipo de riesgo.
  - Aplicar un nivel adecuado de independencia de la prueba.
  - Hacer revisiones y análisis estático.
  - Aplicar las técnicas y los niveles de cobertura adecuados.
  - Aplicar tipos de prueba que aborden las características de calidad afectadas.
  - Hacer prueba dinámica, incluida la de regresión.

## 5.3 Monitorización de la prueba, control de la prueba y compleción de la prueba

| Actividad | Qué hace |
|---|---|
| Monitorización | Recoge información sobre la prueba para evaluar su avance y medir si se cumplen los criterios de salida o las tareas asociadas (por ejemplo, objetivos de cobertura de riesgos de producto, requisitos o criterios de aceptación). |
| Control | Usa esa información para dar, en forma de directivas de control, la orientación y las acciones correctivas que hagan la prueba más eficaz y eficiente. Ejemplos: repriorizar cuando un riesgo identificado se materializa; reevaluar si un elemento cumple criterios de entrada o salida tras un retrabajo; ajustar el calendario ante un retraso del entorno de prueba; añadir recursos donde y cuando se necesiten. |
| Compleción | Recoge datos de las actividades terminadas para consolidar experiencia, productos de prueba y otra información relevante. Ocurre en hitos: fin de un nivel de prueba, fin de una iteración ágil, fin (o cancelación) de un proyecto de prueba, liberación de un sistema o fin de una entrega de mantenimiento. |

### 5.3.1 Métricas usadas en la prueba

Muestran el avance frente al calendario y el presupuesto previstos, la calidad actual del objeto y la efectividad de las actividades respecto a los objetivos o a una meta de iteración; la monitorización las recoge para apoyar el control y la compleción.

| Categoría | Ejemplos |
|---|---|
| Avance del proyecto | Compleción de tareas, uso de recursos, esfuerzo de prueba. |
| Avance de la prueba | Avance en la implementación de casos y en la preparación del entorno; casos ejecutados o no, superados o fallidos; tiempo de ejecución. |
| Calidad del producto | Disponibilidad, tiempo de respuesta, tiempo medio hasta el fallo. |
| Defectos | Número y prioridad de defectos encontrados y corregidos, densidad de defectos, porcentaje de detección. |
| Riesgo | Nivel de riesgo residual. |
| Cobertura | Cobertura de requisitos, cobertura de código. |
| Coste | Coste de la prueba, coste organizativo de la calidad. |

### 5.3.2 Propósito, contenido y audiencia de los informes de prueba

El suministro de información de prueba resume y comunica la información durante la prueba y después de ella.

| Aspecto | Informe del avance de la prueba | Informe de compleción de la prueba |
|---|---|---|
| Propósito | Apoyar el control continuo; dar información suficiente para modificar calendario, recursos o plan ante desviaciones o cambios de circunstancias. | Resumir una etapa concreta (nivel, ciclo, iteración) y dar información para pruebas posteriores. |
| Cuándo | De forma regular (diaria, semanal, etc.) durante la monitorización y el control. | Al completarse un proyecto, nivel o tipo de prueba, idealmente con sus criterios de salida cumplidos. |
| Contenido | Periodo de prueba; avance (adelanto o retraso, desviaciones notables); obstáculos y sus soluciones; métricas (5.3.1); riesgos nuevos o modificados en el periodo; prueba planificada para el periodo siguiente. | Resumen de la prueba; evaluación de la prueba y de la calidad del producto frente al plan original (objetivos y criterios de salida); desviaciones del plan (calendario, duración, esfuerzo); obstáculos y soluciones; métricas tomadas de los informes de avance; riesgos no mitigados y defectos sin corregir; lecciones aprendidas. |

- Cada audiencia necesita información distinta, lo que influye en la formalidad y la frecuencia: dentro del equipo, el avance se comunica a menudo y de manera informal; el informe de un proyecto terminado sigue una plantilla y se emite una sola vez.
- La norma ISO/IEC/IEEE 29119-3 incluye plantillas y ejemplos de ambos (allí, los de avance se llaman informes de estado de la prueba).

### 5.3.3 Comunicación del estado de la prueba

La mejor forma depende de los intereses de la gestión de la prueba, las estrategias de prueba de la organización, las normas reglamentarias o, en equipos autoorganizados (ver sección 1.5.2 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]), del propio equipo. Opciones:
- Comunicación verbal con el equipo y otros implicados.
- Cuadros de mando: paneles de IC/EC, tableros de tareas y gráficos de quemado.
- Canales electrónicos: correo electrónico, chat.
- Documentación en línea.
- Informes de prueba formales (5.3.2).

Pueden combinarse. En equipos distribuidos, donde la distancia o la diferencia horaria impiden hablar cara a cara, puede convenir una comunicación más formal. Cada implicado se interesa por información distinta, así que la comunicación se adapta a cada uno.

## 5.4 Gestión de la configuración

- En la prueba, la gestión de la configuración (GC) es la disciplina para identificar, controlar y seguir productos de trabajo (planes, estrategias, condiciones, casos, guiones, resultados, registros e informes de prueba) como **elementos de la configuración**.
- En un elemento complejo, como un entorno de prueba, registra sus componentes, sus relaciones y sus versiones. Si el elemento se aprueba para la prueba, pasa a ser una **línea base** y solo puede cambiarse mediante un proceso formal de control de cambios.
- Al crear una nueva línea base, registra qué elementos cambiaron; es posible volver a una línea base anterior para reproducir resultados de pruebas previas.
- Para apoyar la prueba, la GC asegura que:
  - Todos los elementos de configuración, incluidos los elementos de prueba (partes individuales del objeto de prueba), se identifican de forma única, se controlan por versión, se siguen sus cambios y se relacionan entre sí para mantener la trazabilidad durante todo el proceso.
  - Toda la documentación y el software identificados se referencian sin ambigüedad en la documentación de prueba.
- La integración, la entrega y el despliegue continuos, con sus pruebas asociadas, suelen implementarse en un canal DevOps automatizado (ver sección 2.1.4 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]) que normalmente incluye GC automatizada.

## 5.5 Gestión de defectos

- Como encontrar defectos es uno de los objetivos principales, hace falta un proceso de gestión de defectos establecido. Lo que se informa son anomalías que pueden resultar defectos reales u otra cosa (un falso positivo, una solicitud de cambio); se aclara al tratar el informe.
- Las anomalías pueden informarse en cualquier fase del CVDS, de la forma que este determine.
- Como mínimo, el proceso incluye un flujo de trabajo para cada anomalía, desde su descubrimiento hasta su cierre, y reglas de clasificación. El flujo suele cubrir: registrar, analizar y clasificar, decidir la respuesta (corregir o mantener tal cual) y cerrar el informe. Todos los implicados deben seguirlo; conviene tratar igual los defectos de la prueba estática, en especial los del análisis estático.
- Objetivos de un informe de defecto: dar a quienes lo gestionan y resuelven información suficiente; ofrecer un medio para seguir la calidad del producto de trabajo; aportar ideas para mejorar los procesos de desarrollo y prueba.

| Campo típico (prueba dinámica) | Contenido |
|---|---|
| Identificador | Único. |
| Título | Breve resumen de la anomalía. |
| Fecha, organización y autor | Fecha de la observación, organización emisora y autor con su rol. |
| Objeto y entorno | Identificación del objeto de prueba y del entorno de prueba. |
| Contexto | Caso de prueba y actividad en curso, fase del CVDS y otros datos, como la técnica, la lista de comprobación o los datos de prueba usados. |
| Descripción del fallo | Pasos que detectaron la anomalía y lo necesario para reproducirla y resolverla: registros, volcados de base de datos, capturas o grabaciones. |
| Resultados | Esperados y reales. |
| Severidad | Grado de impacto sobre los intereses de los implicados o los requisitos. |
| Prioridad | De la corrección. |
| Estado | Por ejemplo: abierto, aplazado, duplicado, a la espera de corrección, a la espera de prueba de confirmación, reabierto, cerrado, rechazado. |
| Referencias | Por ejemplo, al caso de prueba. |

Las herramientas de gestión de defectos pueden rellenar algunos campos automáticamente (identificador, fecha, autor y estado inicial). La norma ISO/IEC/IEEE 29119-3, que llama a estos documentos informes de incidencias, incluye plantillas y ejemplos.
