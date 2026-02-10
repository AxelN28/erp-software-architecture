# Taller de Arquitectura de Software – ERP Módulo de Compras

Este repositorio contiene el desarrollo del **taller de Arquitectura de Software**, cuyo objetivo es documentar la arquitectura de un **sistema ERP enfocado en el Módulo de Compras**, utilizando la plantilla **arc42** como guía principal.

El sistema propuesto permite gestionar productos, proveedores y órdenes de compra, brindando una solución estructurada para el control del proceso de adquisiciones dentro de una organización.

La documentación arquitectónica describe el alcance del sistema, las decisiones tecnológicas, las restricciones de la arquitectura y los principales escenarios de ejecución, aplicando buenas prácticas de ingeniería de software.

---

## Diagramas de Arquitectura

Como parte del taller, se desarrollaron varios diagramas para representar la arquitectura del sistema:

- **Diagrama de Contexto (C1):**  
  Muestra la relación del sistema ERP con los actores externos, como los usuarios administrativos y el sistema contable, permitiendo entender el entorno en el que opera el sistema.

- **Diagrama de Contenedores (C2):**  
  Representa la estructura general del sistema, separando el frontend, el backend, la base de datos y los sistemas externos, y mostrando cómo se comunican entre sí.

- **Diagrama de Secuencia:**  
  Describe el flujo de ejecución de un escenario crítico del sistema, como el registro de un producto, mostrando la interacción entre el usuario, el frontend, el backend y la base de datos.

Estos diagramas facilitan la comprensión del diseño del sistema y respaldan las decisiones arquitectónicas documentadas.

---

## Tecnologías Utilizadas

- Backend: Java con Spring Boot  
- Frontend: React (SPA)  
- Base de datos: PostgreSQL  
- Comunicación: API REST  

---

## Autor

**Axel Salgado**  
Arquitectura de Software
