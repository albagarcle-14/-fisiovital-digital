# Informe de cierre del proyecto
 
## Comparativa planificado vs. real
| Dimensión | Planificado | Real | Desviación |
|---|---|---|---|
| Alcance | Módulo de facturación mixta completo, panel de informes y migración desde Excel | Facturación mixta implementada parcialmente; informes, autenticación, citas y pacientes entregados; CR-001 de recordatorios aprobado | Parcial: entrega parcial del alcance principal de facturación, con ajuste pendiente de reglas de mutuas. |
| Plazo | 3 meses de ejecución total | Avance al 24 de junio de 2026: 42% completado frente al 50% planificado | Retraso del 16% en la ejecución hasta la semana 6, principalmente por la complejidad de facturación mixta. |
| Coste | 25.000 € - 35.000 € estimados | 14.800 € gastados hasta la semana 6 | Coste en línea con el presupuesto, ligera desviación al alza (CPI 0.95) por horas adicionales de QA y ajustes técnicos. |
 
## Estado final de los riesgos (de 02-planificacion/riesgos.md)
| ID | Riesgo | ¿Se materializó? | Notas |
|---|---|---|---|
| R1 | Retraso en la integración/simulación con aseguradoras médicas externas. | Sí | Se mitigó con mocks estáticos, pero el desarrollo de facturación se vio ralentizado por ajustes en reglas de seguro. |
| R2 | Complejidad técnica en el cifrado y protección de los historiales clínicos según el RGPD. | No | Se aplicaron librerías estándar desde el inicio y el desarrollo de datos clínicos avanzó sin incidencias graves. |
| R3 | Cuellos de botella en QA por cambios imprevistos en el contrato de la API a mitad del desarrollo. | Sí | El cambio en el contrato OpenAPI generó bloqueo parcial en QA y un retraso de 2 días en pantallas de Citas. |
| R4 | Caída del servidor centralizado en la UE provocando parada de servicio. | No | Infraestructura y backup en región europea se implementaron correctamente. |
| R5 | Desbordamiento del alcance inicial por peticiones de última hora del cliente. | Sí | Se aceptó CR-001 de recordatorios de cita por email como ampliación controlada fuera del alcance inicial. |
| R6 | Sanciones por almacenar datos de salud fuera de la UE. | No | El despliegue quedó definido para hosting en la UE y la auditoría de DevOps aseguró el cumplimiento. |
| R7 | Resistencia al cambio de las recepcionistas por una interfaz compleja. | No | Se planificó capacitación y pruebas de usabilidad; no hay evidencia de rechazo activo en esta fase. |
| R8 | Parada del proyecto por baja de un único desarrollador. | No | Se documentó el código y se mantuvieron dailies para asegurar continuidad. |
 
## Entregables generados durante el proyecto
- Project Charter del proyecto FisioVital Digital.
- Contrato OpenAPI unificado para Citas y Facturación (`02-planificacion/api/openapi.yaml`).
- EDT/WBS del proyecto (`02-planificacion/edt.md`).
- Plan de gestión de riesgos (`02-planificacion/riesgos.md`).
- Cronograma detallado con Gantt (`02-planificacion/cronograma.md`).
- Solicitud de cambio CR-001 de recordatorios automáticos (`03-ejecucion/cambios/CR-001-recordatorios.md`).
- Plan de pruebas y estado de QA (`03-ejecucion/qa/pruebas.md`).
- Informe de seguimiento Semana 6 (`03-ejecucion/seguimiento/seguimiento/informe-semana-06.md`).
- Acta de aceptación final (`sesion-4-cierre/acta-aceptacion.md`).
 
## Cierre administrativo/contractual
- Se confirma la aprobación del acta de aceptación con condiciones, dejando pendiente la culminación total del módulo de facturación mixta.
- El proyecto sigue el presupuesto estimado de 25.000 € - 35.000 €, con gasto reportado de 14.800 € a la semana 6 y una eficiencia de coste cercana a lo planificado.
- Se documenta que cualquier ampliación adicional sobre facturación de mutuas o pagos online deberá gestionarse como Fase 2.
- El cierre contractual final se validará tras completar los ajustes de QA en la facturación y la migración desde Excel.
