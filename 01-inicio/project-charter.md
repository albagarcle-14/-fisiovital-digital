# Project Charter — FisioVital Digital
 
## 1. Justificación del proyecto
El proyecto surge ante la necesidad crítica de la clínica FisioVital de automatizar, digitalizar y centralizar su proceso de facturación. Actualmente, la gestión manual de cobros a pacientes particulares y el control de los reembolsos por seguros/mutuas médicas genera descuadres financieros mensuales, ineficiencia administrativa y pérdidas de tiempo. Este módulo resolverá estos problemas integrando el control de los estados de pago directamente con el flujo operativo de la clínica.
 
## 2. Objetivos SMART
- **S (Específico):** Desarrollar e implementar el módulo de facturación digital que gestione los flujos de cobro a particulares y mutuas.
- **M (Medible):** Lograr que el 100% de las facturas emitidas por la clínica queden registradas digitalmente bajo los endpoints `/facturas`.
- **A (Alcanzable):** Basar el desarrollo estrictamente en el contrato técnico predefinido en `openapi.yaml`.
- **R (Relevante):** Eliminar por completo los descuadres financieros de caja al cierre de cada mes en la clínica.
- **T (Acotado en el tiempo):** Tener el sistema desplegado y operando en el entorno de producción en un plazo máximo de 3 meses.
 
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
| Configuración del entorno de desarrollo y Base de Datos | Semana 3 |
| Desarrollo completo de la lógica de negocio y endpoints de la API | Semana 6 (Fin de Mes 1) |
| Pruebas de integración, regresión y QA del Módulo de Facturación | Semana 8 (Fin de Mes 2) |
| Pruebas de aceptación con el usuario (UAT) junto a Marta y Ana | Semana 10 |
| Capacitación del personal de recepción (Mitigación resistencia al cambio) | Semana 11 |
| Despliegue final en producción y migración desde el sistema Excel anterior | Semana 12 (Fin de Mes 3) |
 
 ## 5. Presupuesto estimado de alto nivel
Entre 25.000 € y 35.000 € para todo el proyecto (excluyendo el mantenimiento posterior).
     
## 6. Riesgos de alto nivel
  - **Resistencia al cambio:** Personal de recepción con más de 20 años de experiencia utilizando papel y métodos tradicionales, lo que puede dificultar la adopción de la plataforma web.
  - **Seguridad y Privacidad Extrema:** Manejo de historiales clínicos confidenciales; cualquier fallo de seguridad vulnera la estricta ley de protección de datos.
  - **Dependencia del plazo:** El contrato del proveedor del Excel actual vence en 3 meses exactos; si nos retrasamos, la clínica se queda sin sistema de gestión.
 
 
## 7. Jefe de proyecto y autoridad
Alba García — autoridad para:
- Gestionar la asignación de tareas del equipo de desarrollo y asegurar el cumplimiento del Plan de Pruebas.
- Administrar el uso del presupuesto asignado dentro de los límites establecidos.
- Actuar como el canal único de comunicación técnica con la cliente Marta Sánchez para la validación de entregables.
 
## 8. Criterios de éxito y aceptación
- Eliminación completa de errores por citas duplicadas en las clínicas.
- Separación limpia y sin errores en la facturación de pacientes particulares y de seguros.
- Capacidad de la gerencia para generar informes automáticos de ocupación por clínica en cualquier momento.
  