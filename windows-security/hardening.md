# Windows Security Hardening

## Objetivo

El laboratorio incorpora diferentes medidas de endurecimiento (hardening) orientadas a reducir la superficie de ataque de los sistemas Windows y mejorar su capacidad de monitoreo y protección.

Las configuraciones se aplicaron en un entorno virtualizado y aislado de laboratorio.

## Controles implementados

### Políticas de contraseñas

Se configuró una política de contraseñas mediante Group Policy:

| Control | Configuración |
|---|---|
| Longitud mínima | 12 caracteres |
| Historial de contraseñas | 24 contraseñas |
| Umbral de bloqueo | 5 intentos fallidos |

Estas medidas buscan reducir el riesgo asociado al uso de contraseñas débiles o reutilizadas.

### Account Lockout

Se configuró el bloqueo de cuentas después de múltiples intentos de autenticación fallidos.

Este control permite:

- Reducir intentos repetitivos de autenticación.
- Generar eventos de seguridad para monitoreo.
- Facilitar la investigación de posibles ataques de fuerza bruta.

### Windows Firewall

Se revisó y configuró el firewall de Windows para controlar las comunicaciones del sistema y reducir exposiciones innecesarias.

Las pruebas de laboratorio permiten verificar que las reglas configuradas produzcan el comportamiento esperado.

### Servicios innecesarios

Se revisaron servicios de Windows que no eran necesarios para el escenario de laboratorio.

El objetivo fue reducir componentes innecesarios que pudieran ampliar la superficie de ataque.

### Auditoría de seguridad

Se habilitaron políticas de auditoría para aumentar la visibilidad sobre actividades relevantes del sistema.

Entre los eventos monitorizados se encuentran:

- Autenticaciones exitosas y fallidas.
- Bloqueos de cuentas.
- Creación de usuarios.
- Cambios en grupos de seguridad.
- Acceso a objetos.
- Actividad de PowerShell.

### PowerShell Logging

Se habilitaron mecanismos de registro relacionados con PowerShell para mejorar la visibilidad sobre la ejecución de scripts.

Se consideran especialmente relevantes:

- Event ID 4103
- Event ID 4104

Estos registros pueden utilizarse como fuente de información durante investigaciones de seguridad.

## Integración con Wazuh

Los controles de seguridad y eventos generados en Windows se integran con Wazuh para facilitar el monitoreo centralizado.

```text
Windows Security Controls
        ↓
Windows Event Logs
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Wazuh Dashboard
        ↓
Security Monitoring
