# Acta de kick-off interno
 
## Dudas/riesgos planteados por el equipo
- **Frontend:** Le preocupa que la estructura de datos definida en el archivo estático `openapi.yaml` sea demasiado rígida para construir los formularios dinámicos de las mutuas de seguros (por ejemplo, si el número de póliza cambia de formato según la compañía). Solicita revisar si hay margen para añadir lógica de validación visual en el cliente antes de enviar la petición POST.
- **Backend:** Detecta un riesgo potencial de rendimiento y concurrencia al consultar de forma masiva los estados de las facturas (`GET /facturas/{id}/estado`) durante los cierres de mes de la clínica. Propone implementar una estrategia de indexación en la base de datos sobre los campos de estado y fecha de emisión para evitar bloqueos del sistema.
- **QA:** Plantea la necesidad de contar con un entorno de base de datos aislado y poblado con datos de prueba ficticios (tanto de pacientes particulares como de pólizas simuladas) desde la semana 3. Advierte que si los datos de prueba no son realistas, los test de integración y aceptación automatizados podrían dar falsos positivos.
- **DevOps:** Alerta sobre la falta de un entorno de *Staging* o preproducción definido en los hitos iniciales. Recomienda automatizar un pipeline de CI/CD (Integración y Despliegue Continuos) para que cada cambio aprobado en el repositorio de GitHub se despliegue automáticamente en una URL de pruebas y evitar errores humanos de última hora en el despliegue final.
 
## Matriz RACI inicial (alto nivel)
| Actividad | Jefe de Proyecto | Frontend | Backend | QA | DevOps |
|---|---|---|---|---|---|
| Definir alcance | R/A | C | C | C | C |
| Diseño de interfaz | I | R/A | C | C | I |
| Lógica de negocio y datos | I | C | R/A | C | C |
| Pruebas | I | C | C | R/A | C |
| Despliegue | I | I | C | C | R/A |
 
*(R = Responsable, A = Aprobador, C = Consultado, I = Informado)*