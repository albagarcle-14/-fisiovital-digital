```markdown
# Plan de Pruebas y Estado de QA — Semana 6

## Resumen de Ejecución
A fecha de la Semana 6, el plan de pruebas automatizadas se ha integrado completamente en el pipeline de CI/CD.

## Matriz de Estado de Tests
| Componente | Tipo de Test | Estado | Resultado |
|---|---|---|---|
| Autenticación | Unitario / Integración | Ejecutado | Pasado (100%) |
| Citas | Unitario / Validación | Ejecutado | Pasado (100%) |
| Historial Clínico | Cifrado de Datos | Ejecutado | Pasado (100%) |
| Facturación Mixta | Lógica de Negocio | En progreso | Bloqueado parcialmente |

## Nota Técnica
Los tests del módulo de Facturación están fallando en un 60% debido a las desviaciones detectadas en las reglas de cálculo de mutuas frente a particulares. El equipo de QA está redefiniendo los casos de prueba en paralelo al desarrollo Backend.
