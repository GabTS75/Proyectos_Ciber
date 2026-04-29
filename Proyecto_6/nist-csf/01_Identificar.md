# Identificar

## Identificar el tipo de ataque y los sistemas afectados

### **Tipo de ataque**

El ataque identificado es una **Denegación de Servicio (DoS)**, específicamente mediante una **Inundación ICMP (ICMP Flood)**. El atacante aprovechó el protocolo ICMP (usado normalmente para diagnósticos de red como el `ping`) para enviar una cantidad abrumadora de solicitudes que saturaron la capacidad de procesamiento de la red.

### **Sistemas afectados**

1. **Cortafuegos (Firewall):** Fue el punto de entrada y el sistema que falló debido a una configuración de seguridad inexistente o deficiente que permitía el paso ilimitado de paquetes ICMP.
2. **Infraestructura de Red Interna:** Los switches y routers se vieron saturados por el volumen de tráfico, lo que impidió que el tráfico legítimo de los empleados circulara con normalidad.
3. **Servicios de Producción:** Los servidores y herramientas dedicados al **diseño web, diseño gráfico y soluciones de marketing** quedaron inaccesibles, paralizando el trabajo de la organización.
4. **Disponibilidad de Recursos:** Se vio afectada la tríada de la seguridad (Confidencialidad, Integridad y Disponibilidad), específicamente el pilar de la **Disponibilidad**.

---

> **Reflexión:**
> 
> 
> Es importante notar que, aunque el "arma" fue el ICMP, el **riesgo real identificado** fue la falta de una auditoría previa en las reglas del firewall. En un entorno profesional, esto nos indica que el activo más vulnerable no era solo la red, sino nuestro proceso de gestión de configuraciones.
>