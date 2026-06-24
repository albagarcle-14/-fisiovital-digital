# ADR 001 — Arquitectura monolítica modular

## Estado
Aceptada

## Contexto
El proyecto FisioVital Digital cuenta con un plazo crítico e inamovible de 3 meses (12 semanas) debido al fin del contrato del sistema Excel actual. El presupuesto es ajustado (entre 25.000€ y 35.000€), lo que limita la cantidad de entornos de infraestructura que el perfil de DevOps puede desplegar. Además, el equipo técnico cuenta con recursos limitados (un Dev Frontend, un Dev Backend, un QA y un DevOps), por lo que se requiere una arquitectura que minimice la sobrecarga operativa y permita definir rápidamente el contrato de la API para que Frontend no trabaje a ciegas.

## Decisión
Se adopta una arquitectura **monolítica modular**, con un único desplegable dividido en los siguientes módulos independientes:
- Autenticación / Usuarios
- Citas
- Pacientes / Historial Clínico
- Facturación
- Administración / Informes

```mermaid
graph TD
    A[Monolito FisioVital Digital] --> B[Módulo Autenticación]
    A --> C[Módulo Citas]
    A --> D[Módulo Pacientes / Historial Clínico]
    A --> E[Módulo Facturación]
    A --> F[Módulo Administración / Informes]
    C --> B
    D --> B
    E --> C
    E --> D
    F --> C
    F --> D
    F --> E
