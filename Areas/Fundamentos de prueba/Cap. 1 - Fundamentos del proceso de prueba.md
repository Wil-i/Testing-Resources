---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 1
paginas: "14–26"
duracion: "180 min"
---

# 1. Fundamentos del proceso de prueba

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Cobertura|cobertura]], [[Índice de términos#Depurar|depurar]], [[Índice de términos#Defecto|defecto]], [[Índice de términos#Error|error]], [[Índice de términos#Fallo|fallo]], [[Índice de términos#Calidad|calidad]], [[Índice de términos#Aseguramiento de la calidad|aseguramiento de la calidad]], [[Índice de términos#Causa raíz|causa raíz]], [[Índice de términos#Análisis de prueba|análisis de prueba]], [[Índice de términos#Base de prueba|base de prueba]], [[Índice de términos#Caso de prueba|caso de prueba]], [[Índice de términos#Compleción de la prueba|compleción de la prueba]], [[Índice de términos#Condición de prueba|condición de prueba]], [[Índice de términos#Control de la prueba|control de la prueba]], [[Índice de términos#Datos de prueba|datos de prueba]], [[Índice de términos#Diseño de la prueba|diseño de la prueba]], [[Índice de términos#Ejecución de prueba|ejecución de prueba]], [[Índice de términos#Implementación de prueba|implementación de prueba]], [[Índice de términos#Monitorización de la prueba|monitorización de la prueba]], [[Índice de términos#Objeto de prueba|objeto de prueba]], [[Índice de términos#Objetivo de prueba|objetivo de prueba]], [[Índice de términos#Planificación de prueba|planificación de prueba]], [[Índice de términos#Procedimiento de prueba|procedimiento de prueba]], [[Índice de términos#Resultado de prueba|resultado de prueba]], [[Índice de términos#Prueba|prueba]], [[Índice de términos#Producto de prueba|producto de prueba]], [[Índice de términos#Validación|validación]], [[Índice de términos#Verificación|verificación]]

## Objetivos de aprendizaje
- **FL-1.1.1 (K1)**: identificar objetivos de prueba característicos.
- **FL-1.1.2 (K2)**: diferenciar entre probar y depurar.
- **FL-1.2.1 (K2)**: dar ejemplos de por qué es necesario probar.
- **FL-1.2.2 (K1)**: recordar la relación entre prueba y aseguramiento de la calidad.
- **FL-1.2.3 (K2)**: distinguir entre causa raíz, error, defecto y fallo.
- **FL-1.3.1 (K2)**: explicar los siete principios de la prueba.
- **FL-1.4.1 (K2)**: resumir las actividades y tareas de prueba.
- **FL-1.4.2 (K2)**: explicar cómo influye el contexto en el proceso de prueba.
- **FL-1.4.3 (K2)**: diferenciar los productos de prueba que soportan cada actividad.
- **FL-1.4.4 (K2)**: explicar el valor de mantener la trazabilidad.
- **FL-1.4.5 (K2)**: comparar los roles de la prueba.
- **FL-1.5.1 (K2)**: dar ejemplos de competencias genéricas necesarias para probar.
- **FL-1.5.2 (K1)**: recordar las ventajas del enfoque de equipo completo.
- **FL-1.5.3 (K2)**: distinguir ventajas e inconvenientes de la independencia de la prueba.

## 1.1 ¿Qué es probar?

El software que no funciona como se espera puede causar pérdidas económicas, de tiempo o de reputación y, en casos extremos, lesiones o muertes. Probar evalúa la calidad del software y ayuda a reducir el riesgo de que falle en operación.

- Probar es un conjunto de actividades para descubrir defectos y evaluar la calidad de artefactos de software; el artefacto que se prueba es el **objeto de prueba**.
- Dos ideas erróneas frecuentes:
  - Que probar es solo ejecutar pruebas y revisar resultados: incluye otras actividades y debe alinearse con el ciclo de vida de desarrollo (ver [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]).
  - Que probar es solo verificar: además de la **verificación** (¿cumple los requisitos especificados?) incluye la **validación** (¿satisface las necesidades de usuarios e implicados en su entorno operativo?).
- La prueba puede ser **dinámica** (ejecuta el software) o **estática** (no lo ejecuta: revisiones y análisis estático, ver [[Areas/Fundamentos de prueba/Cap. 3 - Prueba estática|capítulo 3]]). La dinámica obtiene casos de prueba con técnicas y enfoques de prueba (ver [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]]).
- No es solo técnica: hay que planificarla, gestionarla, estimarla, monitorizarla y controlarla (ver [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]]). Se apoya en herramientas (ver [[Areas/Fundamentos de prueba/Cap. 6 - Herramientas de prueba|capítulo 6]]), pero es sobre todo una actividad intelectual que exige conocimiento especializado, capacidad analítica y pensamiento crítico y sistémico.
- Ampliación: ISO/IEC/IEEE 29119-1.

