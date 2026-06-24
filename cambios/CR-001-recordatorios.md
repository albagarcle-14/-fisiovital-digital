# CR-001 — Solicitud de cambio: recordatorios automáticos de cita

## Solicitante
Marta Sánchez (Gerente FisioVital)

## Descripción de la solicitud
Añadir un sistema de recordatorios automáticos enviados a los pacientes 24 horas antes de su cita programada para mitigar el absentismo en la agenda. Inicialmente, el canal requerido será el correo electrónico (Email).

## Análisis de impacto
**Alcance:** Ampliación del alcance técnico en el Backend para programar la lógica de envío diario de correos. No altera el Frontend orientado al paciente.
**Tiempo:** Desviación estimada de 3 a 4 días adicionales de desarrollo sobre la línea base.
**Coste:** Impacto presupuestario bajo en infraestructura para contratar un proveedor SMTP externo. Horas de ingeniería asumibles por el margen de contingencia.
**Riesgos:** Riesgo de entregas en spam si las DNS del dominio no se configuran correctamente con registros SPF/DKIM.

## Recomendación técnica
El equipo considera el cambio totalmente viable. Backend confirma que la información de contacto ya reside en la base de datos y requiere un proceso cronológico automatizado. DevOps notifica la necesidad de dar de alta un servicio externo de pasarela de correo no contemplado en el plan inicial.

## Decisión
Aceptado con condiciones (Vía email exclusivamente para la Fase 1) — Fecha: 24 de junio de 2026.

```mermaid
sequenceDiagram
    participant Cliente
    participant JP as Jefe de Proyecto
    participant Backend
    participant DevOps
    Cliente->>JP: Solicita recordatorios automáticos
    JP->>Backend: ¿Es viable? ¿Cuánto cuesta?
    Backend->>JP: Estimación de esfuerzo
    JP->>DevOps: ¿Necesita infraestructura nueva?
    DevOps->>JP: Respuesta
    JP->>Cliente: Decisión final
