---
tags: [capitulo]
area: "[[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]"
capitulo: 5
paginas: "55–58"
duracion: "55 min"
---

# 5. Automatización de la ejecución de la prueba

> Parte de [[Areas/Pruebas de aplicaciones móviles/Pruebas de aplicaciones móviles|Pruebas de aplicaciones móviles]]

**Términos clave:** [[Índice de términos#Prueba basada en dispositivo|prueba basada en dispositivo]], [[Índice de términos#Informe de prueba|informe de prueba]], [[Índice de términos#Prueba basada en agente usuario|prueba basada en agente usuario]]

## Objetivos de aprendizaje
- **NBPAM-5.1.1 (K2)**: diferenciar enfoques y marcos comunes de automatización móvil.
- **NBPAM-5.2.1 (K2)**: describir métodos de automatización para apps móviles.
- **NBPAM-5.3.1 (K1)**: recordar los parámetros para evaluar herramientas de automatización móvil.
- **NBPAM-5.4.1 (K2)**: diferenciar enfoques de laboratorio de pruebas, con ventajas y desventajas para la automatización.

## 5.1 Enfoques de automatización

- La elección depende en parte del tipo de app.

| Enfoque | Funcionamiento | Aplicable a |
|---|---|---|
| Basado en agente usuario | Usa la cadena user-agent del navegador para hacerse pasar por un navegador concreto en un dispositivo concreto. | Apps web móviles. |
| Basado en dispositivo | Ejecuta la app directamente en el dispositivo. | Todo tipo de apps móviles. |

- La web móvil puede automatizarse con herramientas web de escritorio; las nativas suelen requerir herramientas específicas, y los proveedores de plataforma ofrecen herramientas propias.
- Siguen aplicando los enfoques clásicos: captura y reproducción, guiada por datos, guiada por palabras clave y guiada por comportamiento (CTFL y CTAL Test Automation Engineer).
- Capacidades clave de un marco de automatización móvil: identificación de objetos, operaciones sobre objetos, informes de prueba, API y extensibilidad, documentación adecuada, integración con otras herramientas e independencia de la práctica de desarrollo.

## 5.2 Métodos de automatización

- El probador debe entender cómo se graban o escriben los guiones y cómo acceder a objetos gráficos (botones, listas desplegables, campos).
- Métodos de identificación de objetos: reconocimiento de imagen, reconocimiento OCR o de texto, y reconocimiento de objetos (web o nativo según el tipo de app). Hay que elegir el que funcione en muchos dispositivos, en paralelo y de forma continua.

| Criterio | Identificación de objetos | Comparación de imágenes / OCR |
|---|---|---|
| Fiabilidad | Aguanta cambios de diseño mientras el identificador no cambie; riesgo de interactuar con objetos ocultos al usuario y obtener un falso negativo. | Las imágenes escalan con la pantalla, pero la prueba falla en cuanto cambia el diseño. |
| Experiencia del autor | Suele requerir escribir guiones a mano, al menos para mejorar legibilidad y mantenibilidad de lo grabado. | Prueba íntegramente por GUI, sin guiones. |
| Velocidad | Tiende a ser más rápida, sobre todo con herramientas nativas del fabricante. | Más lenta: compara píxel a píxel con imágenes de línea base. |
| Mantenimiento | Depende de la calidad de los guiones. | Sobre todo, reponer las imágenes de línea base que cambian. |
| Reto de creación | Dominar el lenguaje de guion y el diseño de software para una solución sostenible. | Generar imágenes de línea base, sobre todo si la app cambia a menudo. |

## 5.3 Evaluación de herramientas de automatización

- Dos categorías de parámetros: **ajuste organizativo** (ver CTFL, capítulo 6.2) y **ajuste técnico**.
- Parámetros técnicos:
  - Requisitos y complejidad de la automatización (Face ID, huella, chatbots).
  - Requisitos del entorno: condiciones de red variables, importación o creación de datos de prueba, virtualización del lado servidor.
  - Informes de prueba y bucles de retroalimentación.
  - Capacidad de gestionar ejecución a gran escala, local o en un laboratorio en la nube.
  - Integración con las demás herramientas de la organización.
  - Soporte y documentación para versiones actuales y futuras.

## 5.4 Enfoques de configuración para un laboratorio de automatización de pruebas

- Opciones: laboratorio de dispositivos en las instalaciones de la organización, laboratorio remoto o una combinación (comparados en el apartado 4.4 del [[Areas/Pruebas de aplicaciones móviles/Cap. 4 - Plataformas, herramientas y entornos|capítulo 4]]).
- Fases tempranas: dispositivos locales junto con emuladores y simuladores; mantener un laboratorio local es costoso y lento.
- Fases avanzadas: regresión completa, pruebas funcionales y no funcionales en un laboratorio completo; el laboratorio remoto en la nube, actualizado continuamente, complementa al local, asegura combinaciones de dispositivo y SO vigentes y aporta mejores informes y automatización avanzada.
- Al ejecutar a escala (marco de automatización o trabajo de integración continua), la estabilidad del laboratorio es clave para la eficiencia y fiabilidad.
- El laboratorio remoto no siempre es imprescindible: un laboratorio local bien diseñado y mantenido puede igualarlo o superarlo.
