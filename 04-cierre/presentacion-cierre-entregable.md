# Presentación Final - FisioVital Digital

Documento listo para entregar. Presentación estructurada para una exposición de 8-10 minutos.

## 1. Título y apertura (30 s)
- Proyecto: **FisioVital Digital — Módulo de Facturación y Gestión**
- Jefa de Proyecto: **Alba García**
- Repositorio: https://github.com/Alba-Garcia14/-fisiovital-digital-main

## 2. Agenda (20 s)
- Inicio / Justificación
- Planificación y cronograma
- Ejecución: cambios, incidencias y DevOps
- Cierre y aceptación
- Evidencia Git
- Conclusiones y siguientes pasos

## 3. Inicio / Justificación (1 min)
- Necesidad: automatizar y centralizar la facturación de FisioVital para eliminar descuadres financieros y reducir tiempo administrativo.
- Objetivo SMART: implementar el módulo de facturación digital con endpoints `/facturas`, `/facturas/{id}` y `/facturas/{id}/estado` en un plazo de 3 meses.
- Stakeholders clave: Marta Sánchez (gerente y patrocinadora), Ana (administradora), equipo de recepcionistas y fisioterapeutas.

## 4. Alcance (45 s)
- Incluye:
  - Desarrollo de la API de facturación y estados de factura.
  - Roles de Administrador y Recepcionista con niveles de acceso diferenciados.
  - Almacenamiento seguro en base de datos centralizada.
  - Validación del número de póliza/cobertura para mutuas.
- No incluye:
  - Pasarela de pago online.
  - Integraciones automáticas con APIs externas de mutuas.
  - Acceso para fisioterapeutas ni exportación contable automatizada.

## 5. Planificación y cronograma (1 min 15 s)
- WBS/EDT: análisis, backend, frontend, QA, DevOps, despliegue.
- Cronograma de 3 meses con hitos semanales y Gantt definido.
- Principales riesgos:
  - Integración con aseguradoras externas.
  - Cumplimiento RGPD en datos de salud.
  - Cambios de alcance y desviaciones en API.

## 6. Ejecución (2 min)
- Gestión del cambio: solicitud **CR-001** de recordatorios automáticos por email aprobada y planificada.
- DevOps: infraestructura en la UE, pipeline CI/CD automatizado y backups programados.
- Incidencia técnica: **INC-001** resuelta al sincronizar versiones de librería de cifrado entre backend y pipeline.

## 7. QA y estado de pruebas (1 min)
- Pruebas ejecutadas con éxito en autenticación, citas e historial.
- Facturación mixta en progreso, con bloqueo parcial del 60% debido a ajustes en reglas de cálculo entre particulares y seguros.
- Mitigación: uso de mocks para simulaciones de aseguradoras y validación iterativa.

## 8. Cierre y acta de aceptación (1 min)
- Acta aceptada con condiciones: entrega parcial aceptada, pendiente ajuste final de facturación mixta.
- Se entregó: módulos de autenticación, citas, pacientes, primeros informes y esquema de facturación.
- Se dejó constancia de reservas para completar las reglas de negocio de mutuas y finalizar QA.

## 9. Evidencia Git (1 min)
- Commits relevantes en la rama `main` local:
  - `ec1460b` — first commit
  - `a55b012` — docs(cierre): acta de aceptación final
  - `e34d6a2` — docs(cierre): informe de cierre del proyecto
  - `f221a8e` — docs: completar documentos de cierre (acta, informe, lecciones, postmortem)
- Para visualizar en GitHub si no está subido:
```powershell
cd "c:\Users\alba_\Downloads\-fisiovital-digital-main"
git push -u origin main
```
- Si se desea versionar la entrega:
```powershell
git tag -a v1.0 -m "v1.0 entrega inicial"
git push origin v1.0
```

## 10. Lecciones aprendidas y recomendaciones (1 min)
- Contrato API temprano y documentación clara ayudaron a alinear al equipo.
- La facturación mixta requiere validación de reglas de negocio reales antes de cerrar el proyecto.
- Recomendación: implementar control de dependencias y validación de entornos en CI, y formalizar revisiones intermedias con el cliente.

## 11. Cierre y siguientes pasos (20 s)
- Acción inmediata: completar la subida a GitHub y generar el tag de versión.
- Paso siguiente: finalizar los tests y reglas de facturación de mutuas, luego cerrar la entrega total.

---

### Recursos de apoyo
- `README.md`
- `01-inicio/project-charter.md`
- `02-planificacion/cronograma.md`
- `03-ejecucion/devops/pipeline-despliegue.md`
- `sesion-4-cierre/informe-cierre.md`

Este archivo está listo para entregar como guion final de la presentación.
