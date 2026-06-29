# Estrategia de despliegue — FisioVital Digital

## Entornos
| Entorno | Propósito | Proveedor / Región |
|---|---|---|
| Desarrollo | Integración de ramas locales de desarrollo y tests unitarios iniciales. | Local / Entornos de desarrollo aislados |
| Pre-producción | Entorno idéntico a producción para el control de calidad (QA) y validación del cliente. | AWS (Europa / Fráncfort) |
| Producción | Entorno final en vivo con alta disponibilidad y cifrado médico para pacientes reales. | AWS (Europa / Fráncfort) |

## Pipeline CI/CD
```mermaid
flowchart LR
    A[Push a rama] --> B[Tests automáticos]
    B --> C[Build]
    C --> D[Despliegue a pre-producción]
    D --> E{Validación manual}
    E -->|OK| F[Despliegue a producción]
    E -->|KO| G[Rollback]
Estrategia de despliegue a producción
El paso de Pre-producción a Producción se realiza mediante una promoción controlada por un "Deployment Gate" que requiere la firma y aprobación manual del Jefe de Proyecto tras el visto bueno de QA. En caso de detectarse fallos en caliente tras el lanzamiento, se activa una estrategia de Rollback automatizado mediante contenedores inmutables (Rollback a la última imagen Docker estable) para restaurar el servicio en menos de 2 minutos.

Lección aplicada tras INC-001
Para mitigar por completo el riesgo de caídas por discrepancias en módulos críticos (como el cifrado RGPD), se incorpora una fase de validación estricta de versiones (lockfiles y escaneo de dependencias) en la etapa de Tests automáticos. Si existe una incompatibilidad de versiones entre el entorno de contenedores y el software de desarrollo, el pipeline bloqueará el despliegue antes de alterar el servidor.

Checklist de salida a producción
[ ] Pasar el 100% del plan de pruebas funcionales y de seguridad de QA en Pre-producción.

[ ] Ejecutar congelación de versiones (Dependency Lock) verificando compatibilidad de contenedores Docker.

[ ] Confirmar alta operativa del servicio SMTP externo para el envío de recordatorios (CR-001).

[ ] Realizar una copia de seguridad (Backup) en frío de la base de datos médica cifrada.


---

### Paso 2: Guardar el archivo (Commit y Push automático)

1. Haz clic en el botón verde **`Commit changes...`** arriba a la derecha.
2. En el recuadro del mensaje del commit, escribe exactamente el texto solicitado:
   ```text
   docs(ejecucion): estrategia de despliegue y pipeline CI/CD
