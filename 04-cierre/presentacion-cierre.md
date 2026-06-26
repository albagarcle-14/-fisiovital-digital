# Presentación final — FisioVital Digital

Duración objetivo: 8–10 minutos. Guion detallado con notas del orador.

---

## 1. Título y apertura (30 s)
- Proyecto: **FisioVital Digital — Módulo de Facturación y Gestión**
- Jefa de Proyecto: **Alba García**
- Repositorio (evidencia): [ -fisiovital-digital-main ](../..#L1)

---

## 2. Agenda (20 s)
- Inicio / Justificación
- Planificación y cronograma
- Ejecución (cambios, incidencias, DevOps)
- Cierre y aceptación
- Evidencia en Git (commits, PRs, issues, tags)
- Conclusiones y siguientes pasos

---

## 3. Inicio / Justificación (1 min)
- Necesidad: automatizar y centralizar la facturación para evitar descuadres y pérdida de tiempo.
- Documento base: [01-inicio/project-charter.md](01-inicio/project-charter.md#L1-L20)
- Stakeholders clave: Marta Sánchez (patrocinadora), Ana (administradora). See [01-inicio/stakeholders.md](01-inicio/stakeholders.md#L1-L12).

---

## 4. Alcance (45 s)
- Incluye: endpoints `/facturas`, `/facturas/{id}`, `/facturas/{id}/estado`; roles Administrador y Recepcionista; almacenamiento seguro. ([Project Charter](01-inicio/project-charter.md#L23-L48)).
- Excluye: pasarela de pago online, integración automática con mutuas (Fase 2).

---

## 5. Planificación y cronograma (1 min 15 s)
- WBS/EDT: [02-planificacion/edt.md](02-planificacion/edt.md#L1-L20)
- Cronograma y Gantt: [02-planificacion/cronograma.md](02-planificacion/cronograma.md#L1-L30)
- Riesgos principales: integraciones con aseguradoras, RGPD, cambios de alcance ([02-planificacion/riesgos.md](02-planificacion/riesgos.md#L1-L20)).


---

## 6. Ejecución (2 min)
- Cambios: **CR-001** — recordatorios automáticos por email (aceptado). ([03-ejecucion/cambios/CR-001-recordatorios.md](03-ejecucion/cambios/CR-001-recordatorios.md#L1-L20))
- DevOps: entornos en la UE, pipeline CI/CD, checklist de salida a producción. ([03-ejecucion/devops/pipeline-despliegue.md](03-ejecucion/devops/pipeline-despliegue.md#L1-L40))
- Incidencias: **INC-001** (incompatibilidad de librería de cifrado) resuelta actualizando la imagen de contenedor. ([03-ejecucion/incidencias/incidencia-001.md](03-ejecucion/incidencias/incidencia-001.md#L1-L20))


---

## 7. QA y estado de pruebas (1 min)
- Estado actual: autenticación, citas e historial OK; Facturación Mixta: pruebas bloqueadas ~60% por reglas de mutuas. ([03-ejecucion/qa/pruebas.md](03-ejecucion/qa/pruebas.md#L1-L20)).
- Mitigaciones: mocks para aseguradoras y redefinición de casos de prueba.


---

## 8. Cierre y acta de aceptación (1 min)
- Acta de aceptación: aceptado con condiciones; facturación parcialmente entregada. ([sesion-4-cierre/acta-aceptacion.md](sesion-4-cierre/acta-aceptacion.md#L1-L30)).
- Informe de cierre con comparativa plan vs real y entregables listados. ([sesion-4-cierre/informe-cierre.md](sesion-4-cierre/informe-cierre.md#L1-L40)).


---

## 9. Evidencia Git (1 min)
- Commits relevantes en `main` (local):
	- `ec1460b` — first commit
	- `a55b012` — docs(cierre): acta de aceptación final
	- `e34d6a2` — docs(cierre): informe de cierre del proyecto
	- `f221a8e` — docs: completar documentos de cierre (acta, informe, lecciones, postmortem)
	(Referencia: `.git/logs/refs/heads/main` en el repositorio local.)
- Pull Requests / Issues / Tags: revisa en GitHub: https://github.com/Alba-Garcia14/-fisiovital-digital-main

Comando para subir commits si no están en remoto:
```powershell
cd "c:\Users\alba_\Downloads\-fisiovital-digital-main"
git push -u origin main
```
---

## 10. Lecciones aprendidas y recomendaciones (1 min)
- Lecciones: contrato API temprano ayudó; falta de control de dependencias provocó INC-001. ([sesion-4-cierre/lecciones-aprendidas.md](sesion-4-cierre/lecciones-aprendidas.md#L1-L20)).
- Recomendaciones: implementar lockfiles y escaneo de dependencias en CI; usar PRs descriptivos y tags de versión; revisión intermedia con cliente antes del cierre.

---

## 11. Cierre y llamada a la acción (20 s)
- Acción inmediata: ejecutar `git push -u origin main` para centralizar evidencia en GitHub y crear tag `v1.0` cuando QA esté cerrado:
```powershell
git tag -a v1.0 -m "v1.0 entrega inicial" 
git push origin v1.0
```
- Ofrezco demo en vivo de `openapi.yaml` y `informe-cierre.md`.

---

## Apéndice: Recursos rápidos
- README: [README.md](../README.md#L1)
- Project Charter: [01-inicio/project-charter.md](01-inicio/project-charter.md#L1-L20)
- Cronograma: [02-planificacion/cronograma.md](02-planificacion/cronograma.md#L1-L30)
- Pipeline: [03-ejecucion/devops/pipeline-despliegue.md](03-ejecucion/devops/pipeline-despliegue.md#L1-L40)
- Informe de cierre: [sesion-4-cierre/informe-cierre.md](sesion-4-cierre/informe-cierre.md#L1-L40)

---

Fin de la presentación. 

Nota final para el orador: práctica de 8–10 minutos; usa las notas para navegar los documentos mostrados en la demo.
