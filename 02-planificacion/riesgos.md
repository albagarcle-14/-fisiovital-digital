# Plan de gestión de riesgos — FisioVital Digital

A continuación se detalla el análisis de riesgos del proyecto, abarcando las dimensiones técnicas, operativas y normativas identificadas por el equipo para el despliegue en las 5 clínicas.

| ID | Riesgo | Categoría | Probabilidad | Impacto | Respuesta |
|---|---|---|---|---|---|
| **R1** | Retraso en la integración/simulación con aseguradoras médicas externas. | Técnico | Alta | Alta | **Mitigar:** Diseñar *mocks* (simulaciones) estáticos en la semana 4 para que Frontend avance sin depender del sistema real de los seguros. |
| **R2** | Complejidad técnica en el cifrado y protección de los historiales clínicos según el RGPD. | Técnico | Media | Alta | **Mitigar:** Utilizar librerías de cifrado estándar y validadas por la industria en el backend desde el primer día de desarrollo. |
| **R3** | Cuellos de botella en QA por cambios imprevistos en el contrato de la API a mitad del desarrollo. | QA | Media | Media | **Prevenir:** Congelar el contrato OpenAPI tras la primera semana y requerir aprobación de todo el equipo para cualquier modificación. |
| **R4** | Caída del servidor centralizado en la UE provocando la parada del servicio en las 5 clínicas. | DevOps | Baja | Alta | **Mitigar:** Configurar un pipeline de backups automáticos cada hora con réplica en una región secundaria europea. |
| **R5** | Desbordamiento del alcance inicial por peticiones de última hora del cliente (ej. App móvil o pagos online). | Alcance | Alta | Media | **Aceptar/Acotar:** Remitir explícitamente al Project Charter. Cualquier extra se moverá obligatoriamente a una "Fase 2" post-lanzamiento. |
| **R6** | Sanciones legales graves e interrupción del negocio por almacenar datos de salud fuera de la Unión Europea. | Normativo | Baja | Crítica | **Prevenir:** Auditoría obligatoria en el script de despliegue de DevOps para bloquear regiones de hosting que no sean `eu-west` o similares. |
| **R7** | Resistencia al cambio o rechazo del sistema por parte de las 8 recepcionistas debido a una interfaz compleja. | Equipo/Recursos | Media | Alta | **Mitigar:** Involucrar a una recepcionista en las pruebas de usabilidad de Frontend en la semana 6 y realizar 5 días de capacitación al cierre. |
| **R8** | Cuello de botella o parada del proyecto si el único desarrollador Backend o Frontend causa baja médica. | Equipo/Recursos | Baja | Alta | **Mitigar:** Mantener el código documentado diariamente en las ramas de Git y realizar reuniones de sincronización (*dailies*) de 10 minutos. |
