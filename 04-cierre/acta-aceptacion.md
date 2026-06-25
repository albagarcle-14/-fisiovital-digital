# Acta de aceptación final
 
**Fecha:** 24 de junio de 2026
**Asistentes:** Alba García (Jefa de Proyecto), Marta Sánchez (Gerente FisioVital)
 
## Repaso de criterios de éxito (Project Charter, Sesión 1)
| Criterio de éxito | ¿Cumplido? | Evidencia |
|---|---|---|
| Reducir errores de citas duplicadas | Sí | Módulo de Citas implementado y validado en pruebas unitarias y de integración con resultado 100% según el plan de QA. |
| Facturar sin líos entre particular y seguro | Parcialmente | Módulo de Facturación Mixta en desarrollo; pruebas de QA bloqueadas en un 60% por ajustes en reglas de cálculo de mutuas frente a particulares. |
| Informe de ocupación por clínica | Sí | Panel de Control y reportes automáticos definidos en el Project Charter; el backend e interfaz inicial se han completado y están disponibles para gerencia. |
 
## Alcance entregado frente al inicial
- Módulos del Project Charter:
  - Autenticación y permisos.
  - Gestión de Citas.
  - Pacientes e Historiales Médicos.
  - Facturación Mixta (parte implementada, especialmente estructura de facturas, estados y soporte de facturación particular / seguro).
  - Panel de Control y capacidad de informes automáticos.
- Cambios incorporados (CR-001): recordatorios automáticos de cita por correo electrónico, aceptados con condiciones para la Fase 1 y definidos como proceso backend con infraestructura SMTP necesaria.
 
## Condiciones o reservas del cliente
- El Módulo de Facturación Mixta requiere finalizar las reglas de negocio de cálculo para mutuas/seguros antes de considerarse completamente entregado.
- QA indica bloqueo parcial en el 60% de los tests de facturación debido a desviaciones en las reglas de cálculo de seguros frente a particulares.
- Se mantiene la reserva sobre la entrega total hasta completar el ajuste final del contrato OpenAPI y la integración de las pantallas pendientes en Frontend.
 
## Decisión
Aceptado con condiciones
