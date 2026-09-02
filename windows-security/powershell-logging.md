# PowerShell Logging

## Objetivo

Configurar mecanismos de registro de PowerShell para aumentar la visibilidad sobre la ejecución de scripts y facilitar el análisis de actividad administrativa y potencialmente sospechosa en el entorno Windows.

## Configuración

En el laboratorio se habilitaron mecanismos de registro de PowerShell mediante políticas y configuración del sistema.

El objetivo es obtener información adicional sobre la actividad ejecutada mediante PowerShell y disponer de evidencia para posteriores investigaciones.

## Eventos relevantes

### Event ID 4103 — PowerShell Module Logging

El evento 4103 proporciona información relacionada con la actividad de módulos de PowerShell.

Puede utilizarse como fuente de telemetría durante el análisis de actividad administrativa.

### Event ID 4104 — PowerShell Script Block Logging

El evento 4104 registra información relacionada con bloques de código ejecutados mediante PowerShell.

Este evento es especialmente útil para mejorar la visibilidad durante investigaciones de seguridad.

## Flujo de monitoreo

```text
PowerShell Activity
        ↓
Windows Event Logs
        ↓
Event ID 4103 / 4104
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Wazuh Dashboard
        ↓
Security Analysis
