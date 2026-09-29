---
tags: [capitulo]
area: "[[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]"
capitulo: 2
paginas: "29–38"
duracion: "265 min"
---

# 2. Tipos de prueba para aplicaciones móviles

> Parte de [[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]

**Términos clave:** [[Índice de términos#Coexistencia|coexistencia]], [[Índice de términos#Compatibilidad|compatibilidad]], [[Índice de términos#Conectividad|conectividad]], [[Índice de términos#Compatibilidad multinavegador|compatibilidad multinavegador]], [[Índice de términos#Interoperabilidad|interoperabilidad]], [[Índice de términos#Sistema sujeto a prueba|sistema sujeto a prueba]], [[Índice de términos#Tipo de prueba|tipo de prueba]], [[Índice de términos#Usabilidad|usabilidad]]

## Objetivos de aprendizaje
- **NBPAM-2.1.1 (K2)**: describir las prestaciones y el hardware del dispositivo que deben considerarse en la prueba.
- **OP-2.1.1 (H1)**: probar la app usando varias funciones del dispositivo mientras el SSP está en uso.
- **NBPAM-2.1.2 (K3)**: preparar pruebas de compatibilidad con tamaños de pantalla, proporción de aspecto y densidad.
- **OP-2.1.2 (H3)**: probar en varios dispositivos (virtuales o físicos) el efecto de resolución y tamaño en la interfaz.
- **NBPAM-2.1.3 (K2)**: describir cómo la prueba evidencia los efectos del sobrecalentamiento en el SSP.
- **NBPAM-2.1.4 (K1)**: recordar tipos de prueba para los sensores de entrada.
- **NBPAM-2.1.5 (K1)**: recordar pruebas para los distintos métodos de entrada.
- **OP-2.1.5 (H0)**: probar entradas con varios teclados instalados, gestos y, opcionalmente, cámara.
- **NBPAM-2.1.6 (K2)**: describir cómo el cambio de orientación revela problemas de interfaz.
- **OP-2.1.6 (H3)**: probar el efecto del cambio de orientación en funcionalidad, retención de datos e interfaz.
- **NBPAM-2.1.7 (K3)**: preparar pruebas con interrupciones típicas del dispositivo.
- **OP-2.1.7 (H3)**: probar la app con diversas interrupciones durante su uso.
- **NBPAM-2.1.8 (K3)**: preparar pruebas de cambio de permisos de acceso a prestaciones del dispositivo.
- **OP-2.1.8 (H3)**: conceder y denegar permisos (en la instalación o después) y observar el comportamiento.
- **NBPAM-2.1.9 (K3)**: preparar pruebas del impacto de la app en el consumo de energía y del estado de carga en la app (el PDF lo rotula por error como 2.1.8).
- **OP-2.1.9 (H3)**: probar con distintos niveles de batería, obtener datos de consumo y medir el comportamiento con batería baja o agotada.
- **NBPAM-2.2.1 (K3)**: preparar pruebas del tratamiento de notificaciones.
- **OP-2.2.1 (H2)**: probar notificaciones con la app en primer y segundo plano, y el efecto de cambiar su configuración.
- **NBPAM-2.2.2 (K2)**: describir cómo verificar los enlaces de acceso rápido.
- **OP-2.2.2 (H3)**: probar la funcionalidad de acceso rápido o directo.
- **NBPAM-2.2.3 (K3)**: preparar pruebas del impacto de las preferencias de usuario del SO.
- **OP-2.2.3 (H3)**: cambiar preferencias del SO con la app en ejecución.
- **NBPAM-2.2.4 (K2)**: diferenciar las pruebas necesarias para apps nativas, web e híbridas.
- **OP-2.2.4 (H0, opcional)**: identificar pruebas según el tipo de app.
- **NBPAM-2.2.5 (K1)**: recordar pruebas para apps en varias plataformas o versiones de SO.
- **NBPAM-2.2.6 (K1)**: recordar pruebas de coexistencia e interoperabilidad con otras apps.
- **NBPAM-2.3.1 (K2)**: resumir la prueba de conectividad (redes, Bluetooth, modo avión).
- **OP-2.3.1 (H0, opcional)**: probar una transferencia de datos mientras el teléfono conmuta entre Wi-Fi y datos móviles según la señal.

## 2.1 Prueba de la compatibilidad con el hardware del dispositivo

### 2.1.1 Prestaciones del dispositivo

- La diversidad obliga a priorizar dispositivos con los datos de mercado (apartado 1.1 del [[Areas/Pruebas de aplicaciones móviles/Cap. 1 - Contexto de la movilidad|capítulo 1]]); la cartera es un compromiso entre cobertura de mercado, coste y riesgo.
- Variables a cubrir: métodos de apagado, formas de navegar, teclados físicos y de software, y hardware como radio, USB, Bluetooth, cámaras, altavoces, micrófono y auriculares con micrófono. Ninguna debe interferir con la app.
- Las características varían incluso entre modelos del mismo fabricante y cambian con el tiempo (por ejemplo, el lector de huellas pasó de no existir a ser habitual en gama media y alta).
- No basta con probar que la función esperada funciona: la app debe seguir funcionando si la función **falta** (una app que usa cámara frontal y trasera no debe fallar con varias cámaras, una sola o ninguna).

### 2.1.2 Diferentes pantallas

- Variables: tamaño de pantalla y de visor (viewport), relación de aspecto, resolución en ppi y dpi. Se priorizan las combinaciones más comunes del mercado objetivo.
- Verificar que la app escala los elementos según densidad y tamaño, que no se solapan, que no hay problemas de usabilidad o táctiles y que las imágenes no se encogen de forma problemática por un cociente dpi/ppi alto.

### 2.1.3 Temperatura del dispositivo

- Causas de sobrecalentamiento: carga de batería, carga de trabajo intensa, apps en segundo plano, uso continuo de datos móviles, Wi-Fi o GPS.
- Reacciones del dispositivo: baja la frecuencia de CPU, libera memoria o apaga partes del sistema, lo que puede afectar a la app.
- Diseñar pruebas que consuman mucha energía durante un periodo largo e ininterrumpido; el SSP no debe comportarse de forma inesperada.

### 2.1.4 Sensores de entrada

- Sensores: GPS, acelerómetro, giroscopio, magnetómetro de 3 ejes, presión, temperatura, humedad, ritmo cardíaco, luz y entradas sin contacto.
- Verificar:
  - Funcionamiento con cada sensor disponible, incluidos distintos movimientos (circular, de vaivén como al caminar).
  - Respuesta correcta a distintas condiciones de iluminación.
  - Entrada y salida de sonido con botones de volumen físicos y de software, micrófonos, altavoces con cable e inalámbricos y distinto ruido ambiente.
  - Exactitud de la localización con GPS activado y desactivado, con distinta calidad de señal y con métodos alternativos (Wi-Fi, torres de telefonía, introducción manual).

### 2.1.5 Métodos de entrada

- Compatibilidad con los teclados de software de los principales fabricantes y los más difundidos.
- El teclado aparece por defecto con el diseño y las teclas adecuadas al campo.
- Gestos: pulsación o contacto, doble contacto, contacto múltiple, deslizar, pulsar, doble pulsación, arrastrar, pellizcar para abrir o cerrar. Cada pantalla responde a los gestos que soporta e ignora los demás.
- Cámara: capturar fotos y vídeo, escanear códigos de barras, QR y documentos, medir distancias; se activa la cámara correcta por defecto (por ejemplo, la frontal en videoconferencia); probar con y sin uso de cámara, y con una sola cámara, sobre todo si falta la que usa la app.

### 2.1.6 Cambios de orientación de la pantalla

- Verificar usabilidad y funcionalidad en vertical y horizontal, que la app conserva su estado, que los campos de entrada retienen lo capturado y que los de salida mantienen los datos durante la sesión.
- No basta con un solo giro: los problemas de renderizado o de estado pueden aparecer solo tras varios cambios seguidos. Probar múltiples rotaciones en distintos estados de la interfaz, con y sin datos, sin pérdida ni alteración.

### 2.1.7 Interrupciones características

- Del dispositivo: llamadas de voz, mensajes, cargador conectado, memoria baja, otras notificaciones. Del usuario: cambiar de app o poner el dispositivo en espera.
- Verificar que la app las trata sin efectos negativos y preserva estado, datos y sesión.
- Modo "no molestar": probar su uso y también su desactivación tras un periodo largo, cuando llegan muchas notificaciones a la vez.
- Ejemplo: contestar una llamada durante el uso y volver exactamente al estado previo.

### 2.1.8 Permisos de acceso a las prestaciones del dispositivo

- Las apps piden acceso a carpetas (contactos, imágenes) y sensores (cámara, micrófono); negar o cambiar el permiso afecta al comportamiento.
- Verificar que la app funciona con permisos reducidos, los solicita al usuario y no falla sin explicación; que solo pide permisos relevantes para su función; que responde bien si se retira o rechaza un permiso en la instalación; y que cada solicitud es correcta y justificada.
- El probador debe saber para qué se necesita cada permiso. Diseñar casos que nieguen permisos en la instalación y los concedan después.

### 2.1.9 Consumo de energía y estado de carga

- Verificar el estado de la batería y los defectos de descarga, la integridad de datos con batería baja o agotada, y el consumo en uso intensivo, en uso ligero y en segundo plano.
- Requieren planificación: periodos largos sin interrupción, a veces con el dispositivo desatendido y la app en primer o segundo plano. Se usan analizadores de registros para extraer patrones de descarga.

## 2.2 Prueba de las interacciones de la aplicación con el software del dispositivo

### 2.2.1 Notificaciones

- El SO puede retrasar u omitir notificaciones para ahorrar energía.
- Condiciones de prueba: tratamiento correcto en primer y segundo plano, sobre todo con batería baja; si la notificación permite interactuar sin abrir la app (por ejemplo, responder), esa interacción debe verse luego en la app; si contiene un enlace profundo, debe abrir la página correspondiente y no la de inicio.

### 2.2.2 Enlaces de acceso rápido

- Accesos directos de apps en Android y Force Touch o 3D Touch en iOS ejecutan un subconjunto de funciones desde la pantalla de inicio.
- Condiciones: comportamiento correcto en versiones de SO que tienen o no esa prestación, y que las acciones realizadas desde el acceso rápido se reflejen al abrir la app.

### 2.2.3 Preferencias de usuario del sistema operativo

- Toda preferencia del SO debe respetarse (por ejemplo, con el dispositivo en silencio la app no debe sonar).
- Preferencias a variar: sonido, brillo, red, ahorro de energía, fecha y hora, zona horaria, idioma, tipo de acceso y notificaciones.

### 2.2.4 Diferentes tipos de aplicaciones

Las pruebas dependen del tipo de aplicación descrito en el apartado 1.4 del [[Areas/Pruebas de aplicaciones móviles/Cap. 1 - Contexto de la movilidad|capítulo 1]].

| Tipo | Pruebas específicas |
|---|---|
| Nativa | Compatibilidad con el dispositivo; uso de sus prestaciones. |
| Híbrida | Interacción con prestaciones nativas; rendimiento afectado por la capa de abstracción; aspecto y sensación frente a las nativas. |
| Web | Compatibilidad multinavegador; funcionamiento con distintos motores JavaScript; uso de funciones del SO (selector de fecha, teclado adecuado); aspecto y sensación frente a las nativas. |

### 2.2.5 Interoperabilidad con varias plataformas y versiones de SO

- Cada SO tiene limitaciones propias; la app debe funcionar y respetar el aspecto de cada plataforma.
- Condiciones: tratamiento de interrupciones, notificaciones y optimizaciones de energía; funcionamiento correcto si se comparte código o se usa un marco multiplataforma (si no se comparte código, equivale a probar dos apps distintas); compatibilidad con versiones anteriores; prestaciones nuevas o modificadas (por ejemplo, el modo Doze de Android obligó a probar en versiones con y sin ese marco).

### 2.2.6 Interoperabilidad y coexistencia con otras aplicaciones

- Las apps interactúan entre sí (por ejemplo, contactos y correo).
- Condiciones: transferencia de datos correcta entre el SSP y la otra app, sin corromper los datos del usuario en esta; y detección de comportamientos en conflicto (una app apaga el GPS para ahorrar energía y otra lo enciende sola).
- No es realista probar la coexistencia con todas las apps del mercado; se prioriza por riesgo.

## 2.3 Prueba de diversos métodos de conectividad

- Métodos: redes móviles 2G a 5G, Wi-Fi y otras conexiones inalámbricas como NFC o Bluetooth (ver apartado 1.5 del [[Areas/Pruebas de aplicaciones móviles/Cap. 1 - Contexto de la movilidad|capítulo 1]]).
- Alternativas para probar:

| Alternativa | Valoración |
|---|---|
| Emuladores o simuladores (y algunos servicios de acceso remoto) que simulan redes | Útiles pero de valor limitado. |
| Red móvil propia con modificación del ancho de banda | Muy costosa. |
| Prueba de campo | Más rentable, pero difícil de reproducir. |

- En la vida real el usuario cambia de Wi-Fi a datos móviles (al salir de casa), entre redes, versiones y células GSM, atraviesa puntos muertos sin cobertura o se desconecta a propósito con el modo avión.
- Condiciones de prueba: funcionamiento correcto en cada modo; conmutación sin comportamientos inesperados ni pérdida de datos; mensajes claros al usuario cuando la funcionalidad se limita por red escasa, nula o de bajo ancho de banda, indicando la limitación y su causa.
