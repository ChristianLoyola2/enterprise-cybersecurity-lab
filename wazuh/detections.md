# Detecciones de Seguridad con Wazuh

## Objetivo

Definir y analizar casos de detección basados en eventos de seguridad generados dentro del laboratorio Windows y recopilados por Wazuh.

El objetivo es practicar la identificación de actividades potencialmente sospechosas y establecer un proceso básico de triage e investigación.

---

## 1. Múltiples intentos de autenticación fallida

### Evento de interés

**Event ID 4625 — An account failed to log on**

Este evento registra un intento de autenticación fallido en Windows.

### Indicadores de interés

Durante el análisis se consideran:

- Usuario afectado
- Equipo destino
- Origen de la actividad
- Marca temporal
- Cantidad de intentos
- Frecuencia de los eventos
- Existencia de autenticaciones exitosas posteriores

### Triage

Una secuencia aislada de eventos 4625 no necesariamente representa un ataque.

Se debe analizar:

```text
4625
 ↓
¿Es una actividad esperada?
 ↓
¿Hay múltiples intentos?
 ↓
¿Existe un patrón temporal?
 ↓
¿Provienen del mismo origen?
 ↓
¿Existe un 4624 posterior?
 ↓
Determinar necesidad de investigación
