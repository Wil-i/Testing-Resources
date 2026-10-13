---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 4
paginas: "44–57"
duracion: "390 min"
---

# 4. Análisis y diseño de la prueba

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Criterios de aceptación|criterios de aceptación]], [[Índice de términos#Desarrollo guiado por prueba de aceptación|desarrollo guiado por prueba de aceptación]], [[Índice de términos#Técnica de prueba de caja negra|técnica de prueba de caja negra]], [[Índice de términos#Análisis del valor frontera|análisis del valor frontera]], [[Índice de términos#Cobertura de rama|cobertura de rama]], [[Índice de términos#Prueba basada en lista de comprobación|prueba basada en lista de comprobación]], [[Índice de términos#Enfoque de prueba basado en la colaboración|enfoque de prueba basado en la colaboración]], [[Índice de términos#Cobertura|cobertura]], [[Índice de términos#Elemento de cobertura|elemento de cobertura]], [[Índice de términos#Prueba de tabla de decisión|prueba de tabla de decisión]], [[Índice de términos#Partición de equivalencia|partición de equivalencia]], [[Índice de términos#Predicción de errores|predicción de errores]], [[Índice de términos#Técnica de prueba basada en la experiencia|técnica de prueba basada en la experiencia]], [[Índice de términos#Prueba exploratoria|prueba exploratoria]], [[Índice de términos#Prueba de transición de estado|prueba de transición de estado]], [[Índice de términos#Cobertura de sentencia|cobertura de sentencia]], [[Índice de términos#Técnica de prueba|técnica de prueba]], [[Índice de términos#Técnica de prueba de caja blanca|técnica de prueba de caja blanca]]

## Objetivos de aprendizaje
- **FL-4.1.1 (K2)**: distinguir entre técnicas de caja negra, de caja blanca y basadas en la experiencia.
- **FL-4.2.1 (K3)**: usar la partición de equivalencia para obtener casos de prueba.
- **FL-4.2.2 (K3)**: usar el análisis del valor frontera para obtener casos de prueba.
- **FL-4.2.3 (K3)**: usar la prueba de tabla de decisión para obtener casos de prueba.
- **FL-4.2.4 (K3)**: usar la prueba de transición de estado para obtener casos de prueba.
- **FL-4.3.1 (K2)**: explicar la prueba de sentencia.
- **FL-4.3.2 (K2)**: explicar la prueba de rama.
- **FL-4.3.3 (K2)**: explicar el valor de la prueba de caja blanca.
- **FL-4.4.1 (K2)**: explicar la predicción de errores.
- **FL-4.4.2 (K2)**: explicar la prueba exploratoria.
- **FL-4.4.3 (K2)**: explicar la prueba basada en lista de comprobación.
- **FL-4.5.1 (K2)**: explicar cómo redactar historias de usuario en colaboración con desarrolladores y representantes de negocio.
- **FL-4.5.2 (K2)**: clasificar las opciones para redactar criterios de aceptación.
- **FL-4.5.3 (K3)**: usar el desarrollo guiado por prueba de aceptación (DGPA) para obtener casos de prueba.

## 4.1 Introducción a las técnicas de prueba

Las técnicas de prueba apoyan el análisis (qué probar) y el diseño (cómo probar): permiten obtener de forma sistemática un conjunto relativamente pequeño pero suficiente de casos, y ayudan a definir condiciones de prueba, identificar elementos de cobertura y determinar datos de prueba. Ampliación: ISO/IEC/IEEE 29119-4.

| Categoría | En qué se basa | Consecuencias |
|---|---|---|
| Caja negra (basadas en la especificación) | Comportamiento especificado del objeto, sin mirar su estructura interna. | Los casos no dependen de la implementación: si esta cambia pero el comportamiento requerido no, siguen siendo útiles. |
| Caja blanca (basadas en la estructura) | Estructura interna y procesamiento del objeto. | Los casos dependen del diseño, así que solo pueden crearse tras el diseño o la implementación. |
| Basadas en la experiencia | Conocimiento y experiencia del probador. | Su efectividad depende de las competencias del probador; detectan defectos que se escapan a las otras dos, por lo que son complementarias. |

## 4.2 Técnicas de prueba de caja negra

El programa trata cuatro técnicas habituales: partición de equivalencia, análisis del valor frontera, prueba de tabla de decisión y prueba de transición de estado.

### 4.2.1 Partición de equivalencia

- La partición de equivalencia (PE) divide los datos en particiones cuyos elementos se espera que el objeto procese igual. Si un valor de una partición revela un defecto, cualquier otro valor de esa partición debería revelarlo también: basta una prueba por partición.
- Se aplica a cualquier dato relacionado con el objeto: entradas, salidas, elementos de configuración, valores internos, valores temporales y parámetros de interfaz.
- Las particiones pueden ser continuas o discretas, ordenadas o no, finitas o infinitas; no deben solaparse ni estar vacías.
- Con objetos simples es fácil, pero en la práctica entender cómo trata el objeto cada valor suele ser complicado: hay que particionar con cuidado.
- **Partición válida** (valores válidos) y **no válida** (valores no válidos). Su definición varía entre equipos y organizaciones:
  - Válidos: los que el objeto debe procesar, o aquellos cuyo procesamiento define la especificación.
  - No válidos: los que el objeto debe ignorar o rechazar, o aquellos cuyo procesamiento la especificación no define.
- Con varios conjuntos de particiones (por ejemplo, varios parámetros de entrada), un caso cubre particiones de distintos conjuntos. El criterio más sencillo es la cobertura **Cada Elección**: usar al menos una vez cada partición de cada conjunto; no tiene en cuenta combinaciones de particiones.

### 4.2.2 Análisis del valor frontera

- El análisis del valor frontera (AVF) ejercita las fronteras de las particiones, por lo que solo sirve para particiones ordenadas. Los valores mínimo y máximo de una partición son sus valores frontera; si dos elementos pertenecen a una partición, todos los intermedios también.
- Se centra en las fronteras porque es donde los desarrolladores se equivocan con más probabilidad: fronteras desplazadas por encima o por debajo de lo previsto, u omitidas.

| Versión | Elementos de cobertura por frontera | 100 % de cobertura | Medida (en %) |
|---|---|---|---|
| AVF de 2 valores | El valor frontera y su vecino más cercano de la partición adyacente. | Ejercitar todos los valores frontera identificados. | Valores frontera ejercitados ÷ valores frontera identificados. |
| AVF de 3 valores | El valor frontera y sus dos vecinos (algunos elementos pueden no ser valores frontera). | Ejercitar todos los valores frontera y sus vecinos. | Valores frontera y vecinos ejercitados ÷ total identificado. |

El AVF de 3 valores es más riguroso: puede detectar defectos que el de 2 valores pasa por alto. Ejemplo: si la decisión "si (x ≤ 10)" se implementó como "si (x = 10)", los datos del AVF de 2 valores (x = 10, x = 11) no lo detectan, pero x = 9, que aporta el de 3 valores, probablemente sí. En el texto fuente ambas condiciones aparecen como "x = 10"; el operador "≤" de la condición prevista se perdió en la extracción o la traducción.

### 4.2.3 Prueba de tabla de decisión

- Sirve para probar requisitos que especifican cómo distintas combinaciones de condiciones producen resultados distintos; registra con eficacia lógica compleja, como reglas de negocio.
- Las filas son condiciones y acciones; cada columna es una **regla de decisión**: una combinación única de condiciones con sus acciones.
- Tablas de entrada limitada: valores booleanos. Tablas de entrada ampliada: algunas condiciones o acciones toman valores múltiples (rangos, particiones de equivalencia, valores discretos).

| Notación | Significado |
|---|---|
| V | La condición se cumple. |
| F | La condición no se cumple. |
| – | El valor de la condición es irrelevante para la acción. |
| N/A | La condición es inviable para esa regla. |
| X | La acción debe producirse. |
| (en blanco) | La acción no debe producirse. |

- Una tabla completa tiene una columna por cada combinación de condiciones. Se simplifica eliminando combinaciones inviables y se minimiza fusionando columnas en las que algunas condiciones no afectan al resultado (los algoritmos de minimización quedan fuera del programa).
- **Cobertura**: los elementos de cobertura son las columnas con combinaciones factibles; el 100 % exige ejercitarlas todas; se mide como columnas ejercitadas ÷ columnas factibles.
- Fortalezas: enfoque sistemático que identifica todas las combinaciones (algunas se pasarían por alto) y revela lagunas o contradicciones en los requisitos.
- Debilidad: el número de reglas crece exponencialmente con las condiciones; para reducirlo se usa una tabla minimizada o un enfoque basado en el riesgo.

### 4.2.4 Prueba de transición de estado

- Un **diagrama de transición de estados** modela el comportamiento mostrando estados posibles y transiciones válidas. Una transición la inicia un evento, opcionalmente calificado por una condición de guarda; se supone instantánea y puede provocar una acción. Etiqueta habitual: "evento [condición de guarda] / acción" (la traducción incluye un corchete de cierre de más); guarda y acción se omiten si no existen o no son relevantes.
- Una **tabla de estados** es un modelo equivalente: filas = estados, columnas = eventos (con guardas si las hay), celdas = transiciones con el estado destino y las acciones. A diferencia del diagrama, muestra explícitamente las transiciones no válidas (celdas vacías).
- Un caso de prueba suele ser una secuencia de eventos que produce una secuencia de cambios de estado (y acciones); normalmente cubre varias transiciones.

| Criterio | Elementos de cobertura | 100 % exige | Medida (en %) |
|---|---|---|---|
| Todos los estados | Estados. | Visitar todos los estados. | Estados visitados ÷ total de estados. |
| Transiciones válidas (cobertura de conmutador 0) | Transiciones válidas únicas. | Ejercitar todas las transiciones válidas. | Válidas ejercitadas ÷ total de válidas. |
| Todas las transiciones | Todas las transiciones de la tabla de estados. | Ejercitar todas las válidas e intentar todas las no válidas. | Válidas y no válidas ejercitadas o intentadas ÷ total de válidas y no válidas. |

- Probar una sola transición no válida por caso evita el **enmascaramiento de defectos** (que un defecto impida detectar otro).
- Relación entre criterios: todos los estados es más débil que transiciones válidas, porque suele lograrse sin ejercitar todas las transiciones. Transiciones válidas es el criterio más usado y su cobertura completa garantiza la de todos los estados. La cobertura completa de todas las transiciones garantiza ambas y debería ser el mínimo para software crítico para la misión y la seguridad física.

## 4.3 Técnicas de prueba de caja blanca

El programa se centra, por su popularidad y sencillez, en dos técnicas relacionadas con el código: prueba de sentencia y prueba de rama. Quedan fuera las técnicas más rigurosas de entornos críticos o de alta integridad, las de niveles superiores (como la prueba de API) y las de cobertura no basada en código (como la cobertura de neuronas en redes neuronales).

### 4.3.1 Prueba de sentencia y cobertura de sentencia

- Elementos de cobertura: sentencias ejecutables. Se diseñan casos que ejerciten sentencias hasta un nivel aceptable; la cobertura es sentencias ejercitadas ÷ sentencias ejecutables, en porcentaje.
- Con el 100 % se ejecuta al menos una vez cada sentencia, incluida cualquiera con un defecto, lo que puede provocar un fallo que lo revele.
- Límites: no detecta todos los defectos, como los que dependen de los datos (una división por cero que solo falla con denominador cero), ni garantiza ejercitar toda la lógica de decisión, porque pueden quedar ramas sin ejercitar (4.3.2).

### 4.3.2 Prueba de rama y cobertura de rama

- Una **rama** es una transferencia de control entre dos nodos del grafo de flujo de control. Puede ser incondicional (código en línea recta) o condicional (resultado de una decisión).
- Elementos de cobertura: ramas. La cobertura es ramas ejercitadas ÷ total de ramas, en porcentaje.
- Con el 100 % se ejercitan todas las ramas, incondicionales y condicionales. Las condicionales suelen ser el resultado verdadero o falso de un "if...then", el resultado de un switch/case o la decisión de salir o seguir en un bucle.
- Límite: puede no detectar defectos que requieren recorrer un camino concreto.

| Aspecto | Prueba de sentencia | Prueba de rama |
|---|---|---|
| Elemento de cobertura | Sentencia ejecutable | Rama (incondicional o condicional) |
| Qué garantiza al 100 % | Cada sentencia se ejecuta al menos una vez | Cada rama se ejercita; también el 100 % de sentencias |
| Qué puede escaparse | Defectos dependientes de datos; ramas no ejercitadas | Defectos que exigen un camino específico |

La cobertura de rama **subsume** a la de sentencia: todo conjunto de casos con 100 % de ramas logra 100 % de sentencias, pero no al revés.

### 4.3.3 El valor de la prueba de caja blanca

- Fortaleza común: tiene en cuenta toda la implementación, lo que facilita detectar defectos aunque la especificación sea vaga, obsoleta o incompleta.
- Debilidad: si el software no implementa uno o más requisitos, puede no detectar esos defectos de omisión.
- Puede usarse en la prueba estática (por ejemplo, en ejecuciones simuladas del código): sirve para revisar código aún no ejecutable, pseudocódigo y otra lógica de alto nivel que pueda modelarse con un grafo de flujo de control.
- Hacer solo prueba de caja negra no mide la cobertura real del código. Las medidas de caja blanca dan una medición objetiva y la información necesaria para generar pruebas adicionales que aumenten la cobertura y, con ella, la confianza en el código.

## 4.4 Técnicas de prueba basadas en la experiencia

| Técnica | Se apoya en | Útil sobre todo para |
|---|---|---|
| Predicción de errores | Conocimiento de errores, defectos y fallos pasados o típicos. | Anticipar dónde y cómo fallará el software (ataques de defecto). |
| Prueba exploratoria | Aprendizaje simultáneo del objeto mientras se diseña, ejecuta y evalúa. | Especificaciones escasas, presión de tiempo o complemento de técnicas formales. |
| Prueba basada en lista de comprobación | Lista de condiciones construida con experiencia y análisis de defectos. | Dar directrices y cierta consistencia sin casos detallados. |

### 4.4.1 Predicción de errores

- Anticipa errores, defectos y fallos según el conocimiento del probador: cómo funcionó la aplicación en el pasado, qué errores suelen cometer los desarrolladores y qué defectos producen, y qué fallos aparecieron en aplicaciones similares.

| Ámbito | Ejemplos de errores, defectos o fallos |
|---|---|
| Entrada | No se acepta una entrada correcta; parámetros erróneos o ausentes. |
| Salida | Formato incorrecto; resultado erróneo. |
| Lógica | Casos ausentes; operador erróneo. |
| Cálculo | Operando incorrecto; cálculo erróneo. |
| Interfaces | Desajuste de parámetros; tipos incompatibles. |
| Datos | Inicialización incorrecta; tipo erróneo. |

- Los **ataques de defecto** son una forma metódica de aplicarla: el probador crea o adquiere una lista de posibles errores, defectos y fallos (a partir de la experiencia, de datos de defectos o del conocimiento común sobre por qué falla el software) y diseña pruebas que los expongan o provoquen.

### 4.4.2 Prueba exploratoria

- Las pruebas se diseñan, ejecutan y evalúan a la vez mientras el probador aprende sobre el objeto; sirve para conocerlo mejor, explorarlo en profundidad con pruebas concentradas y crear pruebas para áreas no probadas.
- **Enfoque basado en sesiones**: la exploración se hace en un marco temporal definido y la guía un contrato de prueba con los objetivos de prueba, que pueden tratarse como condiciones de alto nivel. Los elementos de cobertura se identifican y ejercitan durante la sesión; el probador puede documentar pasos y descubrimientos en hojas de sesión. Suele seguir una recapitulación en la que probador e implicados comentan los resultados.
- Útil con especificaciones escasas o inadecuadas, con fuerte presión de tiempo o como complemento de técnicas más formales.
- Es más eficaz si el probador tiene experiencia, conoce el dominio y domina competencias como el análisis, la curiosidad y la creatividad (ver sección 1.5.1 del [[Areas/Fundamentos de prueba/Cap. 1 - Fundamentos del proceso de prueba|capítulo 1]]).
- Puede incorporar otras técnicas, como la partición de equivalencia.

### 4.4.3 Prueba basada en lista de comprobación

- El probador diseña, implementa y ejecuta pruebas para cubrir las condiciones de una lista de comprobación, construida con la experiencia, el conocimiento de lo que importa al usuario o la comprensión de por qué y cómo falla el software.
- La lista no debe incluir elementos que se puedan comprobar automáticamente, elementos más propios de criterios de entrada o salida, ni elementos demasiado generales.
- Los elementos suelen formularse como preguntas, cada una comprobable por separado y de forma directa; pueden referirse a requisitos, propiedades de la interfaz gráfica, características de calidad u otras condiciones. Sirven para pruebas funcionales y no funcionales (por ejemplo, un conjunto de 10 heurísticas para pruebas de usabilidad).
- Con el tiempo algunas entradas pierden efectividad porque los desarrolladores aprenden a evitar esos errores, y conviene añadir otras por defectos graves recién encontrados: hay que actualizar la lista periódicamente según el análisis de defectos, sin dejar que crezca en exceso.
- Sin casos detallados, aporta directrices y cierta consistencia; si la lista es de alto nivel, habrá variabilidad entre ejecuciones, con más cobertura pero menos repetibilidad.

## 4.5 Enfoques de prueba basados en la colaboración

Las técnicas de 4.2, 4.3 y 4.4 buscan sobre todo detectar defectos; los enfoques basados en la colaboración se centran también en **evitarlos** mediante colaboración y comunicación.

### 4.5.1 Redacción colaborativa de historias de usuario

Una historia de usuario representa una prestación con valor para un usuario o comprador del sistema. Tiene tres aspectos críticos, las "3 C":

| C | Inglés | Qué es |
|---|---|---|
| Cuartilla (tarjeta) | Card | El medio que describe la historia, como una ficha o una entrada en un tablero electrónico. |
| Conversación | Conversation | Explica cómo se usará el software; puede ser documentada o verbal. |
| Confirmación | Confirmation | Los criterios de aceptación (4.5.2). |

La traducción usa "cuartilla" en lugar de "tarjeta" para conservar la mnemotecnia de las 3 C.

- Formato habitual: "Como [rol], quiero [objetivo], de modo que pueda [valor de negocio para el rol]", seguido de los criterios de aceptación.
- La autoría colaborativa usa técnicas como la tormenta de ideas y los mapas mentales, y logra una visión compartida desde tres perspectivas: negocio, desarrollo y prueba.
- Una buena historia cumple **INVEST**:

| Letra | Español | Inglés |
|---|---|---|
| I | Independiente | Independent |
| N | Negociable | Negotiable |
| V | Valiosa | Valuable |
| E | Estimable | Estimable |
| S | Pequeña | Small |
| T | Comprobable (capacidad de prueba) | Testable |

- Si un implicado no sabe cómo probar una historia, puede que no esté clara, que no refleje algo valioso para él o que simplemente necesite ayuda para probarla.

### 4.5.2 Criterios de aceptación

- Son las condiciones que una implementación de la historia debe cumplir para que los implicados la acepten; pueden verse como las condiciones de prueba que las pruebas deben ejercitar. Suelen surgir de la Conversación (4.5.1).
- Se usan para: definir el alcance de la historia, lograr consenso entre implicados, describir escenarios positivos y negativos, servir de base a la prueba de aceptación de usuario (4.5.3) y permitir una planificación y estimación precisas.

| Formato | Ejemplos |
|---|---|
| Orientado a escenarios | El formato Dado/Cuando/Entonces del desarrollo guiado por el comportamiento (ver sección 2.1.3 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]). |
| Orientado a reglas | Lista de verificación con viñetas o tabla de correspondencia entre entradas y salidas. |

La mayoría de criterios cabe en uno de los dos formatos, pero el equipo puede usar otro propio siempre que los criterios estén bien definidos y no sean ambiguos.

### 4.5.3 Desarrollo guiado por prueba de aceptación (DGPA)

Es un enfoque de probar primero (ver sección 2.1.3 del [[Areas/Fundamentos de prueba/Cap. 2 - Prueba en el ciclo de vida|capítulo 2]]): los casos se crean antes de implementar la historia, los escriben miembros del equipo con distintas perspectivas (clientes, desarrolladores, probadores) y pueden ejecutarse de forma manual o automatizada.

| Paso | Qué se hace |
|---|---|
| 1. Taller de especificación | El equipo analiza, debate y redacta la historia y, si faltan, sus criterios de aceptación; se resuelven incompletitudes, ambigüedades o defectos. |
| 2. Creación de los casos | El equipo en conjunto o el probador crea casos basados en los criterios de aceptación; son ejemplos de cómo funciona el software y pueden aplicarse las técnicas de 4.2, 4.3 y 4.4. |
| 3. Orden de cobertura | Primero casos positivos (comportamiento correcto sin excepciones ni errores, siguiendo el flujo esperado), después negativos y por último características no funcionales, como eficiencia de desempeño o usabilidad. |

- Ejemplos y pruebas son lo mismo, por lo que los términos se usan indistintamente.
- Los casos deben ser comprensibles para los implicados: frases en lenguaje natural con precondiciones (si las hay), entradas y postcondiciones.
- Deben cubrir todas las características de la historia sin ir más allá, y no debe haber dos casos que describan las mismas características; los criterios de aceptación pueden detallar aspectos descritos en la historia.
- Si se capturan en un formato compatible con un marco de automatización, los desarrolladores pueden automatizarlos escribiendo el código de apoyo mientras implementan la prestación: las pruebas de aceptación se convierten en **requisitos ejecutables**.