### 1.1.1 Objetivos de prueba

Objetivos característicos:
- Evaluar productos de trabajo como requisitos, historias de usuario, diseños y código.
- Provocar fallos y encontrar defectos.
- Lograr la cobertura necesaria del objeto de prueba.
- Reducir el riesgo asociado a una calidad insuficiente.
- Verificar que se cumplen los requisitos especificados y los contractuales, legales y normativos.
- Dar a los implicados información para decidir con fundamento.
- Generar confianza en la calidad del objeto de prueba.
- Validar que el objeto está completo y funciona como esperan los implicados.

Los objetivos cambian con el contexto: el producto de trabajo, el nivel de prueba, los riesgos, el ciclo de vida seguido y factores de negocio como la estructura corporativa, la competencia o el tiempo de comercialización.

### 1.1.2 Probar y depurar

Son actividades distintas. Probar desencadena fallos causados por defectos (prueba dinámica) o encuentra defectos directamente (prueba estática); depurar busca, analiza y elimina las causas.

| Origen del hallazgo | Qué hace la depuración |
|---|---|
| Una prueba dinámica provoca un fallo | Reproduce el fallo, lo diagnostica (encuentra la causa raíz) y corrige la causa. |
| Una prueba estática identifica un defecto | Solo elimina el defecto: no hace falta reproducir ni diagnosticar, porque la prueba estática encuentra defectos directamente y no provoca fallos. |

- Después de corregir, la **prueba de confirmación** comprueba si el problema quedó resuelto; conviene que la haga quien ejecutó la prueba inicial.
- Puede seguir una **prueba de regresión** para ver si la corrección provoca fallos en otras partes del objeto de prueba (ver sección 2.2.3 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]).

## 1.2 ¿Por qué es necesario probar?

Como forma de control de la calidad, la prueba ayuda a cumplir los objetivos acordados dentro del alcance, el tiempo, la calidad y el presupuesto. Su aporte no se limita al equipo de prueba: cualquier implicado con competencias de prueba puede contribuir al éxito del proyecto.

### 1.2.1 Contribuciones de la prueba al éxito

- Detecta defectos de forma rentable; la depuración (actividad ajena a la prueba) los elimina, así que la prueba mejora la calidad de forma indirecta.
- Evalúa directamente la calidad del objeto en distintas etapas del ciclo de vida; esas mediciones alimentan decisiones de gestión, como pasar a la siguiente etapa o entregar.
- Representa de forma indirecta a los usuarios: los probadores mantienen presentes sus necesidades durante todo el desarrollo, ya que implicar a usuarios representativos suele ser caro o inviable.
- Puede ser obligatoria por requisitos contractuales o legales o por estándares reglamentarios.

### 1.2.2 Prueba y aseguramiento de la calidad (AC)

"Prueba" y "aseguramiento de la calidad" suelen usarse como sinónimos, pero no lo son: la prueba es una forma de **control de la calidad** (CC).

| Aspecto | Control de la calidad (CC) | Aseguramiento de la calidad (AC) |
|---|---|---|
| Enfoque | Correctivo, orientado al producto. | Preventivo, orientado a los procesos. |
| Foco | Actividades que llevan a niveles de calidad adecuados. | Implementar y mejorar procesos: un buen proceso bien seguido produce un buen producto. |
| Alcance | La prueba es una de sus formas principales; otras son los métodos formales (comprobación de modelos y prueba de corrección), la simulación y los prototipos. | Se aplica al desarrollo y a la prueba; es responsabilidad de todos los participantes del proyecto. |
| Uso de los resultados de prueba | Corregir defectos. | Retroalimentar sobre el rendimiento de los procesos de desarrollo y prueba. |

### 1.2.3 Errores, defectos, fallos y causas raíz

Las personas cometen **errores** (equivocaciones) que producen **defectos**, y estos pueden dar lugar a **fallos**.

