## 1. Plataforma Blog: GitHub

## 2. Repositorio: mi-blog-tecnico/Readme.md

## 3. Entrada de Blog: Resolviendo anomalías de tracking en un entorno de alta demanda

### Contexto

Durante el diseño y ejecución de la estrategia digital *full-funnel* para el proyecto de zapatillas sostenibles TERRAE, implementamos un sistema de automatización basado en IA para la optimización dinámica de campañas. El objetivo del proyecto era escalar rápidamente las creatividades con mayor rendimiento y gestionar el tráfico hacia el embudo de ventas.

### Problema

En las primeras horas de la prueba de estrés de la campaña, nos enfrentamos a un desafío técnico crítico: un conflicto entre el script de optimización de la IA y el píxel de seguimiento principal. Esta colisión provocó que los eventos de conversión se dispararan por duplicado en el panel de control. Esto no solo amenazaba con corromper la integridad de nuestras métricas, sino que ponía en riesgo el presupuesto al alimentar a los algoritmos con datos falsos de retorno de inversión.

### Acciones

Detuvimos inmediatamente la inyección de tráfico y convocamos una revisión de *post-mortem* sin culpas (*blameless*). Las medidas técnicas que tomamos fueron:

1. Aislamiento y diagnóstico: Identificamos rápidamente que el archivo pixel-tracking.js estaba disparando el evento de forma duplicada debido a la nueva integración.

2. Refactorización: Modificamos la arquitectura de recolección de datos en el código, moviendo la confirmación de la conversión del lado del cliente al servidor (Server-Side Tracking) para garantizar una fuente única de verdad.

3. Despliegue rápido (Hotfix): Realizamos un commit directo en el repositorio principal para aplicar el parche de forma inmediata y detener la fuga de datos falsos de retorno de inversión.

### Aprendizajes

La lección principal fue que la velocidad al integrar nuevas herramientas nunca debe comprometer la arquitectura de datos. Implementamos dos mejoras permanentes en nuestro flujo de trabajo: la obligación de realizar pruebas en *staging* para cualquier inyección de código de terceros, y la configuración de alertas automáticas que nos avisen si hay un pico irreal de conversiones (ej. +200% en menos de una hora).

---

## 4. Documentación de Control de Versiones

Para asegurar la trazabilidad de la resolución, el flujo de trabajo quedó documentado en nuestro repositorio con las siguientes acciones clave:

* **Problema inicial:** `feat: implementación inicial de tracking con IA` ([Ver commit](https://github.com/contentweb10-del/mi-blog-tecnico/commit/172ce01d5838452ce8aec9ac22edf93b520d2f72))
* **Commit de Resolución:** `fix: migración de validación de eventos a server-side para evitar duplicidad` ([Ver commit](https://github.com/contentweb10-del/mi-blog-tecnico/commit/05f74df16f9c2c66408a9ab773d4950ad32c874a))

---

## 5. Reflexión: Feedback Radicalmente Sincero

Durante la reunión de *post-mortem*, pusimos en práctica los principios de la sinceridad radical (*radical candor*). En lugar de suavizar el error o, por el contrario, señalar con el dedo a quien autorizó el pase a producción, abordamos el fallo combinando el desafío directo con el cuidado personal. Fui transparente al señalar que nuestros protocolos de Quality Assurance (QA) fueron insuficientes y que nos saltamos pasos críticos por la prisa del lanzamiento. Al enfocar la crítica estrictamente en el *proceso* y no en las *personas*, evitamos actitudes defensivas. Esto permitió que todo el equipo colaborara activamente en diseñar los nuevos filtros de seguridad en lugar de preocuparse por proteger sus puestos, fortaleciendo enormemente la confianza del grupo.

---

## 6. Publicación



---

## 7. Checklist de Entrega Final

Copia y completa este bloque para tu entrega definitiva:

- [x] **URL pública del blog o entrada:** https://github.com/contentweb10-del/mi-blog-tecnico
- [x] **Enlace al repositorio o snapshot de commits:** https://github.com/contentweb10-del/mi-blog-tecnico/commits/main
- [x] **Breve reflexión sobre feedback aplicado:** Incluida. (Se abordó el fallo en el proceso de QA combinando desafío directo y empatía, separando a las personas del error para construir soluciones conjuntas sin generar actitudes defensivas).
- [x] **Documentación clara y estructurada según plantilla:** Completada.
- [x] **Evidencia de control de versiones:** Documentada en la sección 4.
