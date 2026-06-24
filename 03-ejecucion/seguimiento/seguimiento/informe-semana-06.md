```markdown
# Informe de seguimiento — Semana 6

**Fecha:** 24 de junio de 2026
**Periodo cubierto:** Semana 6 del proyecto

## Avance por módulo
| Módulo | Responsable | Previsto a fecha | Real a fecha | Estado |
|---|---|---|---|---|
| Autenticación | Backend | 100% | 100% | A tiempo |
| Citas | Backend | 100% | 100% | A tiempo |
| Pacientes/Historial | Backend | 100% | 100% | A tiempo |
| Facturación | Backend | 50% | 20% | Retraso: las reglas del pago mixto (particular/seguro) han costado más de lo previsto |
| Pantallas Autenticación | Frontend | 100% | 100% | A tiempo |
| Pantallas Citas | Frontend | 100% | 90% | 2 días de retraso, a la espera de un ajuste del contrato de API |
| Pantallas Pacientes/Historial | Frontend | ≈30% | 0% | No iniciado: se priorizó terminar Citas primero |
| Plan de pruebas | QA | 100% | 100% | A tiempo |
| Entornos | DevOps | 100% | 100% | A tiempo |
| Pipeline CI/CD | DevOps | 100% | 100% | A tiempo, pero ver INC-001 (incidencia de anoche) |

## Indicadores simplificados
- **Avance planificado:** 50%
- **Avance real:** 42%
- **SPI simplificado (real / planificado):** 0.84 *(Ritmo algo más lento de lo previsto)*
- **Coste planificado a fecha:** 14.000 €
- **Coste real a fecha:** 14.800 €
- **CPI simplificado (planificado / real):** 0.95 *(Gastando ligeramente más de lo previsto)*

## Hitos
- **Hito Alcanzado:** Infraestructura de red, pipelines de despliegue automatizados y base de datos RGPD completados y operativos en la UE.
- **Hito Retrasado:** Cierre de la lógica del Módulo de Facturación Mixta e integración del ajuste del contrato API en el Frontend.

## Problemas activos
1. Retraso en el desarrollo backend de las reglas de negocio para la facturación combinada (particulares frente a mutuas/seguros).
2. Bloqueo parcial en las pantallas de citas de Frontend (al 90%) pendientes de consolidar un cambio menor en el contrato OpenAPI.
3. Incidencia técnica detectada en el pipeline de DevOps la pasada noche (ver informe INC-001).