| Concepto | Qué es | Precisiones |
|---|---|---|
| Error | Equivocación humana. | Se debe a presión de tiempo, complejidad de productos, procesos, infraestructura o interacciones, cansancio o falta de formación. |
| Defecto | Imperfección en la documentación (especificación de requisitos, guion de prueba), el código fuente o un artefacto de apoyo (archivo de construcción). | Los introducidos al inicio del ciclo de vida, si no se detectan, generan artefactos defectuosos después. Al ejecutarse, algunos siempre provocan fallos, otros solo en ciertas circunstancias y otros nunca. |
| Fallo | El sistema no hace lo que debería o hace lo que no debería. | Además de errores y defectos, puede deberse a condiciones ambientales (radiación o campos electromagnéticos que dañan el firmware). |
| Causa raíz | Razón fundamental por la que ocurre un problema, por ejemplo la situación que lleva a un error. | Se identifica con el análisis de la causa raíz al producirse un fallo o hallarse un defecto; tratarla (por ejemplo, eliminándola) puede evitar o reducir fallos o defectos similares. |

## 1.3 Principios de la prueba

El programa recoge siete principios generales aplicables a toda prueba:

| N.º | Principio | Idea clave | Ver |
|---|---|---|---|
| 1 | La prueba muestra la presencia de defectos, no su ausencia | Reduce la probabilidad de que queden defectos ocultos, pero aunque no encuentre ninguno no demuestra que el objeto sea correcto. | — |
| 2 | La prueba exhaustiva es imposible | Probarlo todo solo es viable en casos triviales; el esfuerzo se concentra con técnicas de prueba, priorización de casos y prueba basada en el riesgo. | cap. 4; 5.1.5; 5.2 |
| 3 | La prueba temprana ahorra tiempo y dinero | Eliminar defectos pronto evita defectos derivados y reduce el coste de la calidad; la prueba estática y la dinámica deben empezar lo antes posible. | cap. 3; cap. 4 |
| 4 | Los defectos se agrupan | Pocos componentes concentran la mayoría de los defectos o de los fallos en operación; las agrupaciones previstas y observadas alimentan la prueba basada en el riesgo. | 5.2 |
| 5 | Las pruebas se desgastan | Repetidas muchas veces dejan de encontrar defectos nuevos; hay que modificar pruebas y datos o escribir pruebas nuevas. La repetición sí es útil, por ejemplo, en la regresión automatizada. | 2.2.3 |
| 6 | La prueba depende del contexto | No existe un enfoque universal; se prueba de forma distinta en contextos distintos. | — |
| 7 | Falacia de la ausencia de defectos | Verificar a fondo los requisitos y corregir todos los defectos no garantiza un sistema que satisfaga a los usuarios, cumpla los objetivos de negocio y compita; además de verificar hay que validar. | — |

Las referencias de la columna "Ver" corresponden al [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]] (2.2.3), al [[Areas/Fundamentos de prueba/Cap. 3 - Prueba estática|capítulo 3]], al [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]] y al [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]] (5.1.5 y 5.2).

## 1.4 Actividades de prueba, productos de prueba y roles de prueba

Aunque la prueba depende del contexto, hay conjuntos comunes de actividades sin los cuales es difícil alcanzar los objetivos; juntos forman el **proceso de prueba**. Qué actividades se incluyen, cómo se implementan y cuándo se decide en la planificación (ver sección 5.1 del [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]]). Ampliación: ISO/IEC/IEEE 29119-2.

### 1.4.1 Actividades y tareas de prueba

Parecen secuenciales, pero suelen hacerse de forma iterativa o en paralelo y adaptarse al sistema y al proyecto.

| Actividad | Qué incluye | Ver |
|---|---|---|
| Planificación | Definir los objetivos de prueba y elegir el enfoque que mejor los cumpla dentro de las restricciones del contexto. | 5.1 |
| Monitorización y control | Monitorización: comprobar continuamente las actividades y comparar el avance real con el plan. Control: tomar las medidas necesarias para cumplir los objetivos. | 5.3 |
| Análisis | Analizar la base de prueba para identificar prestaciones que se pueden probar y definir y priorizar las condiciones de prueba con sus riesgos; evaluar la base y los objetos para detectar defectos y valorar su capacidad de ser probados. Responde a "¿qué probar?" en términos de criterios de cobertura medibles. | 5.2; cap. 4 |
| Diseño | Convertir las condiciones en casos de prueba y otros productos (como contratos de prueba); identificar elementos de cobertura que guían las entradas de los casos; definir requisitos de datos, diseñar el entorno e identificar infraestructura y herramientas. Responde a "¿cómo probar?". | cap. 4 |
| Implementación | Crear o adquirir los productos necesarios para ejecutar (por ejemplo, datos); organizar casos en procedimientos y juegos de prueba; crear guiones manuales y automatizados; priorizar procedimientos en un calendario de ejecución; montar el entorno y verificar su configuración. | 5.1.5 |
| Ejecución | Ejecutar según el calendario, de forma manual o automatizada (también prueba continua o sesiones en pareja); comparar resultados reales con esperados; registrar resultados; analizar anomalías e informar de ellas a partir de los fallos observados. | 5.5 |
| Compleción | En hitos (entrega, fin de iteración, fin de un nivel): tratar defectos no resueltos, solicitudes de cambio o elementos del trabajo acumulado; archivar o entregar los productos reutilizables; dejar el entorno en el estado acordado; extraer lecciones aprendidas y mejoras; crear y comunicar el informe de compleción. | 2.1.6 |

