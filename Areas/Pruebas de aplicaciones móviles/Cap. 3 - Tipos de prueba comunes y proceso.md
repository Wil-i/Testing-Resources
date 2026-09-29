---
tags: [capitulo]
area: "[[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]"
capitulo: 3
paginas: "39–50"
duracion: "200 min"
---

# 3. Tipos de prueba comunes y proceso de prueba para aplicaciones móviles

> Parte de [[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]

**Términos clave:** [[Índice de términos#Fin anómalo|fin anómalo]], [[Índice de términos#Accesibilidad|accesibilidad]], [[Índice de términos#Inyección de código|inyección de código]], [[Índice de términos#Prueba exploratoria|prueba exploratoria]], [[Índice de términos#Prueba de campo|prueba de campo]], [[Índice de términos#Heurístico|heurístico]], [[Índice de términos#Instalabilidad|instalabilidad]], [[Índice de términos#Eficiencia de desempeño|eficiencia de desempeño]], [[Índice de términos#Prueba de rendimiento|prueba de rendimiento]], [[Índice de términos#Prueba post-entrega|prueba post-entrega]], [[Índice de términos#Prueba de seguridad|prueba de seguridad]], [[Índice de términos#Gestión de prueba basada en sesión|gestión de prueba basada en sesión]], [[Índice de términos#Prueba de estrés|prueba de estrés]], [[Índice de términos#Nivel de prueba|nivel de prueba]], [[Índice de términos#Proceso de prueba|proceso de prueba]], [[Índice de términos#Pirámide de prueba|pirámide de prueba]], [[Índice de términos#Tour|tour]], [[Índice de términos#Laboratorio de usabilidad|laboratorio de usabilidad]], [[Índice de términos#Prueba de usabilidad|prueba de usabilidad]]

## Objetivos de aprendizaje
- **NBPAM-3.1.1 (K3)**: preparar pruebas de instalabilidad.
- **NBPAM-3.1.2 (K3)**: preparar pruebas de estrés.
- **NBPAM-3.1.3 (K2)**: dar ejemplos de problemas de seguridad en apps móviles.
- **NBPAM-3.1.4 (K1)**: recordar consideraciones de tiempo y de uso de recursos.
- **NBPAM-3.1.5 (K3)**: preparar pruebas de usabilidad.
- **OP-3.1.5 (H2)**: elegir un tour, una mnemotecnia o una heurística para probar la usabilidad con gestión basada en sesiones.
- **NBPAM-3.1.6 (K1)**: reconocer el tipo de prueba necesario para bases de datos móviles.
- **NBPAM-3.1.7 (K2)**: resumir la prueba de internacionalización (globalización) y localización.
- **NBPAM-3.1.8 (K2)**: resumir la necesidad de la prueba de accesibilidad.
- **NBPAM-3.2.1 (K2)**: describir los niveles adicionales, como la prueba de campo, y sus actividades asociadas.
- **NBPAM-3.2.2 (K2)**: describir las pruebas necesarias para la aprobación de la tienda de aplicaciones.
- **NBPAM-3.3.1 (K1)**: recordar SBTM, personas y mnemotecnias en la prueba exploratoria móvil.
- **OP-3.3.1 (H2)**: elegir una mnemotecnia móvil (o parte) y probar con SBTM.
- **NBPAM-3.3.2 (K2)**: describir itinerarios (tours) y heurísticas como técnicas exploratorias.
- **OP-3.3.2 (H2)**: elegir una heurística móvil para probar una app.
- **NBPAM-3.3.3 (K3)**: usar un tour móvil específico (como el de prestaciones) para probar una app.
- **OP-3.3.3 (H2)**: elegir un tour móvil para probar una app (OP-3.1.5, OP-3.3.1, OP-3.3.2 y OP-3.3.3 pueden hacerse juntos).
- **NBPAM-3.4.1 (K2)**: adaptar el proceso de prueba del CTFL a la prueba móvil.
- **NBPAM-3.4.2 (K2)**: describir enfoques de prueba específicos por nivel.

## 3.1 Tipos de prueba comunes para aplicaciones móviles

### 3.1.1 Prueba de instalabilidad

- Cubre instalación, actualización y desinstalación por distintas vías:
  - Tiendas de aplicaciones (Google Play Store, Apple App Store); las apps empresariales, mediante enlace o servicios de distribución como HockeyApp o App Center.
  - Carga lateral (sideloading): copiar el archivo al dispositivo e instalarlo desde ahí.
  - Aplicaciones de escritorio (Apple iTunes, Android App Installer) con cable; suelen permitir también desinstalar.
- Medios: instalación aérea (Wi-Fi o datos móviles) o cable de datos.
- Condiciones de prueba:
  - Instalar, desinstalar y actualizar en memoria interna y externa (si se admite).
  - Reinstalar habiendo elegido, o no, "conservar datos de la aplicación" al desinstalar.
  - Cancelar o interrumpir la instalación o desinstalación (apagando el dispositivo o cortando Internet) y reanudarla después.
  - Permisos: comportamiento si el usuario niega el permiso (por ejemplo, a la libreta de direcciones) y si se le informa.
  - Actualizar sin pérdida de datos.
- Algunas apps exigen dispositivos liberados (jailbreak, iOS) o con control privilegiado (rooting, Android). La mayoría de proveedores no lo admite por posibles consecuencias legales; si la app no lo requiere, puede no ser necesario probarlo.

### 3.1.2 Prueba de estrés

- Mide la eficiencia de desempeño más allá de la carga normal, centrada en el dispositivo; el estrés del back-end se trata en el programa de Prueba de Rendimiento.
- Condiciones: CPU alta, memoria insuficiente, poco espacio en disco, carga de batería, fallos, ancho de banda insuficiente y muchísimas interacciones del usuario (quizá con simulación de red real).
- Herramientas: Monkey, herramienta de línea de comandos que se ejecuta desde el intérprete de comandos de ADB; o de forma manual con archivos grandes o apps que consuman mucha memoria o CPU.

### 3.1.3 Prueba de seguridad

- Tema amplio, con programa propio (CTAL Security Testing).
- Riesgos principales: acceso a datos sensibles del dispositivo, transferencia sin cifrar y almacenamiento inseguro.
- Condiciones: entradas para inyección de código y desbordamiento; cifrado de datos en tránsito y almacenados localmente; borrado de datos temporales tras el uso o tras un fin anómalo.
- Revisar además el OWASP Mobile Top 10.

### 3.1.4 Prueba de rendimiento

- Si la app no responde con rapidez (por ejemplo, en 3 segundos o menos), el usuario puede desinstalarla por otra; tiempo y consumo de recursos son factores de éxito.
- Se prueba la eficiencia en el propio dispositivo y en la interacción con el back-end y otros dispositivos; la prueba de rendimiento del sistema completo no es específica de móviles (programa de Prueba de Rendimiento).
- Cronometrar los flujos principales (en banca: iniciar sesión, cambiar dirección, transferencia con PIN y TAN) y compararlos con apps similares.
- Considerar también el rendimiento **percibido**: la UX influye en cuánto está dispuesto a esperar el usuario.

### 3.1.5 Prueba de usabilidad

- Muchos usuarios desinstalan una app a los pocos minutos por mala usabilidad o rendimiento.
- La UX debe respetar el aspecto y la sensación de la plataforma; el probador debe conocerlos.
- Herramientas del probador: heurísticas, tours, el concepto de personas y, si hace falta, un laboratorio de usabilidad.
- Lo que se detecta suele ser un **hallazgo**, no un defecto; el probador debe saber explicarlo al equipo y al propietario del producto.
- Una app usable es autoexplicativa e intuitiva, tolera errores del usuario, es consistente en redacción y comportamiento, cumple las guías de diseño de la plataforma y muestra la información necesaria en cualquier tamaño y tipo de pantalla. Ampliar con el programa de Prueba de Usabilidad.

### 3.1.6 Prueba de base de datos

- Aplica a datos locales en archivos planos o bases de datos.
- Condiciones: sincronización, conflictos de carga, restricciones de datos, funciones ABML/CRUD (alta, baja, modificación, lectura), búsqueda, integración de datos del dispositivo (contactos) o de terceros (imágenes, vídeos, mensajes) y rendimiento del almacenamiento local.

### 3.1.7 Prueba de globalización y localización

- **Internacionalización o globalización**: distintas ubicaciones, formatos de fecha, número y moneda, y sustitución de cadenas reales por pseudocadenas.
- **Localización**: cadenas, imágenes y flujos adaptados a una región. Las palabras en ruso o alemán pueden ser mucho más largas y romper pantallas pequeñas.
- Punto crítico: el formato de fecha (AÑO-MES-DÍA frente a DÍA-MES-AÑO).

### 3.1.8 Prueba de accesibilidad

- Evalúa qué tan fácil es el uso para personas con discapacidad; se prueba la app con cada ajuste de accesibilidad del dispositivo.
- Seguir las guías de los proveedores (Google, Apple), recoger la opinión de usuarios que necesitan accesibilidad y, para la web móvil, las guías del W3C.

## 3.2 Niveles de prueba adicionales aplicables a aplicaciones móviles

Se suman a los niveles del CTFL (de componente a aceptación).

### 3.2.1 Prueba de campo

- Verifica la app en el escenario de uso real: varias redes y tecnologías (Wi-Fi, datos móviles).
- Incluye conmutar torres, redes, Wi-Fi y datos móviles durante el uso, con distintas velocidades de descarga e intensidades de señal, y el tratamiento de puntos ciegos.
- Requiere planificación cuidadosa: dispositivos adecuados, Wi-Fi, planes de datos de varios operadores, medios de transporte, rutas y horarios.
- También cubre la usabilidad en contexto y factores del entorno como la temperatura.

### 3.2.2 Aprobación de la tienda de aplicaciones y prueba posterior a la entrega

- Antes del envío se ejecutan (y deben superarse) pruebas con listas de comprobación basadas en las directrices del SO, de diseño de interfaz y de uso de librerías y API de las tiendas; si es una actualización, también las pruebas de actualización.
- La aprobación puede tardar, y un rechazo obliga a enviar una nueva versión, por lo que hay que considerarlo en la planificación.
- **Prueba post-entrega**: descargar e instalar la app desde la tienda ya publicada.

## 3.3 Técnicas de prueba basadas en la experiencia

### 3.3.1 Personas y mnemotecnias

- **Persona**: personaje ficticio que representa a clientes reales, con motivaciones, expectativas, problemas, hábitos y objetivos (nombre, género, edad, ingresos, formación, ubicación). En móvil puede incluir qué otras apps usa, cuántas veces por hora mira el teléfono y qué otros dispositivos tiene. Sirve para imitar el comportamiento real del usuario.
- **Mnemotecnia**: ayuda de memoria en la que cada letra representa una técnica, método o foco de prueba.

Mnemotecnia **SFDPOT** (escrita SFiDPOT en el programa):

| Letra | Aspecto | Qué revisar |
|---|---|---|
| S | Structure (estructura) | Elementos de la interfaz y de la app, su jerarquía de orden y de llamada. |
| F | Function (función) | Las prestaciones requeridas existen y funcionan según los requisitos. |
| i | Input (entrada) | Todas las entradas (teclado, sensores, cámara) están disponibles y se procesan bien. |
| D | Data (datos) | Almacenar (también en tarjeta SD), modificar, añadir y borrar según los requisitos. |
| P | Platform (plataforma) | Funciones del SO disponibles según la configuración, incluida la tienda de descarga. |
| O | Operations (operaciones) | Actividades normales del usuario, como pasar entre redes móviles y Wi-Fi. |
| T | Time (tiempo) | Zonas horarias, horas y fechas. |

Mnemotecnia y heurística específica de móvil **I SLICED UP FUN**: Inputs (entradas), Store (tienda), Location (localización), Interactions and interruptions (interacciones e interrupciones), Communication (comunicación), Ergonomics (ergonomía), Data (datos), Usability (usabilidad), Platform (plataforma), Function (función), User scenarios (escenarios de usuario), Network (red).

### 3.3.2 Heurísticas

- Enfoque de "regla empírica" práctico: no garantiza el óptimo, pero basta para los objetivos inmediatos.
- La mayoría de las mnemotecnias sirven como heurísticas, pero no toda heurística es una mnemotecnia.

### 3.3.3 Tours (itinerarios)

- Exploran la app desde un punto de vista concreto; ayudan a entender su funcionamiento, modelar flujos y son eficaces en la prueba de campo.
- Analogías del tour **Landmark** (el turista que visita lugares emblemáticos):

| Lugar del tour | Analogía en la prueba móvil |
|---|---|
| Casco histórico | Código heredado. |
| Distrito financiero | Lógica de negocio. |
| Hora pico | Arranque y cierre de la app. |
| Barrio turístico | Partes que usan los principiantes. |
| Barrio de hoteles | Partes activas solo en reposo. |

- Combinar tours con SBTM, heurísticas y mnemotecnias mejora la eficacia.
- Tours útiles para apps:

| Tour | Aspecto cubierto |
|---|---|
| Supermodel (supermodelo) | Aspecto, sensación y usabilidad. |
| Landmark (lugar emblemático) | Prestaciones más importantes. |
| Sabotage (sabotaje) | Robustez. |
| Feature (prestación) | Prestaciones nuevas. |
| Scenario (escenario) | Flujos completos combinados con historias de usuario. |
| Connectivity (conectividad) | Conexiones usadas (Wi-Fi, GSM). |
| Location (localización) | Idioma, fechas y números correctos. |
| Light (luz) | Visibilidad en oscuridad, exteriores, luz roja. |
| Low battery (batería baja) | Pérdida de datos por carga baja. |

- Otros tours citados de Kohl: Gesture (usar todos los gestos posibles), Orientation (cambiar orientación), Change your mind (volver atrás), Motion (distintos movimientos), Location (desplazarse), Connectivity (cambiar tipo de conexión o ubicación), Comparison (comparar con otros dispositivos), Consistency (consistencia de pantallas e interfaz gráfica).

### 3.3.4 Gestión de prueba basada en sesiones (SBTM)

- Gestiona la prueba exploratoria en bloques de tiempo definidos. Cada sesión tiene tres tareas: preparación; diseño y ejecución; investigación y reporte de problemas.
- Usa una hoja de sesión con un contrato (charter) que fija los objetivos y donde se documenta lo ejecutado.
- La prueba exploratoria, basada en la experiencia (CTFL), es muy eficaz en móviles.

## 3.4 Proceso y enfoques de la prueba móvil

### 3.4.1 Proceso de prueba

Las actividades del proceso ISTQB aplican, con estos añadidos móviles:

| Grupo de actividades | Aspectos móviles a considerar | Referencia |
|---|---|---|
| Planificación | Combinaciones de dispositivos; emuladores y simuladores en el entorno; desafíos propios; tipos de prueba específicos. | 4.3, 1.7, 3.2 |
| Análisis y diseño | Aprobación de tiendas; prueba de campo; compatibilidad de dispositivos; tipo de laboratorio; tipos de prueba específicos. | 3.2.2, 3.2.1, 3.2 |
| Implementación y ejecución | Prueba de campo; descarga e instalabilidad post-entrega; técnicas basadas en la experiencia; pruebas basadas en directrices de plataforma, interfaz y tiendas. | 3.2.1, 3.1.1, CTFL |

Los apartados 4.3 y 1.7 citados en la tabla corresponden al [[Areas/Pruebas de aplicaciones móviles/Cap. 4 - Plataformas, herramientas y entornos|capítulo 4]] y al [[Areas/Pruebas de aplicaciones móviles/Cap. 1 - Contexto de la movilidad|capítulo 1]].

Las pruebas basadas en directrices las ejecuta normalmente el proveedor de la plataforma en su aprobación, pero conviene que el proveedor de la app las pase antes para evitar rechazos.

### 3.4.2 Enfoques de prueba

- Desarrolladores y probadores comparten actividades.
- La profundidad por nivel (componente, integración, sistema, campo, aprobación de tienda, post-entrega, aceptación de usuario) depende de la arquitectura, la complejidad y el público.
- Las plataformas ofrecen herramientas por nivel: emuladores y simuladores en la prueba de componentes (para aprovechar el marco y las API de instrumentación) y en la de sistema cuando faltan dispositivos reales (funcionalidad, parte de la usabilidad e interfaz).
- Una implementación temprana ayuda a configurar bien los dispositivos y a cumplir a tiempo los prerrequisitos de ejecución.
- Importan las pruebas unitarias, de integración y manuales (sobre todo en campo). En móviles es habitual **invertir la pirámide de prueba**: puede haber muchas pruebas manuales.
