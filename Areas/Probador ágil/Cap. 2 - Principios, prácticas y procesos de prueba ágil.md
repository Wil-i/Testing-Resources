---
tags: [capitulo]
area: "[[Areas/Probador ágil/Probador ágil|Probador ágil]]"
capitulo: 2
paginas: "26–36"
duracion: "105 min"
---

# 2. Principios, prácticas y procesos fundamentales de prueba ágil

> Parte de [[Areas/Probador ágil/Probador ágil|Probador ágil]]

**Términos clave:** [[Índice de términos#Prueba de verificación de la construcción|prueba de verificación de la construcción]], [[Índice de términos#Elemento de la configuración|elemento de la configuración]], [[Índice de términos#Gestión de la configuración|gestión de la configuración]]

## Objetivos de aprendizaje
- **NB-AT-2.1.1 (K2)**: describir las diferencias entre las actividades de prueba en proyectos ágiles y no ágiles.
- **NB-AT-2.1.2 (K2)**: describir cómo se integran las actividades de desarrollo y de prueba en proyectos ágiles.
- **NB-AT-2.1.3 (K2)**: describir el papel de la prueba independiente en proyectos ágiles.
- **NB-AT-2.2.1 (K2)**: describir herramientas y técnicas para comunicar el estado de la prueba, incluidos su avance y la calidad del producto.
- **NB-AT-2.2.2 (K2)**: describir cómo evolucionan las pruebas a lo largo de varias iteraciones y por qué la automatización es importante para gestionar el riesgo de regresión.
- **NB-AT-2.3.1 (K2)**: comprender las competencias (personas, dominio y prueba) del probador en un equipo ágil.
- **NB-AT-2.3.2 (K2)**: comprender el rol del probador en un equipo ágil.

## 2.1 Diferencias entre probar en enfoques tradicionales y ágiles

La prueba cambia con el ciclo de vida. Frente a los modelos tradicionales (secuencial como el modelo V, iterativo como RUP), los ágiles difieren en cómo integran prueba y desarrollo, en los productos de trabajo, en la terminología, en los criterios de entrada y salida de los niveles, en el uso de herramientas y en cómo aprovechan la prueba independiente. Las organizaciones adaptan los ciclos de vida; apartarse del ideal ágil (ver sección 1.1 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]) puede ser una adaptación inteligente, y saber adaptarse al contexto es clave para el probador.

### 2.1.1 Actividades de prueba y desarrollo

- Iteraciones muy cortas que producen software funcionando con valor para negocio: planificación de la entrega al inicio, luego iteraciones que empiezan con su propia planificación.
- Desarrollo, integración y prueba ocurren en paralelo y solapados durante toda la iteración; la prueba no es una fase final.
- Todos prueban: los desarrolladores hacen pruebas unitarias, los probadores prueban las prestaciones y los implicados del negocio las prueban durante la implementación, con casos escritos o simplemente usándolas.
- Buenas prácticas:
  - Iteraciones periódicas de consolidación o estabilización para defectos persistentes y deuda técnica.
  - Ninguna prestación está hecha hasta integrarla y probarla con el sistema.
  - "Arreglar primero los bugs": atender al inicio de una iteración los defectos que quedaron de la anterior (con la contra de que el trabajo total de la iteración queda menos claro).
- Con prueba basada en el riesgo, el análisis de alto nivel ocurre en la planificación de la entrega (a menudo dirigido por probadores) y el de riesgos por iteración en su planificación; influye en la secuencia de desarrollo, en la prioridad y profundidad de la prueba y en la estimación (ver sección 3.2 del [[Areas/Probador ágil/Cap. 3 - Métodos, técnicas y herramientas|capítulo 3]]).
- **Trabajo en pareja** (por ejemplo en XP): dos probadores, o un probador con un desarrollador, para desarrollar y probar una prestación; es más difícil con equipos distribuidos, aunque procesos y herramientas ayudan.
- Los probadores pueden actuar como entrenadores de prueba y calidad, fomentando la propiedad colectiva de la calidad.
- Con automatización en todos los niveles, el probador crea, ejecuta, monitoriza y mantiene pruebas automatizadas; la prueba manual se inclina hacia técnicas basadas en la experiencia y en defectos (ataques de software, prueba exploratoria, predicción de errores). Los desarrolladores se centran en pruebas unitarias y los probadores en pruebas automatizadas de integración, sistema e integración de sistemas, por lo que se valora un perfil técnico.
- Como el cambio es constante, se prefiere documentación ligera; la automatización ayuda a absorber el esfuerzo de regresión, siempre que el ritmo de cambio no supere la capacidad del equipo para gestionar sus riesgos.

### 2.1.2 Productos de trabajo de un proyecto

| Categoría | Qué describen o hacen | Productos típicos en ágil |
|---|---|---|
| Orientados al negocio | Qué se necesita y cómo usarlo | Historias de usuario y criterios de aceptación; las colecciones grandes de historias relacionadas son **épicas**, que pueden repartirse entre equipos y esprints y también llevan criterios de aceptación. |
| De desarrollo | Cómo se construye, la implementación y la evaluación de piezas de código | Código y pruebas unitarias automatizadas, creadas después del código o antes (probar primero / desarrollo guiado por pruebas, que funcionan más como especificaciones de diseño ejecutables de bajo nivel). |
| De prueba | Cómo se prueba, las pruebas y sus resultados | Pruebas automatizadas, planes de prueba, catálogos de riesgos de calidad, pruebas manuales, informes de defectos, registros de resultados y métricas; tableros de control (ver 2.2.1). |

- Se evita documentación que no aporte valor al cliente, equilibrando eficiencia con lo necesario para negocio, prueba, desarrollo y mantenimiento; el equipo decide qué productos y qué nivel de detalle en la planificación de la entrega.
- Una historia describe una prestación que cabe en una sola iteración.
- En proyectos regulados, de seguridad física, distribuidos o muy complejos se formaliza más: historias convertidas en especificaciones formales e informes de trazabilidad vertical y horizontal para auditores y reguladores.

### 2.1.3 Niveles de prueba

- En modelos secuenciales, los criterios de salida de un nivel forman parte de los de entrada del siguiente; en algunos iterativos no, y los niveles se solapan entre sí y con requisitos, diseño y desarrollo.
- En ágil el solapamiento se debe a cambios que pueden llegar en cualquier momento de la iteración (en teoría Scrum no los admite tras la planificación, pero en la práctica ocurren).
- Recorrido típico de una historia dentro de la iteración:
  - **Prueba unitaria**, normalmente del desarrollador.
  - **Prueba de aceptación de prestaciones**, a veces dividida en:
    - *Verificación de la prestación*: suele estar automatizada, la hacen desarrolladores o probadores y comprueba los criterios de aceptación.
    - *Validación de la prestación*: suele ser manual y colaborativa con negocio; determina si la prestación es apta para su uso, da visibilidad del avance y retroalimentación real.
- En paralelo corre la regresión: se reejecutan las unitarias y las de verificación de prestaciones de la iteración actual y de las anteriores, normalmente con integración continua.
- Puede haber un nivel de prueba de sistema que empieza cuando la primera historia está lista, con pruebas funcionales y no funcionales (rendimiento, fiabilidad, usabilidad, etc.).
- Formas de aceptación: alfa interna, beta externa, de usuario, operativa, regulatoria y de contrato, al cierre de cada iteración, tras ella o tras una serie de iteraciones.

### 2.1.4 Prueba y gestión de la configuración

- Uso intensivo de herramientas: análisis estático, pruebas unitarias y cobertura; código y pruebas se registran continuamente en el sistema de gestión de la configuración con marcos de construcción y prueba automatizados que habilitan la integración continua.
- Las pruebas funcionales automatizadas de integración y sistema (arneses, herramientas de interfaz de código abierto o comerciales) pueden integrarse en ese marco; por su duración, a veces se ejecutan cada pocos días mientras las unitarias corren en cada registro.
- Objetivo: confirmar que la construcción funciona y se puede instalar; si una prueba falla, el defecto se corrige antes del siguiente registro. Requiere informes en tiempo real y evita los ciclos "construcción, instalación, fallo, reconstrucción, reinstalación".
- Las herramientas ayudan con el riesgo de regresión, pero confiar solo en las unitarias es un problema porque su efectividad para detectar defectos es limitada; también hacen falta pruebas automatizadas de integración y sistema.

### 2.1.5 Opciones de organización para pruebas independientes

| Opción | Ventaja | Inconveniente |
|---|---|---|
| Probadores integrados en el equipo ágil (con muchas pruebas automatizadas por los desarrolladores) | Participan en muchas tareas de prueba. | Riesgo de perder independencia y evaluación objetiva. |
| Equipo de prueba independiente y separado, con probadores asignados a demanda en los últimos días del esprint | Conserva la independencia y la evaluación imparcial. | Poco tiempo, poco conocimiento de las prestaciones nuevas y dificultades de relación con negocio y desarrollo. |
| Equipo independiente con probadores asignados a largo plazo a equipos ágiles desde el inicio | Mantienen independencia y ganan conocimiento del producto y buenas relaciones. | — |

En la tercera opción, el equipo independiente puede sumar especialistas para trabajo a largo plazo o independiente de la iteración: herramientas de automatización, pruebas no funcionales, entornos y datos de prueba, y niveles que no encajan en un esprint (por ejemplo, integración de sistemas).

## 2.2 Situación de la prueba en proyectos ágiles

El estado, el avance y la calidad cambian constantemente; el probador debe comunicarlos para que el equipo decida a tiempo, y actualizar las pruebas manuales y automatizadas porque los cambios afectan a prestaciones de iteraciones anteriores.

### 2.2.1 Comunicar el estado de la prueba, el avance y la calidad del producto

- El avance se mide por tener software funcionando al final de cada iteración. Fuentes: resultados de la automatización, progresión de tareas e historias en el **tablero de tareas ágil** y **gráficos de quemado**.
- Canales: paneles de control en wiki, correos tipo panel de control y comunicación verbal en las reuniones de pie. Las herramientas pueden generar informes automáticamente, recoger métricas del proceso para su mejora y liberar tiempo del probador.
- **Gráfico de quemado**: trabajo pendiente frente al tiempo asignado a la entrega o a la iteración.
- **Tablero de tareas**: tarjetas de historia y tareas de desarrollo, de prueba y otras (creadas en la planificación de la iteración, ver sección 1.2.5 del [[Areas/Probador ágil/Cap. 1 - Desarrollo ágil de software|capítulo 1]]), a menudo con colores por tipo, que avanzan por columnas como por hacer, en curso, verificar y hecho. Las tareas de prueba se ligan a los criterios de aceptación y pasan a hecho cuando sus guiones automatizados, pruebas manuales y exploratorias se aprueban. El equipo revisa el tablero a menudo y resuelve lo que se estanca.
- **Reunión de pie diaria**: todo el equipo, probadores incluidos, responde qué completó, qué completará y qué le bloquea; los bloqueos de prueba se hacen visibles para todos.
- Métricas de calidad del producto: encuestas de satisfacción del cliente y métricas tradicionales (tasas de paso y fallo, descubrimiento de defectos, resultados de confirmación y regresión, densidad de defectos, defectos encontrados y corregidos, cobertura de requisitos, de riesgos y de código, batido de código).
- Las métricas deben ser relevantes para decidir y nunca usarse para premiar, castigar o aislar a nadie.

### 2.2.2 Gestión del riesgo de regresión con casos de prueba manuales y automatizados en evolución

- Con cada iteración crece el producto y el alcance de la prueba; el riesgo de regresión es alto por el batido de código (líneas añadidas, modificadas o eliminadas) y por cambios en prestaciones ya entregadas.
- Para mantener la velocidad sin acumular deuda técnica, hay que invertir cuanto antes en automatización en todos los niveles y mantener actualizados todos los activos de prueba (pruebas automatizadas, casos manuales, datos y demás artefactos), idealmente en una herramienta de gestión de la configuración (control de versiones, acceso para todos, historial).
- Como repetir todo rara vez es posible, en cada iteración se revisan los casos para elegir candidatos al juego de regresión, retirar los obsoletos y valorar su automatización; cuanto más se automatice, menos esfuerzo de regresión y más tiempo para probar lo nuevo.
- La forma de diseñar, redactar y almacenar los casos se define en la planificación de la entrega; las malas prácticas de diseño se agravan con plazos cortos y cambios constantes.
- Las pruebas automatizadas bien escritas son documentación viva; versionadas junto con las construcciones permiten ver qué se probó en cada una.

| Tipo de prueba automatizada | Cuándo se ejecuta | Qué retroalimentación da |
|---|---|---|
| Unitarias | Antes de registrar código en la línea principal; no se registra si alguna falla. | Inmediata sobre la calidad del código y de la construcción, no del producto. |
| De aceptación | Como parte de la construcción completa de integración continua, al menos a diario, no en cada registro. | Sobre la calidad del producto respecto a la última construcción, no sobre su calidad general. |
| De verificación de la construcción | Subconjunto que cubre funcionalidad y puntos de integración críticos, justo tras desplegar una construcción en el entorno de prueba. | Instantánea sobre la estabilidad, para no perder tiempo con una construcción inestable. |
| De regresión | En la construcción principal diaria y al desplegar una nueva construcción en prueba. | Si fallan, el equipo se detiene: se actualiza o retira la prueba si el cambio es legítimo, o se corrige el defecto antes de seguir con prestaciones nuevas. |

Otras tareas de prueba automatizables: generación y carga de datos de prueba, despliegue de construcciones en entornos de prueba, restauración de un entorno a una línea de base y comparación de salidas.

## 2.3 Rol y competencias de un probador en un equipo ágil

La colaboración estrecha con el equipo y con los implicados del negocio condiciona las competencias y actividades del probador.

### 2.3.1 Competencias del probador ágil

- Además de las del nivel básico: automatización de la prueba, desarrollo guiado por pruebas, prueba de aceptación, caja blanca, caja negra y prueba basada en la experiencia.
- Competencias interpersonales; el probador ágil debe:
  - Ser positivo y orientado a soluciones.
  - Pensar de forma crítica, escéptica y orientada a la calidad.
  - Obtener información activamente de los implicados, no solo de especificaciones escritas.
  - Evaluar y comunicar con precisión resultados, avance y calidad.
  - Definir con cliente e implicados historias que se puedan probar, sobre todo sus criterios de aceptación.
  - Colaborar y trabajar en pareja con programadores y otros miembros.
  - Responder rápido al cambio modificando, añadiendo o mejorando casos.
  - Planificar y organizar su propio trabajo.
- El desarrollo continuo de competencias, incluidas las interpersonales, es esencial.

### 2.3.2 El rol de un probador en un equipo ágil

- Genera retroalimentación sobre estado, avance y calidad del producto, y también sobre la calidad del proceso.
- Actividades:
  - Comprender, implementar y actualizar la estrategia de prueba.
  - Medir e informar la cobertura en todas las dimensiones aplicables.
  - Asegurar el uso adecuado de las herramientas de prueba.
  - Configurar, usar y gestionar entornos y datos de prueba.
  - Informar defectos y colaborar en su resolución.
  - Entrenar al equipo en aspectos de prueba.
  - Asegurar que se planifiquen las tareas de prueba en la entrega y la iteración.
  - Aclarar requisitos con desarrollo y negocio (capacidad de ser probado, consistencia y completitud).
  - Participar proactivamente en las retrospectivas proponiendo e implementando mejoras.
- Todos los miembros son responsables de la calidad y hacen tareas de prueba.
- Riesgos organizativos: perder la mentalidad de probador por trabajar tan cerca de desarrollo; tolerar o callar prácticas ineficientes o de baja calidad; no seguir el ritmo de cambio en iteraciones acotadas. Se mitigan con las opciones de independencia de 2.1.5.