La columna "Ver" remite al [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]] (5.1, 5.1.5, 5.2, 5.3 y 5.5), al [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]] y al [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]] (2.1.6).

### 1.4.2 El proceso de prueba en contexto

La prueba forma parte de los procesos de desarrollo de la organización, la financian los implicados y su fin último es satisfacer sus necesidades de negocio. Por eso su forma depende de factores de contexto:

| Factor | Ejemplos |
|---|---|
| Implicados | Necesidades, expectativas, requisitos, disposición a cooperar. |
| Miembros del equipo | Competencias, conocimientos, experiencia, disponibilidad, necesidades de formación. |
| Dominio del negocio | Criticidad del objeto de prueba, riesgos identificados, necesidades del mercado, normativa legal. |
| Factores técnicos | Tipo de software, arquitectura del producto, tecnología. |
| Restricciones del proyecto | Alcance, tiempo, presupuesto, recursos. |
| Factores organizativos | Estructura, políticas, prácticas. |
| Ciclo de vida de desarrollo | Prácticas de ingeniería, métodos de desarrollo. |
| Herramientas | Disponibilidad, usabilidad, cumplimiento. |

Estos factores influyen en la estrategia de prueba, las técnicas, el grado de automatización, la cobertura requerida, el detalle de la documentación y el suministro de información.

### 1.4.3 Productos de prueba

Los productos de prueba son la salida de las actividades de 1.4.1. Cada organización los produce, nombra, organiza y gestiona de forma distinta; una gestión de la configuración adecuada asegura su consistencia e integridad (ver sección 5.4 del [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]]). Lista no exhaustiva:

| Actividad | Productos de trabajo típicos |
|---|---|
| Planificación | Plan de prueba, calendario de prueba, registro de riesgos (riesgos con su probabilidad, impacto y mitigación) y criterios de entrada y salida; los tres últimos suelen formar parte del plan. |
| Monitorización y control | Informes del avance de la prueba, documentación de las directivas de control e información sobre riesgos. |
| Análisis | Condiciones de prueba priorizadas (por ejemplo, criterios de aceptación) e informes de defectos sobre la base de prueba, si no se corrigen directamente. |
| Diseño | Casos de prueba priorizados, contratos de prueba, elementos de cobertura y requisitos de datos y de entorno. |
| Implementación | Procedimientos de prueba, guiones automatizados, juegos de prueba, datos de prueba, calendario de ejecución y elementos del entorno (stubs, controladores, simuladores, virtualización de servicios). |
| Ejecución | Registros de prueba e informes de defectos. |
| Compleción | Informe de compleción, acciones de mejora para proyectos o iteraciones siguientes, lecciones aprendidas y solicitudes de cambio (por ejemplo, como elementos del trabajo acumulado del producto). |

El programa remite para estos productos a las secciones 5.1, 5.2, 5.3, 5.3.2 y 5.5 del [[Areas/Fundamentos de prueba/Cap. 5 - Gestión de las actividades de prueba|capítulo 5]] y a la 4.5.2 del [[Areas/Fundamentos de prueba/Cap. 4 - Análisis y diseño de la prueba|capítulo 4]].

### 1.4.4 Trazabilidad entre la base de prueba y los productos de prueba

- Una monitorización y un control efectivos exigen establecer y mantener la trazabilidad entre los elementos de la base de prueba, sus productos asociados (condiciones, riesgos, casos), los resultados y los defectos.
- La trazabilidad permite evaluar la cobertura; conviene definir criterios de cobertura medibles en la base, que pueden servir como indicadores clave de rendimiento del cumplimiento de los objetivos (1.1.1). Por ejemplo:
  - Casos de prueba → requisitos: verifica que los requisitos están cubiertos.
  - Resultados de prueba → riesgos: permite evaluar el riesgo residual del objeto.
- Otros beneficios: determinar el impacto de los cambios, facilitar auditorías, cumplir criterios de gobernanza de TI, hacer más comprensibles los informes de avance y compleción, comunicar aspectos técnicos a los implicados y evaluar la calidad del producto, la capacidad del proceso y el avance frente a los objetivos de negocio.

