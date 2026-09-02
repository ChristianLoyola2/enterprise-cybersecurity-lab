# Arquitectura de Wazuh SIEM

## Objetivo

Wazuh se utiliza como plataforma de monitoreo de seguridad y SIEM dentro del laboratorio para centralizar eventos provenientes de los sistemas Windows y facilitar su análisis.

## Componentes

El entorno de monitoreo está compuesto por:

| Componente | Función |
|---|---|
| Wazuh Agent | Recopila información y eventos del endpoint |
| Wazuh Manager | Recibe, analiza y gestiona los datos de seguridad |
| Wazuh Indexer | Almacena y permite consultar los datos procesados |
| Wazuh Dashboard | Proporciona la interfaz para visualizar y analizar la información |

## Arquitectura del laboratorio

```text
                ┌─────────────────────────┐
                │     Windows Server      │
                │        2022             │
                │                         │
                │ Active Directory        │
                │ DNS / GPO               │
                │ Security Events         │
                └────────────┬────────────┘
                             │
                             │
                ┌────────────▼────────────┐
                │      Windows 10         │
                │                         │
                │ Wazuh Agent             │
                │ Windows Event Logs       │
                └────────────┬────────────┘
                             │
                             │
                    Security Events
                             │
                             ▼
                ┌─────────────────────────┐
                │      Wazuh Manager      │
                │                         │
                │ Analysis / Management   │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │     Wazuh Indexer       │
                │                         │
                │ Security Data Storage   │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │    Wazuh Dashboard      │
                │                         │
                │ Visualization / Search  │
                └─────────────────────────┘

                    Kali Linux
               Controlled Testing
