# Cronograma — FisioVital Digital

## Estimaciones recogidas del equipo

A continuación se detallan los tiempos estimados por cada rol técnico, considerando la complejidad del RGPD en los historiales clínicos, el diseño responsivo para ordenadores y tablets, y la simulación de las aseguradoras en el módulo de facturación.

| Módulo/tarea | Responsable | Duración estimada | Depende de |
|---|---|---|---|
| **Planificación:** Definir alcance, EDT y Contrato API | Todo el equipo | 5 días | Inicio del proyecto |
| **DevOps:** Configuración de Entornos (Hosting UE) | DevOps | 5 días | Definir alcance |
| **DevOps:** Pipeline CI/CD y Backups automáticos | DevOps | 5 días | Configuración de Entornos |
| **QA:** Plan de pruebas inicial y criterios de aceptación | QA | 5 días | Definir alcance |
| **Backend:** Autenticación y Seguridad RGPD | Backend | 5 días | Contrato API |
| **Backend:** Módulo Citas (Evitar duplicados) | Backend | 10 días | Autenticación |
| **Backend:** Módulo Pacientes e Historial Clínico | Backend | 12 días | Autenticación |
| **Backend:** Módulo Facturación Mixta (Particular/Seguros) | Backend | 15 días | Módulo Citas + Módulo Pacientes |
| **Frontend:** Pantallas de Autenticación | Frontend | 4 días | Autenticación (Backend) |
| **Frontend:** Pantallas de Citas (PC y Tablets) | Frontend | 10 días | Módulo Citas (Backend) |
| **Frontend:** Pantallas de Pacientes e Historial | Frontend | 10 días | Módulo Pacientes (Backend) |
| **Frontend:** Pantallas de Facturación Mixta | Frontend | 12 días | Módulo Facturación (Backend) |
| **Frontend:** Panel de Administración e Informes | Frontend | 6 días | Pantallas de Facturación |
| **QA:** Pruebas de Integración y Simulación de Seguros | QA | 8 días | Módulo Facturación + UI Frontend |
| **QA/Cierre:** Regresión final y Migración desde Excel | Todo el equipo | 5 días | Pruebas de Integración |
| **Cierre:** Capacitación del Personal de Recepción | Todo el equipo | 5 días | Regresión final (Semana 11) |

---

## Diagrama de Gantt

```mermaid
gantt
    title Cronograma FisioVital Digital
    dateFormat YYYY-MM-DD
    axisFormat %d/%m
    
    section Planificación
    Definir alcance y Contrato API :done, plan1, 2026-07-06, 5d
    
    section Backend
    Autenticación y RGPD           :back1, after plan1, 5d
    Módulo Citas                   :back2, after back1, 10d
    Módulo Pacientes/Historial     :back3, after back1, 12d
    Módulo Facturación Mixta       :back4, after back2 back3, 15d
    
    section Frontend
    Pantallas Autenticación        :front1, after back1, 4d
    Pantallas Citas (Web/Tablet)   :front2, after back2, 10d
    Pantallas Pacientes e Historial :front3, after back3, 10d
    Pantallas Facturación          :front4, after back4, 12d
    Panel Admin e Informes         :front5, after front4, 6d
    
    section QA
    Plan de pruebas inicial        :qa1, after plan1, 5d
    Simulación e Integración Seguros :qa2, after front4, 8d
    Regresión final y QA de Cierre  :qa3, after qa2, 5d
    
    section DevOps
    Entornos en la UE              :dev1, after plan1, 5d
    Pipeline CI/CD y Backups       :dev2, after dev1, 5d
    
    section Despliegue y Cierre
    Migración de datos (Excel)     :cierre1, after qa3, 2d
    Capacitación de Recepcionistas :cierre2, after cierre1, 5d
    
    section Hitos
    Entrega final y Despliegue     :milestone, m1, 2026-09-28, 0d
