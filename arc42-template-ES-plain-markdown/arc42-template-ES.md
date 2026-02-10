---
date: Enero 2023
title: Plantilla ![arc42](images/arc42-logo.png)
---

#

**Acerca de arc42**

arc42, la plantilla de documentación para arquitectura de sistemas y de software.

Por Dr. Gernot Starke, Dr. Peter Hruschka y otros contribuyentes.

Revisión de la plantilla: 7.0 ES (basada en asciidoc), Enero 2017

© Reconocemos que este documento utiliza material de la plantilla de arquitectura arc42, https://www.arc42.org.

---

# Introducción y Metas {#section-introduction-and-goals}

## Vista de Requerimientos {#_vista_de_requerimientos}

El sistema corresponde a un **ERP enfocado en el Módulo de Compras**, cuyo objetivo es gestionar de manera eficiente los procesos de adquisición de productos dentro de una organización.

El sistema permitirá:

- Registrar y administrar productos
- Registrar y administrar proveedores
- Crear, consultar y actualizar órdenes de compra
- Controlar el estado de las órdenes de compra
- Actualizar el inventario tras confirmar una compra
- Integrarse con un sistema contable externo

## Metas de Calidad {#_metas_de_calidad}

- **Usabilidad**: interfaz clara y fácil de usar
- **Disponibilidad**: acceso continuo al sistema
- **Mantenibilidad**: código modular y bien estructurado
- **Seguridad**: control de acceso a la información
- **Escalabilidad**: posibilidad de crecimiento del sistema

## Partes interesadas (Stakeholders) {#_partes_interesadas_stakeholders}

| Rol/Nombre              | Contacto              | Expectativas                                   |
|------------------------|-----------------------|------------------------------------------------|
| Administrador del ERP  | admin@empresa.com     | Gestión completa del módulo de compras         |
| Usuario Administrativo | usuario@empresa.com   | Facilidad de uso y rapidez                     |
| Área Contable          | contabilidad@empresa.com | Información confiable de compras           |
| Equipo de TI           | soporte@empresa.com   | Sistema mantenible y estable                   |

---

# Restricciones de la Arquitectura {#section-architecture-constraints}

- El backend será desarrollado en **Java con Spring Boot**
- La base de datos utilizada será **PostgreSQL**
- El frontend será una **SPA desarrollada en React**
- La comunicación será mediante **APIs REST con JSON**
- El sistema se desplegará en un entorno **Linux**

---

# Alcance y Contexto del Sistema {#section-context-and-scope}

## Contexto de Negocio {#_contexto_de_negocio}

El sistema ERP – Módulo de Compras interactúa con:

- Usuarios administrativos
- Proveedores (indirectamente)
- Sistema contable externo

![Diagrama de Contexto](./images/c1_context.png)

## Contexto Técnico {#_contexto_técnico}

- Frontend web (React)
- Backend (Spring Boot)
- Base de datos PostgreSQL
- API externa del sistema contable

---

# Estrategia de solución {#section-solution-strategy}

Se implementa una arquitectura basada en **contenedores**, separando claramente frontend, backend y base de datos, permitiendo escalabilidad, mantenibilidad y facilidad de despliegue.

---

# Vista de Bloques {#section-building-block-view}

## Sistema General de Caja Blanca {#_sistema_general_de_caja_blanca}

![Diagrama de Contenedores](./images/c2_containers.png)

Motivación  
: Separar responsabilidades y facilitar el mantenimiento del sistema.

Bloques de construcción contenidos  
: Frontend, Backend, Base de Datos, Sistema Contable Externo.

Interfases importantes  
: API REST entre frontend y backend, integración con sistema contable.

### Frontend (React)

Responsabilidad: Interfaz gráfica para el usuario.

Interfases: API REST

### Backend (Spring Boot)

Responsabilidad: Lógica de negocio y validación de datos.

Interfases: REST API, conexión a base de datos.

### Base de Datos (PostgreSQL)

Responsabilidad: Persistencia de la información.

---

# Vista de Ejecución {#section-runtime-view}

## Registrar un Producto {#_escenario_de_ejecución_1}

1. El usuario ingresa al formulario de registro.
2. El frontend envía los datos al backend.
3. El backend valida la información.
4. Se guarda el producto en la base de datos.
5. Se retorna confirmación al usuario.

![Diagrama de Secuencia](./images/sequence_register_product.png)

---

# Vista de Despliegue {#section-deployment-view}

## Nivel de infraestructura 1 {#_nivel_de_infraestructura_1}

El sistema se despliega en:

- Servidor web para frontend
- Servidor de aplicaciones para backend
- Servidor de base de datos independiente

---

# Conceptos Transversales (Cross-cutting) {#section-concepts}

## Seguridad

Autenticación y autorización de usuarios.

## Persistencia

Uso de ORM para manejo de datos.

---

# Decisiones de Diseño {#section-design-decisions}

- Uso de arquitectura en capas
- Separación frontend y backend
- Uso de REST para comunicación

---

# Requerimientos de Calidad {#section-quality-scenarios}

## Escenarios de calidad {#_escenarios_de_calidad}

- El sistema debe responder en menos de 2 segundos.
- El sistema debe permitir múltiples usuarios concurrentes.

---

# Riesgos y deuda técnica {#section-technical-risks}

- Dependencia de sistemas externos
- Escalabilidad futura no probada

---

# Glosario {#section-glossary}

| Término         | Definición                                               |
|-----------------|----------------------------------------------------------|
| Producto        | Artículo adquirido por la empresa                        |
| Proveedor       | Entidad que suministra productos                         |
| Orden de Compra | Registro de adquisición de productos                     |
| ERP             | Sistema de planificación de recursos empresariales       |
