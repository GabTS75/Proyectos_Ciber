# Recuperar

## Recuperación del incidente

En este paso de **Recuperar**, es la parte en la que se trata de volver a la "normalidad" y asegurarnos de que la empresa sea más **resiliente** que antes. En un ataque **DoS**, a diferencia de un **ataque de malware** donde se borran datos, la recuperación se centra en la **disponibilidad** y la **confianza**.

El objetivo de esta fase es restaurar las capacidades o servicios que resultaron afectados por el incidente de manera segura y eficiente.

### **1. Información y sistemas a recuperar inmediatamente**

- **Disponibilidad de servicios críticos:** La prioridad absoluta es garantizar que el ancho de banda de la red interna esté al 100% para que los equipos de **diseño web y gráfico** puedan acceder a sus servidores de archivos y herramientas en la nube.
- **Conectividad del cliente:** Restaurar el acceso a las soluciones de **marketing en redes sociales** y portales de clientes que pudieron haber experimentado tiempos de espera o errores durante las dos horas del ataque.
- **Integridad de los datos de red:** Aunque un ataque **DoS** no suele borrar datos, se debe verificar que las tablas de enrutamiento y las configuraciones de los servidores no quedaron corruptas debido a la saturación de memoria durante la inundación.

### **2. Procesos de recuperación**

- **Restauración escalonada:** No se encenderán todos los servicios a la vez. Seguiremos un orden de prioridad: 1ro. Infraestructura base (DNS, Gateway), 2do. Servicios de cara al cliente, 3ro. Herramientas internas de diseño.
- **Verificación de seguridad post-incidente:** Antes de dar el incidente por "cerrado", el equipo de seguridad realizará pruebas de estrés controladas para asegurar que las nuevas reglas de limitación de tasa (rate limiting) en el firewall funcionan sin bloquear a los usuarios legítimos.
- **Comunicación con los interesados (Stakeholders):** Se enviará un comunicado interno a los empleados explicando que los sistemas están operativos y, si es necesario, una breve nota profesional a los clientes clave asegurando que sus datos nunca estuvieron en riesgo y que la estabilidad ha sido restablecida.

### **3. Mejora continua:**

- **Actualización del plan de continuidad:** Los tiempos de respuesta observados (2 horas) se utilizarán para ajustar los objetivos de tiempo de recuperación (**RTO**) en futuros planes.

---

> **Reflexión:**
> 
> 
> En este caso en particular, la acción de "recuperar" es sinónimo de "volver a producir". Como analista, el éxito de este paso se mide en lograr que rápidamente el equipo de diseño pueda volver a abrir sus aplicaciones de **Adobe** o **Figma** y seguir trabajando sin notar lentitud.
>