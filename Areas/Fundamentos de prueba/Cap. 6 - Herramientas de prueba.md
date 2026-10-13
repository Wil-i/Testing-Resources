---
tags: [capitulo]
area: "[[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]"
capitulo: 6
paginas: "73–75"
duracion: "20 min"
---

# 6. Herramientas de prueba

> Parte de [[Areas/Fundamentos de prueba/Fundamentos de prueba|Fundamentos de prueba]]

**Términos clave:** [[Índice de términos#Automatización de la prueba|automatización de la prueba]]

## Objetivos de aprendizaje
- **FL-6.1.1 (K2)**: explicar cómo apoyan la prueba los distintos tipos de herramientas.
- **FL-6.2.1 (K1)**: recordar las ventajas y los riesgos de la automatización de la prueba.

## 6.1 Herramientas de apoyo a la prueba

Las herramientas apoyan y facilitan muchas actividades de prueba. Ejemplos:

| Tipo de herramienta | Cómo apoya la prueba |
|---|---|
| Gestión | Aumentan la eficiencia del proceso facilitando la gestión del CVDS, los requisitos, las pruebas, los defectos y la configuración. |
| Prueba estática | Ayudan a hacer revisiones y análisis estático. |
| Diseño e implementación de pruebas | Facilitan la generación de casos, datos y procedimientos de prueba. |
| Ejecución de la prueba y cobertura | Facilitan la ejecución automatizada y la medición de la cobertura. |
| Prueba no funcional | Permiten pruebas no funcionales difíciles o imposibles de hacer a mano. |
| DevOps | Apoyan el canal de entrega DevOps, el seguimiento del flujo de trabajo, la construcción automatizada y la IC/EC. |
| Colaboración | Facilitan la comunicación. |
| Escalabilidad y normalización del despliegue | Por ejemplo, máquinas virtuales y herramientas de contenedores ("contenerización", traducción que el propio programa considera no definitiva). |
| Otras | Cualquier herramienta que ayude a probar; en ese contexto, incluso una hoja de cálculo es una herramienta de prueba. |

## 6.2 Ventajas y riesgos de la automatización de la prueba

Adquirir una herramienta no garantiza el éxito: cada herramienta nueva exige esfuerzo para lograr beneficios reales y duraderos (introducción, mantenimiento, formación) y conlleva riesgos que hay que analizar y mitigar.

| Ventajas potenciales | Riesgos potenciales |
|---|---|
| Ahorra tiempo al reducir trabajo manual repetitivo: ejecutar regresión, reintroducir los mismos datos, comparar resultados esperados y reales, contrastar con estándares de codificación. | Expectativas poco realistas sobre la herramienta, incluidas su funcionalidad y facilidad de uso. |
| Previene errores humanos simples gracias a la consistencia y la repetibilidad: pruebas derivadas de forma coherente de los requisitos, datos creados sistemáticamente, ejecución en el mismo orden y con la misma frecuencia. | Estimaciones imprecisas del tiempo, el coste y el esfuerzo de introducir la herramienta, mantener los guiones y cambiar el proceso manual existente. |
| Evaluación más objetiva (por ejemplo, de la cobertura) y medidas demasiado complejas de obtener para una persona. | Usar una herramienta cuando la prueba manual es más apropiada. |
| Acceso más fácil a la información de prueba para la gestión y los informes: estadísticas, gráficos y datos agregados sobre avance, tasas de defectos y duración de la ejecución. | Confiar demasiado en la herramienta e ignorar la necesidad del pensamiento crítico humano. |
| Ejecución más rápida: detección de defectos más temprana, retroalimentación más rápida y menor tiempo de comercialización. | Depender del proveedor, que puede quebrar, retirar o vender la herramienta o dar un soporte deficiente (consultas, actualizaciones, corrección de defectos). |
| Más tiempo para que los probadores diseñen pruebas nuevas, más profundas y más eficaces. | Usar software de código abierto que puede quedar abandonado o cuyos componentes internos exigen actualizaciones frecuentes. |
| | Incompatibilidad de la herramienta con la plataforma de desarrollo. |
| | Elegir una herramienta que no cumple los requisitos reglamentarios o los estándares de seguridad física. |
