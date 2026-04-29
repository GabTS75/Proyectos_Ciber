# Responder

## Responder a futuros incidentes de seguridad

El plan de respuesta para futuros incidentes de denegación de servicio (**DoS**) o anomalías en la red se estructurará de la siguiente manera:

### **1. Contención y aislamiento**

- **Bloqueo perimetral inmediato:** Ante una alerta de inundación, el primer paso será ejecutar el bloqueo de todo el tráfico **ICMP** en el firewall externo para liberar el ancho de banda de la red interna.
- **Aislamiento de servicios:** Si el ataque se dirige a un servidor específico, se desconectará ese segmento de la red (VLAN) para evitar que la congestión afecte a otros departamentos (ej. separar diseño web de administración).
- **Desactivación de servicios “no críticos”:** Seguir el protocolo de poner fuera de línea servicios secundarios para priorizar los recursos del sistema hacia las operaciones críticas de la empresa.

### **2. Neutralización del incidente**

- **Filtrado dinámico:** Utilizar el IPS para identificar y bloquear automáticamente las direcciones IP de origen que estén generando el tráfico malicioso.
- **Limpieza de tráfico:** Una vez bloqueado el ataque, se reiniciarán los servicios de red de forma escalonada para asegurar que la carga vuelva a la normalidad sin picos de procesamiento.

### **3. Análisis de evidencias**

- **Revisión de logs:** Se analizarán los registros del **SIEM** y del Firewall para identificar patrones: *¿A qué hora exacta empezó? ¿Fue una sola IP o muchas (DDoS)? ¿Hubo algún intento de intrusión adicional aprovechando la distracción del DoS?*
- **Captura de paquetes:** Utilizar herramientas como `tcpdump` o Wireshark para analizar una muestra del tráfico capturado y verificar si el ataque ha evolucionado en complejidad.

### **4. Mejora Continua del Proceso**

- **Creación de "Playbooks":** Documentar este procedimiento paso a paso para que cualquier analista de turno sepa exactamente qué comandos ejecutar sin esperar instrucciones de la gerencia.
- **Comunicación:** Establecer un canal de comunicación rápida (como un grupo de alerta en Slack o Teams) para informar a los departamentos afectados en el minuto 1, reduciendo la incertidumbre.

---

> Reflexión:
> 
> 
> Fijémonos en esta fase de **Responder** por un momento, nos daremos cuenta de que la clave es tener un "guion" ya escrito. En el incidente que hemos experimentado, el equipo tuvo que "improvisar" hasta cierto punto, lo que nos llevó hasta esas 2 horas de caída (sin servicios). Con este plan, la respuesta se vuelve mecánica y mucho más rápida (más ágil).
>