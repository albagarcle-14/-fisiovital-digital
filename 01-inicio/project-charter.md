# Project Charter — FisioVital Digital
 
## 1. Justificación del proyecto
El proyecto surge ante la necesidad crítica de la clínica FisioVital de automatizar, digitalizar y centralizar su proceso de facturación. Actualmente, la gestión manual de cobros a pacientes particulares y el control de los reembolsos por seguros/mutuas médicas genera descuadres financieros mensuales, ineficiencia administrativa y pérdidas de tiempo. Este módulo resolverá estos problemas integrando el control de los estados de pago directamente con el flujo operativo de la clínica.
 
## 2. Objetivos SMART
- **S (Específico):** Desarrollar e implementar el módulo de facturación digital que gestione los flujos de cobro a particulares y mutuas.
- **M (Medible):** Lograr que el 100% de las facturas emitidas por la clínica queden registradas digitalmente bajo los endpoints `/facturas`.
- **A (Alcanzable):** Basar el desarrollo estrictamente en el contrato técnico predefinido en `openapi.yaml`.
- **R (Relevante):** Eliminar por completo los descuadres financieros de caja al cierre de cada mes en la clínica.
- **T (Acotado en el tiempo):** Tener el sistema desplegado y operando en el entorno de producción en un plazo máximo de 2 meses.
 
## 3. Alcance de alto nivel
**Incluye:**
- Desarrollo de los endpoints `/facturas` (creación de facturas para particulares y asegurados), `/facturas/{id}` (consulta del detalle de factura) y `/facturas/{id}/estado` (actualización de estados como "Pendiente" o "Pagada").
- Interfaz web con dos roles de acceso diferenciados: Administrador (Marta, con acceso total) y Recepcionista (creación y modificación de estados).
- Almacenamiento seguro en la base de datos centralizada de la clínica.
- Casilla obligatoria para adjuntar y validar el número de póliza/cobertura en facturas de mutuas.

**No incluye:**
- Conexión automatizada mediante APIs externas con los sistemas propios de las mutuas médicas (la validación inicial se gestionará de manera manual en recepción).
- Módulo de pasarela de pago online (tarjetas de crédito/débito en la web).
- Acceso o visualización del módulo para el rol de fisioterapeuta.
- Exportación automatizada de archivos contables para gestorías externas (Fase 2).
 
## 4. Hitos principales
| Hito | Fecha estimada |
|---|---|
| Acta de Inicio y Project Charter aprobados | Semana 1 |
| Configuración del entorno y Base de Datos | Semana 3 |
| Desarrollo e integración de endpoints de la API | Semana 5 |
| Pruebas de integración, regresión y QA (Módulo Facturación) | Semana 6 |
| Pruebas de aceptación con el usuario (UAT) junto a Marta | Semana 7 |
| Despliegue en producción y cierre del proyecto | Semana 8 (2 meses) |
 
## 5. Presupuesto estimado de alto nivel
12.500 € (cifra orientativa calculada para cubrir las fases de análisis, desarrollo técnico basándose en OpenAPI, control de calidad QA y despliegue durante los 2 meses de ejecución).
 
## 6. Riesgos de alto nivel
- **Retraso por datos de terceros:** Que Marta se demore en entregar la lista de formatos de identificación de las 3 mutuas principales, retrasando el diseño de los formularios.
- **Atascamiento en pruebas de aceptación:** Que el personal de recepción requiera más tiempo de capacitación o detecte problemas de usabilidad que demoren la salida a producción.
- **Incompatibilidad del contrato:** Encontrar discrepancias imprevistas entre la base de datos actual de la clínica y la estructura definida en `openapi.yaml`.
 
## 7. Jefe de proyecto y autoridad
Alba García — autoridad para:
- Gestionar la asignación de tareas del equipo de desarrollo y asegurar el cumplimiento del Plan de Pruebas.
- Administrar el uso del presupuesto asignado dentro de los límites establecidos.
- Actuar como el canal único de comunicación técnica con la cliente Marta Sánchez para la validación de entregables.
 
## 8. Criterios de éxito y aceptación
- **Alineación Técnica:** Pasar el 100% de las pruebas funcionales garantizando que las respuestas de la API mapean de manera idéntica con el contrato establecido.
- **Satisfacción del Cliente:** Obtención del "Sign-off" (aprobación firmada) de Marta Sánchez tras realizar las pruebas de uso en el entorno de pruebas.
- **Puntualidad:** Completar el despliegue final antes de la fecha límite de los 2 meses para asegurar la apertura de la nueva sucursal de FisioVital.