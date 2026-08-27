# Sistema CIP Portátil Automatizado

## Clean-In-Place (CIP)

Proyecto de diseño y desarrollo de un sistema CIP portátil automatizado orientado a la limpieza de equipos y sistemas de proceso sin necesidad de desmontaje.

---

## 📌 Descripción del proyecto

El proyecto consiste en el desarrollo de un sistema **Clean-In-Place (CIP) portátil**, diseñado para realizar procesos de limpieza de manera controlada, repetible y segura.

El sistema integra elementos mecánicos, hidráulicos, eléctricos, de instrumentación y automatización para controlar las diferentes etapas del proceso de limpieza.

El proyecto contempla el diseño, construcción, automatización, integración y validación experimental del sistema.

---

## 🎯 Objetivo general

Diseñar y desarrollar un sistema CIP portátil automatizado capaz de ejecutar ciclos de limpieza controlados mediante variables de proceso como temperatura, tiempo, caudal y otras variables relevantes para el proceso.

---

## ⚙️ Alcance

El proyecto contempla:

- Diseño conceptual y de detalle del sistema.
- Diseño mecánico y estructural.
- Diseño del circuito hidráulico.
- Diseño eléctrico y de control.
- Selección e integración de sensores y actuadores.
- Automatización del ciclo CIP.
- Implementación del sistema de supervisión.
- Comunicación entre los diferentes dispositivos.
- Desarrollo de la interfaz HMI.
- Implementación de monitoreo mediante software.
- Elaboración de protocolos de prueba.
- Validación experimental del sistema.
- Documentación técnica del proyecto.

---

## 🧩 Arquitectura general

El sistema estará compuesto por diferentes subsistemas:

```text
                    ┌─────────────────────┐
                    │      USUARIO        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     HMI / SCADA     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   CONTROLADOR PLC   │
                    └──────────┬──────────┘
                               │
                ┌──────────────┼──────────────┐
                │              │              │
                ▼              ▼              ▼
           Sensores        Actuadores     Comunicaciones
                │              │              │
                └──────────────┼──────────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   SISTEMA HIDRÁULICO│
                    │         CIP         │
                    └─────────────────────┘
