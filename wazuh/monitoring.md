# Monitoreo de Seguridad con Wazuh

## Objetivo

El laboratorio utiliza Wazuh para centralizar, visualizar y analizar eventos de seguridad generados principalmente por los sistemas Windows del entorno.

El objetivo es desarrollar capacidades de Security Monitoring, análisis de logs y detección de actividad potencialmente sospechosa.

## Fuentes de información

Las principales fuentes monitorizadas incluyen:

- Windows Security Event Logs
- Eventos de autenticación
- Bloqueos de cuentas
- Creación de usuarios
- Cambios en grupos de seguridad
- Acceso a objetos auditados
- Actividad de PowerShell
- Información del sistema y del endpoint

## Eventos de interés

| Evento | Actividad |
|---|---|
| 4624 | Inicio de sesión exitoso |
| 4625 | Inicio de sesión fallido |
| 4740 | Bloqueo de cuenta |
| 4720 | Creación de cuenta de usuario |
| 4728 | Adición de un miembro a un grupo global habilitado para seguridad |
| 4729 | Eliminación de un miembro de un grupo global habilitado para seguridad |
| 4663 | Acceso a un objeto |
| 4103 | Registro de módulos de PowerShell |
| 4104 | Registro de bloques de script de PowerShell |

## Flujo de monitoreo

```text
Actividad en Endpoint
        ↓
Windows Event Logs
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Procesamiento y análisis
        ↓
Wazuh Indexer
        ↓
Wazuh Dashboard
        ↓
Monitoreo de seguridad