### 1.4.5 Roles en la prueba

| Rol | Responsabilidad | Actividades principales |
|---|---|---|
| Gestión de prueba | Global sobre el proceso de prueba, el equipo y la dirección de las actividades. | Planificación, monitorización y control, compleción. |
| Prueba | Global sobre el aspecto técnico (de ingeniería) de la prueba. | Análisis, diseño, implementación y ejecución. |

- Las tareas de cada rol dependen del contexto del proyecto y del producto, de las competencias de las personas y de la organización.
- En el desarrollo ágil, parte de la gestión de prueba puede recaer en el equipo ágil; las tareas que abarcan varios equipos o toda la organización pueden quedar en jefes de prueba ajenos al equipo.
- Distintas personas pueden asumir los roles en momentos distintos (jefe de equipo, jefe de prueba, jefe de desarrollo) y una misma persona puede tener ambos a la vez.

## 1.5 Competencias esenciales y buenas prácticas en la prueba

La competencia es la capacidad de hacer algo bien, fruto del conocimiento, la práctica y la aptitud. Un buen probador trabaja eficazmente en equipo y puede probar con distintos niveles de independencia.

### 1.5.1 Competencias genéricas necesarias para probar

| Competencia | Para qué sirve |
|---|---|
| Conocimiento de prueba | Aumentar la efectividad, por ejemplo usando técnicas de prueba. |
| Minuciosidad, cuidado, curiosidad, atención al detalle, método | Encontrar defectos, sobre todo los difíciles. |
| Comunicación, escucha activa, trabajo en equipo | Interactuar con los implicados, transmitir información, hacerse entender e informar y discutir defectos. |
| Pensamiento analítico y crítico, creatividad | Aumentar la efectividad de las pruebas. |
| Conocimientos técnicos | Aumentar la eficiencia, por ejemplo con herramientas adecuadas. |
| Conocimiento del dominio | Entender a los usuarios finales y representantes de negocio y comunicarse con ellos. |

El probador suele traer malas noticias y es frecuente culpar al mensajero. Los resultados pueden percibirse como una crítica al producto y a su autor, el sesgo de confirmación dificulta aceptar información contraria a lo que se cree y hay quien ve la prueba como destructiva. Por eso la comunicación es crucial: los defectos y fallos se comunican de forma constructiva.

### 1.5.2 Enfoque de equipo completo

- Práctica procedente de la Programación Extrema (ver sección 2.1 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]) que se apoya en la capacidad de trabajar en equipo.
- Cualquier miembro con los conocimientos necesarios puede hacer cualquier tarea y todos responden por la calidad; el equipo comparte espacio de trabajo, físico o virtual, porque la ubicación común facilita la comunicación.
- Mejora la dinámica del equipo, la comunicación y la colaboración, y crea sinergia entre los distintos conjuntos de competencias.
- El probador ayuda a los representantes de negocio a crear pruebas de aceptación adecuadas y acuerda con los desarrolladores la estrategia de prueba y los enfoques de automatización; así transfiere conocimiento de prueba e influye en el producto.
- No siempre es apropiado: en contextos críticos para la seguridad puede necesitarse un alto nivel de independencia.

### 1.5.3 Independencia de la prueba

Cierta independencia hace al probador más eficaz encontrando defectos, porque sus sesgos cognitivos difieren de los del autor. No sustituye a la familiaridad: los desarrolladores encuentran muchos defectos en su propio código.

| Quién prueba | Nivel de independencia |
|---|---|
| El propio autor | Ninguna |
| Compañeros del autor en el mismo equipo | Cierta |
| Probadores de fuera del equipo, dentro de la organización | Alta |
| Probadores externos a la organización | Muy alta |

En la mayoría de proyectos conviene combinar niveles: por ejemplo, desarrolladores en la prueba de integración de componentes, el equipo de prueba en la prueba de sistema y de integración de sistemas, y representantes de negocio en la de aceptación.

| Ventajas | Inconvenientes |
|---|---|
| Por su formación, perspectiva técnica y sesgos distintos, el probador independiente reconoce tipos de fallos y defectos diferentes a los que ven los desarrolladores. | Puede quedar aislado del equipo de desarrollo: falta de colaboración, problemas de comunicación o relación de confrontación. |
| Puede verificar, cuestionar o refutar los supuestos de los implicados durante la especificación y la implementación. | Los desarrolladores pueden perder el sentido de responsabilidad por la calidad. |
| | Puede verse como un cuello de botella o como culpable de los retrasos en la entrega. |
