# Plan de pruebas — Módulo Facturación

## Alcance
Basado en el contrato 02-planificacion/api/openapi.yaml: endpoints `/facturas`, `/facturas/{id}` y `/facturas/{id}/estado`.

## Tipos de prueba
- Funcional
- Integración
- Regresión
- Aceptación

## Casos de prueba
| ID | Caso | Endpoint | Resultado esperado |
|---|---|---|---|
| TC01 | Crear factura particular estándar | POST /facturas | 201 Created |
| TC02 | Crear factura con cobertura de seguro médica | POST /facturas | 201 Created |
| TC03 | Crear factura mixta (Copago: Particular + Seguro) | POST /facturas | 201 Created (Cálculo de importes proporcional) |
| TC04 | Intentar crear factura con ID de cita inexistente | POST /facturas | 400 Bad Request |
| TC05 | Intentar facturar importe negativo o cero | POST /facturas | 422 Unprocessable Entity |
| TC06 | Consultar factura existente por ID | GET /facturas/{id} | 200 OK con modelo estructurado |
| TC07 | Consultar factura inexistente | GET /facturas/{id} | 404 Not Found |
| TC08 | Actualizar estado de factura a 'Pagada' | PATCH /facturas/{id}/estado | 200 OK |
| TC09 | Intentar cambiar estado de factura con token inválido | PATCH /facturas/{id}/estado | 401 Unauthorized |

## Criterios de salida a producción
- 100% de los casos de prueba críticos (TC01 a TC05) ejecutados con éxito.
- Cobertura de código en pruebas unitarias del módulo de facturación igual o superior al 85%.
- Cero vulnerabilidades críticas o altas detectadas en el manejo de datos de facturación.
