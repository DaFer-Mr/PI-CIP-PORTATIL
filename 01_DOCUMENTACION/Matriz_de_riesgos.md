# Matriz de Riesgos — Sistema CIP Portátil

Matriz de identificación, evaluación, mitigación y contingencia de riesgos del proyecto.

| ID | Riesgo | Probabilidad | Impacto | Plan de Mitigación | Plan de Contingencia |
|---|---|---|---|---|---|
| R-01 | Ruido electromagnético en la señal del PT100 debido al motor de la bomba | Media | Alto | Uso de transmisor 4–20 mA, cableado blindado y par trenzado. Separar físicamente señal y potencia. | Implementar filtrado en PLC y/o reubicar el sensor/cableado respecto al motor. |
| R-02 | Sobrecalentamiento de la resistencia por marcha en seco debido a fallo del flotador | Baja | Alto | Interbloqueo físico mediante contactor para cortar la alimentación de la resistencia y lógica del PLC que verifique nivel antes de activar el SSR. | Detener inmediatamente el calentamiento, reemplazar el flotador y verificar el circuito de seguridad antes de reanudar operación. |
| R-03 | Inestabilidad en la comunicación MQTT por latencia o pérdida de paquetes | Media | Medio | Utilizar QoS 1 y almacenamiento/buffer local en Node-RED para conservar datos durante interrupciones. | Mantener el control del proceso de forma local en el PLC y realizar reconexión automática del sistema de comunicación. |
| R-04 | Constante de tiempo térmica mayor a la esperada (τ > 10 min) | Media | Medio | Utilizar recirculación forzada mediante la bomba P-101 para mejorar la convección y reducir la constante de tiempo efectiva. | Reducir el volumen operativo a 15 L y evaluar el incremento de potencia de la resistencia si las condiciones eléctricas lo permiten. |
| R-05 | Falla en la dosificación de jabón por obstrucción de la bomba peristáltica | Media | Medio | Realizar mantenimiento preventivo y verificar periódicamente la manguera de silicona y el sistema de dosificación. | Incorporar un sensor de caudal en la línea de dosificación para detectar ausencia de flujo y generar una alarma. |
| R-06 | Daño del sensor de flujo YF-S201 debido a golpe de ariete | Baja | Medio | Instalar válvula de retención y elemento de amortiguación de presión en la línea hidráulica. Evitar cierres bruscos de válvulas. | Detener el proceso, reemplazar el sensor y verificar las condiciones de presión antes de volver a operar. |

## Notas técnicas

- Para R-01, el transmisor 4–20 mA se considera más robusto frente a interferencias electromagnéticas que una señal de milivoltios del PT100, pero no es completamente inmune al ruido.
- Para R-02, la protección contra marcha en seco debe contemplar una desconexión física de la potencia de calentamiento independiente de la lógica normal del PLC.
