---
tags: [capitulo]
area: "[[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]"
capitulo: 4
paginas: "51–54"
duracion: "80 min"
---

# 4. Plataformas, herramientas y entornos de aplicaciones móviles

> Parte de [[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]

**Términos clave:** [[Índice de términos#Emulador|emulador]], [[Índice de términos#Prueba de campo|prueba de campo]], [[Índice de términos#Prueba basada en la proximidad|prueba basada en la proximidad]], [[Índice de términos#Laboratorio de pruebas remoto|laboratorio de pruebas remoto]], [[Índice de términos#Simulador|simulador]]

## Objetivos de aprendizaje
- **NBPAM-4.1.1 (K1)**: recordar los entornos de desarrollo de apps móviles.
- **NBPAM-4.2.1 (K1)**: recordar herramientas comunes incluidas en las plataformas de desarrollo.
- **OP-4.2.1 (H1)**: usar herramientas del SDK para capturar pantallas, extraer registros y simular eventos entrantes.
- **NBPAM-4.3.1 (K2)**: comprender las diferencias entre emuladores y simuladores.
- **NBPAM-4.3.2 (K2)**: describir el uso de emuladores y simuladores en la prueba.
- **OP-4.3.2 (H1)**: crear y lanzar un dispositivo simulado o emulado, instalar una app y probarla.
- **NBPAM-4.4.1 (K2)**: diferenciar enfoques para montar un laboratorio de pruebas.

## 4.1 Plataformas de desarrollo para aplicaciones móviles

- Los entornos de desarrollo integrado (EDI/IDE) móviles ayudan a diseñar, codificar, compilar, instalar, desinstalar, monitorizar, emular, registrar y probar. Ejemplos: **Android Studio** (Android) y **Xcode** (iOS). Se distinguen de un IDE normal por su soporte adicional para móviles.
- Hay marcos de desarrollo multiplataforma que generan apps para varias plataformas sin código específico para cada una.

## 4.2 Herramientas de plataformas de desarrollo comunes

- Los SDK incluyen utilidades para capturar pantallas, extraer registros, enviar eventos aleatorios y notificaciones, monitorizar memoria y CPU y crear dispositivos virtuales.
- Ejemplos: Android Virtual Device (AVD) Manager, Android Debug Bridge (ADB) y Android Device Monitor en Android; Instruments en iOS.

## 4.3 Emuladores y simuladores

### 4.3.1 Introducción

| Aspecto | Simulador | Emulador |
|---|---|---|
| Qué modela | El entorno de ejecución. | El hardware, con el mismo entorno de ejecución del dispositivo físico. |
| Compilación | Versión dedicada que corre en el simulador, no en el dispositivo real; independiente del SO real. | El mismo byte-code que usa el dispositivo real. |
| Como sustituto del dispositivo | Más limitado: el byte-code difiere del que se distribuye. | Reduce el coste del entorno, pero no reemplaza al dispositivo: puede comportarse distinto por limitaciones de la plataforma anfitriona. |

- Ambos se usan a menudo como sinónimos, de forma incorrecta.
- Muy útiles en fases tempranas: se integran con el IDE y permiten desplegar, probar y monitorizar rápido.

### 4.3.2 Uso de emuladores y simuladores

- Cada SO trae su paquete; también los hay de terceros. Se lanzan, se instala la app y se prueba como en un dispositivo real.
- Parámetros configurables: red a distintas velocidades, intensidad de señal, pérdida de paquetes, cambio de orientación, generación de interrupciones, posición GPS. Algunos (posiciones GPS globales, intensidad de señal) son difíciles o caros de reproducir en dispositivos reales.
- La conexión e instalación puede requerir ADB por línea de comandos o hacerse desde Xcode o Android Studio.

## 4.4 Configuración de un laboratorio de pruebas

| Aspecto | Laboratorio en instalaciones de la organización | Laboratorio de prueba remoto |
|---|---|---|
| Concepto | Dispositivos, emuladores y simuladores en sitio. | Acceso remoto a dispositivos (ADR/RDA) alojados en el centro de datos del proveedor. |
| Selección de dispositivos | Por ranking de mercado, SO y versión, tamaño y densidad de pantalla, disponibilidad y coste, prestaciones especiales e importancia para el público objetivo. | Según la oferta del proveedor; hay que evaluar cada proveedor, sobre todo en seguridad. |
| Ventajas | Pruebas de proximidad; aspectos de sensores como batería y tacto; mayor seguridad. | Dispositivos o redes que no se tienen en sitio; disponibilidad bajo demanda; escalable; ubicaciones geográficas útiles para red y GPS. |
| Desventajas | Presupuesto alto de compra y mantenimiento; disponibilidad a tiempo; difícil probar en distintos lugares y entornos. | Respuesta lenta; interacción limitada (multitáctil, gestos); rentable en uso esporádico pero caro en uso prolongado y amplio; NFC, Bluetooth y batería son difíciles de probar en la nube. |

- Prestaciones adicionales de algunos laboratorios remotos: dispositivos físicos dedicados (por ejemplo, el laboratorio de Samsung), dispositivos genéricos exclusivos por SO y versión, brazos robóticos para tacto y gestos, conexión por VPN, conexiones con varios operadores, herramientas y servicios de automatización.
- Se puede usar uno de los dos enfoques o una combinación, según los tipos de prueba.
