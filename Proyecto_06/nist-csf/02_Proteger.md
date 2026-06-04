# Proteger

## Protegiendo los activos de la organización

Para proteger mejor los activos de la organización y asegurar que la red interna no vuelva a ser vulnerable a un ataque de inundación ICMP, he definido los siguientes sistemas y procedimientos a actualizar:

### **1. Configuración avanzada del Firewall (Control Técnico)**

- **Limitación de tasa (Rate Limiting):** Se ha implementado una regla que limita la cantidad de paquetes ICMP que el firewall permite por segundo. Esto evita que un volumen masivo de pings sature el ancho de banda.
- **Verificación de IP de origen (Anti-spoofing):** El firewall ahora verificará que las direcciones IP de origen sean legítimas. Esto impide que los atacantes usen direcciones falsificadas para ocultar su rastro o amplificar el ataque.

### **2. Despliegue de sistemas de seguridad activa (Control Técnico)**

- **Sistema de Prevención de Intrusiones (IPS):** A diferencia de solo detectar, el IPS actuará bloqueando automáticamente el tráfico que coincida con patrones sospechosos de un ataque **DoS** en tiempo real.

### **3. Endurecimiento de la Red (Hardening de procedimientos)**

- **Política de "Denegación por Defecto":** Se revisarán las reglas del firewall para asegurar que solo el tráfico estrictamente necesario esté permitido. Si el protocolo ICMP no es vital para una operación externa, se mantendrá restringido.
- **Gestión de Configuración:** Se establecerá una "Línea Base" de configuración para todos los dispositivos de red, asegurando que ningún firewall se ponga en marcha sin las reglas de protección mínimas.

---

> **Reflexión:**
> 
> 
> En este paso de **Proteger**, considero que no solo instalar software (IDS/IPS) basta, sino que también se propone realizar cambios en los **procedimientos** (la política de denegación por defecto). Esto es vital porque la tecnología por sí sola puede fallar (no hay software perfecto) si no hay una regla o política que la respalde.
>