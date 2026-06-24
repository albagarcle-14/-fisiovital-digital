# Acta de reunión — Descubrimiento inicial
 
 
**Fecha:** 24 de junio de 2026
**Asistentes:** 
Alba García (Jefe de Proyecto), 
Marta Sánchez (Gerente FisioVital)
 
## Temas tratados
- **Contexto del Módulo de Facturación:** Marta expone la necesidad crítica de digitalizar y agilizar el proceso de facturación, ya que actualmente el control de lo que se factura a particulares frente a lo que se gestiona a través de mutuas médicas genera descuadres al final del mes.
- **Flujo de Trabajo Requerido:** Se revisaron los endpoints de la API (`/facturas`). Se confirma que el sistema debe permitir registrar una factura en estado "Pendiente" y que el personal administrativo pueda cambiar su estado a "Pagada" una vez se verifique el cobro.
- **Tipos de Clientes:** Se identifican dos flujos principales: Paciente Particular (pago directo en clínica) y Paciente por Seguro Médico (requiere asociar el número de póliza y validar la cobertura de la mutua).
- **Fechas y Plazos:** Marta indica que necesitan tener el módulo en producción en un plazo máximo de 2 meses para hacerlo coincidir con la campaña de apertura de la nueva sucursal de la clínica.

## Acuerdos
- **Roles de Usuario:** Se acuerda que el sistema web tendrá dos roles diferenciados. El rol *Administrador* (Marta) tendrá control total y consulta de reportes, mientras que el rol *Recepcionista* solo podrá crear facturas y modificar su estado. Los fisioterapeutas no tendrán acceso a este módulo por motivos de privacidad.
- **Validación del Contrato OpenAPI:** Se utilizará de forma estricta el contrato de API especificado en `02-planificacion/api/openapi.yaml` sin añadir nuevos endpoints en esta primera fase para asegurar los plazos de entrega.
- **Ubicación de los Datos:** Las facturas generadas se almacenarán en la base de datos centralizada de FisioVital para que en la Fase 2 se puedan cruzar con el historial clínico de los pacientes.

## Preguntas abiertas pendientes de resolver
- **Integración con Mutuas:** Queda pendiente que Marta nos facilite la lista con los nombres y formatos de identificación de las 3 mutuas principales con las que trabaja la clínica para ajustar los campos de validación del formulario.
- **Exportación de Datos:** Se debe definir en la próxima reunión si el sistema requiere un botón para exportar el listado de facturas en formato CSV/Excel para el gestor contable externo de la empresa.