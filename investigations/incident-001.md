# Incidente 001 — Múltiples autenticaciones fallidas

## 1. Resumen

Se realizó una investigación sobre una serie de eventos de autenticación fallida registrados en un sistema Windows del laboratorio.

El objetivo fue practicar el proceso de identificación, validación y análisis de eventos de seguridad mediante Wazuh SIEM.

## 2. Entorno

- Windows Server 2022
- Windows 10 Pro
- Active Directory
- Wazuh SIEM
- Ubuntu Server
- Kali Linux
- VirtualBox

> La actividad fue realizada en un entorno de laboratorio aislado.

## 3. Detección

**Evento:** 4625 — Failed Logon

La detección se basa en eventos de autenticación fallida registrados por Windows y recopilados mediante Wazuh.

### Fuente

```text
Windows Security Event Log
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Wazuh Dashboard
