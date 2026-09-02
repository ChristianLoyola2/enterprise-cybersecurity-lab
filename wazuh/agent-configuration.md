# Configuración del Wazuh Agent

## Objetivo

El Wazuh Agent se utiliza en los endpoints Windows del laboratorio para recopilar información del sistema y eventos de seguridad y enviarlos al Wazuh Manager.

## Endpoint monitoreado

El laboratorio incluye un equipo Windows 10 Pro configurado con Wazuh Agent.

### Función

El endpoint permite generar y recopilar telemetría relacionada con:

- Eventos de seguridad de Windows
- Autenticaciones
- Fallos de autenticación
- Cambios en cuentas
- Cambios en grupos
- Bloqueos de cuentas
- Actividad de PowerShell
- Información del sistema

## Arquitectura

```text
Windows 10 Pro
      │
      │ Wazuh Agent
      │
      ▼
Wazuh Manager
      │
      ▼
Wazuh Indexer
      │
      ▼
Wazuh Dashboard
