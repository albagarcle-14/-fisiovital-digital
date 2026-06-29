# Informe de Incidencia — INC-001

## Detalles de la incidencia
- **Código:** INC-001
- **Fecha y Hora:** 23 de junio de 2026, 23:15 CEST
- **Módulo afectado:** Pipeline CI/CD (DevOps) y Base de Datos (Backend)
- **Impacto:** Alto (Bloqueo temporal del despliegue automatizado en el entorno de pruebas)

## Análisis de Causa Raíz (RCA)
El pipeline de integración continua falló durante la ejecución de las pruebas automatizadas debido a un error de compilación. La causa raíz fue una **discrepancia de versiones en la librería de cifrado**: el equipo de Backend actualizó la versión local para cumplir con los requerimientos estrictos de protección de datos del RGPD, pero el entorno de contenedores en la nube de DevOps ejecutaba una versión antigua desactualizada, provocando una incompatibilidad crítica.

## Plan de Acción y Resolución
1. **Contención inmediata:** Identificación del log de error en el pipeline y aislamiento de la rama de desarrollo afectada.
2. **Corrección técnica:** Actualización de la imagen del contenedor del servidor de integración en la nube para emparejar la versión de la librería de cifrado con la del Backend.
3. **Validación:** Reejecución forzada del pipeline, confirmando el paso correcto de los tests y el despliegue exitoso (Pipeline en verde).

## Diagrama de flujo de resolución
```mermaid
flowchart TD
    A[Fallo en Pipeline CI/CD] --> B{Análisis de Logs}
    B -->|Incompatibilidad Librería Cifrado| C[Actualizar imagen de contenedor en la nube]
    B -->|Otro motivo| D[Escalar a desarrollo Backend]
    C --> E[Reejecutar Pipeline automatizado]
    E --> F{¿Pipeline en verde?}
    F -->|Sí| G[Incidencia Cerrada / Entorno funcional]
    F -->|No| B

---

### Paso 2: Guardar el archivo (Commit)
1. Haz clic arriba a la derecha en el botón verde **`Commit changes...`**.
2. En el recuadro del mensaje escribe exactamente: 
   ```text
   docs(ejecucion): documentar informe de incidencia INC-001
