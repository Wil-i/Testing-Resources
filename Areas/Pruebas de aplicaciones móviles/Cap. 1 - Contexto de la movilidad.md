---
tags: [capitulo]
area: "[[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]"
capitulo: 1
paginas: "18–28"
duracion: "175 min"
---

# 1. Contexto de la movilidad: factores de negocio y tecnológicos

> Parte de [[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]

**Términos clave:** [[Índice de términos#Análisis del riesgo|análisis del riesgo]], [[Índice de términos#Mitigación del riesgo|mitigación del riesgo]], [[Índice de términos#Prueba basada en el riesgo|prueba basada en el riesgo]], [[Índice de términos#Estrategia de prueba|estrategia de prueba]]

## Objetivos de aprendizaje
- **NBPAM-1.1.1 (K2)**: explicar cómo los datos analíticos móviles alimentan la estrategia y el plan de prueba.
- **OP-1.1.1 (H3)**: a partir de datos analíticos (geografía, plataforma, versión de SO, distribución de dispositivos), seleccionar y priorizar los dispositivos a probar.
- **NBPAM-1.2.1 (K2)**: diferenciar los modelos de negocio de las apps móviles.
- **NBPAM-1.3.1 (K1)**: recordar los tipos de dispositivos móviles.
- **NBPAM-1.4.1 (K2)**: diferenciar los tipos de aplicaciones móviles.
- **NBPAM-1.5.1 (K2)**: diferenciar los tipos generales de arquitectura de apps móviles.
- **NBPAM-1.6.1 (K3)**: aplicar las particularidades del mercado móvil al preparar una estrategia de prueba.
- **NBPAM-1.7.1 (K2)**: dar ejemplos de desafíos de la prueba de apps móviles.
- **OP-1.7.1 (H1)**: recopilar cuota de mercado de dispositivos o SO en una región, y datos de tamaño y densidad de pantalla; armar una lista de cinco dispositivos y calcular la cobertura de mercado esperada (combinable con OP-1.1.1).
- **NBPAM-1.8.1 (K2)**: describir cómo mitigar los riesgos específicos de las apps móviles.

## 1.1 Datos analíticos de móviles

- En el ecosistema móvil intervienen fabricantes, proveedores de plataforma y de SO, proveedores de datos de mercado y de herramientas, desarrolladores y probadores.
- Para aportar a la planificación y al análisis de la prueba, el probador debe conocer:
  - Implicaciones de negocio de la distribución de plataformas.
  - Descargas de la app por plataforma.
  - Cantidad y distribución de versiones del SO.
  - Distribución de tipos de dispositivo en el mercado, incluidas las variaciones geográficas.
  - Tamaños y resoluciones de pantalla, métodos de entrada y tipos de cámara.
- Fuentes: gratuitas o comerciales, por ejemplo StatCounter GlobalStats, los propios proveedores de SO y terceros.
- Uso principal: seleccionar una **cartera de dispositivos** (conjunto fijo de dispositivos) representativa del mercado objetivo y probar según la importancia de cada dispositivo.
- Los datos sobre prestaciones especiales permiten diseñar pruebas específicas (por ejemplo, un dispositivo con sensor de ritmo cardíaco requiere casos propios).

## 1.2 Modelos de negocio para aplicaciones móviles

El probador debe tener presente el modelo de monetización, porque condiciona el comportamiento esperado de la app. Las compras intra-aplicación pueden combinarse con varios modelos.

| Modelo | Cómo genera valor | Qué vigilar al probar |
|---|---|---|
| Semigratuito (freemium) | Uso gratuito; se paga por prestaciones adicionales. | Que la versión gratuita sea atractiva y que las funciones premium justifiquen el pago. |
| Basado en publicidad | Anuncios mostrados durante el uso; rinde más con sesiones largas. | Que los anuncios sean visibles sin tapar partes esenciales ni molestar al usuario. |
| Basado en transacciones | Cobro por transacción (tarifa fija o porcentaje). | Adecuado para pocos tipos de apps, típicamente financieras o empresariales (monederos móviles). |
| De pago (basado en tarifa) | El usuario paga por descargar e instalar. | Solo prospera con prestaciones o usabilidad excepcionales o sin competencia gratuita. |
| Gratuitas y empresariales | No cobran; la empresa monetiza sus servicios (bancos, comercio electrónico). | Las empresariales son de uso interno y actúan como interfaz de los servicios de la organización. |

## 1.3 Tipos de dispositivos móviles

| Tipo | Características |
|---|---|
| Teléfono básico | Llamadas y SMS, pocas apps y juegos integrados; no instala apps ni navega por Internet. |
| Teléfono de altas prestaciones (feature phone) | Soporte limitado de apps e instalación; navegador integrado; hardware extra como cámara. |
| Teléfono inteligente | Incluye sensores; el SO soporta instalación de apps, multimedia y navegación. |
| Tableta | Similar al teléfono inteligente pero más grande; pantalla mayor y a menudo más batería. |
| Dispositivos complementarios e IoT | Amplían funciones de un teléfono o tableta o dan acceso más cómodo a sus datos. |
| Vestibles (wearables) | Se llevan puestos; complementan a otros dispositivos o funcionan solos (relojes, bandas de actividad física). |

Cada tipo tiene prestaciones pensadas para necesidades concretas, lo que debe reflejarse en las pruebas.

## 1.4 Tipos de aplicaciones móviles

Hay tres grandes tipos; elegir uno es una decisión de negocio previa al desarrollo.

| Aspecto | Nativa | Basada en navegador (web móvil) | Híbrida |
|---|---|---|---|
| Construcción | SDK, herramientas y sensores propios de la plataforma. | Tecnologías web estándar ejecutadas en el navegador móvil. | Envoltura nativa con una vista web que ejecuta la app web. |
| Distribución | Tiendas del proveedor (descarga, instalación, actualización). | Acceso por URL; sin instalación. | Tiendas del proveedor. |
| Acceso al dispositivo | Completo. | Limitado a API y sensores disponibles en el navegador. | Completo. |
| Ventajas | Mejor rendimiento, aprovecha la plataforma y cumple sus expectativas. | Multiplataforma sencillo, menor coste, más fácil de mantener. | Desarrollo y actualización fáciles, habilidades similares a las web. |
| Desventajas | Mayor coste; muchas plataformas y dispositivos que instalar y probar. | Menos funciones; requiere Internet. | Rendimiento afectado por la envoltura; aspecto que puede desviarse de la plataforma. |
| Enfoque de prueba | Probar en todos los dispositivos soportados. | Sin prueba de instalabilidad, pero sí de compatibilidad con navegadores. | Combinar ambos enfoques. |

Formas de crear apps web móviles:
- **Sitios m(dot)**: versión móvil específica a la que se redirige (por ejemplo, de facebook.com a m.facebook.com).
- **Web responsiva**: el diseño se ajusta al factor de forma y al tamaño de la ventana gráfica (viewport).
- **Web adaptativa**: diseños distintos para tamaños predefinidos, con funciones a menudo ajustables.
- **Web progresiva**: accesos directos en la pantalla de inicio que parecen apps nativas y a veces funcionan sin conexión.

Otros puntos:
- Nativas e híbridas están instaladas y disponibles sin conexión; las web requieren Internet.
- Canales de distribución: preinstalación, Apple App Store, Google Play Store, tiendas empresariales (solo en la red corporativa) y mercados de terceros.
- Parámetros que cambian el enfoque de prueba: tipos de dispositivo a soportar, sensores y prestaciones usados, disponibilidad en distintas condiciones de red, e instalabilidad, compatibilidad, rendimiento (eficiencia de desempeño) y usabilidad.

## 1.5 Arquitectura de aplicaciones móviles

**Factores para elegir la arquitectura:** audiencia objetivo, tipo de app, soporte de plataformas móviles y no móviles, necesidades de conectividad y almacenamiento, y conexión con otros dispositivos (incluido IoT).

**Decisiones arquitectónicas:**
- **Lado cliente**
  - *Cliente ligero*: sin código de app personalizado en el dispositivo, uso mínimo del SO; suele usar el navegador como interfaz y JavaScript para la lógica cliente.
  - *Cliente pesado*: varias capas de código y uso de funciones del SO; normalmente apps nativas o híbridas.
- **Lado servidor**
  - *Una capa*: monolítica, todo en una máquina; menos escalable y más difícil de asegurar.
  - *Multicapa*: dos capas (servidor web y de base de datos separados) o tres capas (con servidor de aplicaciones). Mejoran separación de responsabilidades, flexibilidad, escalabilidad y seguridad, pero son más caras de desarrollar, gestionar y alojar.
- **Tipo de conexión**: Wi-Fi, datos móviles (2G, 3G, 4G, 5G), NFC, Bluetooth.
- **Modos de conectividad de la app**
  - *Nunca conectada*: funciona sin red (por ejemplo, una calculadora).
  - *Siempre conectada*: requiere red permanente; incluye todas las web móviles, aunque algunas funcionan de forma limitada con conexión parcial.
  - *Parcialmente conectada*: necesita red para ciertas tareas (transferir datos), pero opera largos periodos sin ella.
- **Sincronización de datos**
  - *Continua*: los datos se transfieren en cuanto se envían.
  - *Almacenamiento y retransmisión (store-and-forward)*: se guardan localmente y se envían cuando hay conectividad.
- **Transferencia de datos**
  - *Síncrona*: quien llama espera a que termine la función llamada.
  - *Asíncrona*: el servidor responde de inmediato, procesa en segundo plano y devuelve la llamada al cliente al terminar. Da más control al usuario, pero el mecanismo de establecimiento de comunicación (handshake) complica la gestión de la disponibilidad del cliente o de la red.

## 1.6 Estrategia de prueba para aplicaciones móviles

La estrategia debe considerar todos los parámetros del capítulo, los riesgos y los desafíos de 1.7. Riesgos típicos si falta información:
- Sin datos de proliferación de dispositivos por región, no se puede elegir de forma sostenible en qué dispositivos probar.
- Sin conocer el modelo de negocio, no se puede validar que la app se comporte según ese modelo.

Riesgos y desafíos adicionales a incorporar:
- Variedad de dispositivos, algunos con defectos propios.
- Disponibilidad de dispositivos en la empresa o en laboratorios externos.
- Aparición de tecnologías, dispositivos o plataformas nuevas durante el ciclo de vida.
- Instalación y actualización por varios canales, conservando datos y preferencias.
- Problemas de la plataforma que afectan a la app.
- Cobertura de red en un contexto global y prueba con redes de distintos operadores.
- Uso de emuladores, simuladores o dispositivos reales según nivel y tipo de prueba.

Cómo responde la estrategia:
- **Progresión de entornos**: emuladores o simuladores en etapas tempranas y dispositivos reales después (no todas las pruebas son viables en virtual; ver apartado 4.3 del [[Areas/Pruebas de aplicaciones móviles/Cap. 4 - Plataformas, herramientas y entornos|capítulo 4]]).
- **Alcance frente a la diversidad de dispositivos:**

| Enfoque | Alcance | Comentario |
|---|---|---|
| Plataforma única | Un tipo de dispositivo, una versión de SO, un operador y un tipo de red. | Mínimo coste, mínima cobertura. |
| Multiplataforma | Selección representativa de dispositivos y SO de la mayoría de los clientes del mercado objetivo, según tráfico o analítica. | Equilibrio habitual. |
| Máxima cobertura | Todas las versiones de SO, dispositivos, fabricantes, operadores y redes. | Prueba prácticamente exhaustiva; rara vez viable económicamente. |

- **Recursos externos ante la falta de dispositivos, redes o condiciones reales:**
  - Acceso remoto a dispositivos (dispositivos ajenos accesibles por la web).
  - Prueba multitudinaria (crowd testing): voluntarios con sus propios dispositivos.
  - Redes personales: amigos y colegas.
  - Caza de defectos (bug bash): prueba lúdica con voluntarios internos o del público.
- Además de los niveles del CTFL, se consideran los tipos comunes de prueba móvil (3.1) y los niveles adicionales (3.2), ambos tratados en el [[Areas/Pruebas de aplicaciones móviles/Cap. 3 - Tipos de prueba comunes y proceso|capítulo 3]].

## 1.7 Desafíos de la prueba de aplicaciones móviles

**Desafíos típicos**, poco frecuentes o menos críticos en escritorio o servidor:
- Diversidad de plataformas y fragmentación de dispositivos (SO, versiones, tamaño y calidad de pantalla).
- Diferencias de hardware: sensores variados y dificultad para simular CPU y RAM limitadas.
- Variedad de herramientas de desarrollo por plataforma.
- Diferentes diseños de interfaz y expectativas de UX por plataforma.
- Diversidad de redes, operadores, canales de distribución, usuarios y grupos de usuarios.
- Dispositivos con recursos insuficientes.
- Distintos tipos de app con distintos métodos de conexión.
- Alta visibilidad de los fallos: los usuarios publican reseñas negativas en las tiendas.
- Ciclos de aprobación adicionales en Google Play o Apple App Store.
- Dispositivos recién lanzados no disponibles, lo que obliga a usar emuladores o simuladores.

**Impacto:** muchas combinaciones que probar y muchos dispositivos (más coste); necesidad de compatibilidad con versiones anteriores; nuevas prestaciones en cada versión de SO; directrices distintas por plataforma; CPU, memoria y almacenamiento limitados; ancho de banda variable y fluctuante; velocidades de subida y bajada que dependen del plan de datos.

**Ejemplos:**
- Cada nuevo sensor en el hardware puede exigir pruebas adicionales de compatibilidad con versiones anteriores.
- Las estrategias de caché y de precarga (prefetching) mitigan problemas de red, pero muchas conexiones abiertas penalizan el rendimiento del servidor, ya que la mayoría de apps mantiene al usuario conectado.

## 1.8 Riesgos en la prueba de aplicaciones móviles

Los desafíos, solos o combinados, generan riesgos. El probador contribuye al análisis de riesgo de producto con los métodos del CTFL (capítulo 5.5), más estas mitigaciones específicas:

| Riesgo | Mitigación posible |
|---|---|
| Fragmentación del mercado | Elegir una cartera adecuada, por ejemplo los dispositivos más usados. |
| Coste de soportar varias plataformas | Analizar qué plataformas se usan más y descartar las que salieron del alcance. |
| Nuevas tecnologías, plataformas y dispositivos | Usar versiones de preproducción. |
| Falta de dispositivos para ejecutar la prueba | Servicios de acceso remoto a dispositivos o prueba multitudinaria. |
| Patrones de uso en movimiento | Enfoques adecuados como la prueba de campo. |
