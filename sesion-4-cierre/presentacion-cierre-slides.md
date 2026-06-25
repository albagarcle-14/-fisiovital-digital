# FisioVital Digital

## Módulo de Facturación y Gestión

**Jefa de Proyecto:** Alba García

**Repositorio:** https://github.com/Alba-Garcia14/-fisiovital-digital-main

---

# Agenda

- Inicio / Justificación
- Planificación y cronograma
- Ejecución: cambios, incidencias y DevOps
- Cierre y aceptación
- Evidencia Git
- Conclusiones y siguientes pasos

---

# Inicio / Justificación

- Necesidad: automatizar y centralizar la facturación de FisioVital.
- Objetivo SMART: implementar el módulo de facturación digital con endpoints `/facturas`, `/facturas/{id}` y `/facturas/{id}/estado` en 3 meses.
- Stakeholders clave:
  - Marta Sánchez: gerente y patrocinadora
  - Ana: administradora
  - Recepcionistas y fisioterapeutas

---

# Alcance del Proyecto

### Incluye

- API de facturación y estados de factura.
- Roles Administrador y Recepcionista.
- Almacenamiento seguro y validación de pólizas para mutuas.

### No incluye

- Pago online.
- Integración automática con APIs de mutuas.
- Módulo para fisioterapeutas.

---

# Planificación y Cronograma

- WBS/EDT: análisis, backend, frontend, QA, DevOps, despliegue.
- Cronograma 3 meses con hitos semanales.
- Riesgos principales:
  - Integración con aseguradoras externas.
  - Cumplimiento RGPD.
  - Cambios en el contrato API.

---

# Ejecución: Cambios y DevOps

- CR-001: recordatorios automáticos por email aprobado.
- Infraestructura en la UE y pipeline CI/CD configurado.
- INC-001: fallo en pipeline por versión de librería de cifrado, resuelto con sincronización de contenedores.

---

# Estado de QA

- Autenticación: 100% OK.
- Citas: 100% OK.
- Historial clínico: 100% OK.
- Facturación Mixta: en progreso, 60% de tests bloqueados por reglas de seguros.

---

# Cierre y Aceptación

- Acta aceptada con condiciones.
- Facturación parcialmente entregada.
- Pendiente ajuste final de reglas de mutuas y cierre definitivo de QA.

---

# Evidencia Git

- Commits clave en `main`:
  - `ec1460b` — first commit
  - `a55b012` — docs(cierre): acta de aceptación final
  - `e34d6a2` — docs(cierre): informe de cierre del proyecto
  - `f221a8e` — docs: completar documentos de cierre
- Subir al remoto si no está en GitHub:

```powershell
cd "c:\Users\alba_\Downloads\-fisiovital-digital-main"
git push -u origin main
```

---

# Lecciones Aprendidas

- Contrato API temprano fue clave.
- El control de dependencias en CI debe ser más rígido.
- Revisión intermedia con el cliente reduce reservas en el cierre.

---

# Cierre y Siguientes Pasos

- Acción inmediata: completar el push y versionar.
- Tag recomendado: `v1.0`.
- Próximo paso: finalizar QA y reglas de facturación de mutuas.

---

# Recursos de Apoyo

- `README.md`
- `01-inicio/project-charter.md`
- `02-planificacion/cronograma.md`
- `03-ejecucion/devops/pipeline-despliegue.md`
- `sesion-4-cierre/informe-cierre.md`
