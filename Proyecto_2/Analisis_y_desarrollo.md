# Análisis para el desarrollo del proyecto

## Análisis de la comunicación en la capa de red

Vamos a desglosar este incidente paso a paso para que se logre entender la "historia" que cuentan esos datos.

## Paso 1: Interpretación (Análisis de Logs)

Viendo la imagen que nos muestra `tcpdump`., considero que un analista siempre debe leer primero el registro completamente o siguiendo la línea de tiempo.

1. **La Petición (Request):** El equipo (`192.51.100.15`) intenta hablar con el servidor DNS (`203.0.113.2`) en el puerto `53` (dominio) usando **UDP** para preguntar: *"¿Cuál es la IP de yummyrecipesforme.com?"*.
2. **El Problema:** El servidor responde con un paquete **ICMP**. En redes, ICMP es como el "mensajero" que trae buenas o malas noticias, malas en este caso.
3. **El Error:** El mensaje dice `udp port 53 unreachable`. Esto significa que el servidor está ahí, pero el "negocio" (el servicio DNS) está cerrado o no acepta clientes en esa puerta.

---

## Paso 2: Desarrollo del informe (Parte 1)

Ahora rellenamos la primera parte del **Cybersecurity Incident Report** cogiendo los datos técnicos.

### Parte 1: Resumen del problema en el registro DNS e ICMP

- **El protocolo UDP revela que:** El cliente intentó realizar consultas DNS repetidas para el dominio `yummyrecipesforme.com` hacia el servidor `203.0.113.2`.
- **Esto se basa en los resultados del análisis de red, que muestran que la respuesta de ICMP devolvió el mensaje de error:** `udp port 53 unreachable`.
- **El puerto anotado en el mensaje de error se utiliza para:** Servicios de resolución de nombres de dominio (DNS).
- **El problema más probable es:** El servicio DNS en el servidor de destino no está activo, o hay un firewall bloqueando específicamente el acceso al puerto 53, lo que impide la resolución del nombre de dominio y, en consecuencia, el acceso al sitio web.

---

## Paso 3: Análisis y origen (Parte 2)

Analicemos un poco.

### Parte 2: Análisis de datos y causa del incidente

- **Hora del incidente:** El primer evento registrado ocurrió a las **13:24:32** y continuó con reintentos hasta las **13:28:50**.
- **Cómo se detectó:** A través de reportes de clientes que no podían acceder a la web y la confirmación del analista mediante el error de navegador "puerto de destino inalcanzable".
- **Acciones de investigación:** Se utilizó la herramienta de línea de comandos `tcpdump` para capturar el tráfico de red mientras se intentaba cargar el sitio web, permitiendo ver los paquetes en tránsito.
- **Hallazgos clave:** Se identificó que las solicitudes salientes viajan correctamente, pero el servidor DNS (`203.0.113.2`) rechaza las conexiones UDP en el puerto 53 mediante mensajes de error ICMP.
- **Causa probable:** Una caída del servicio DNS en el servidor o una configuración incorrecta en las reglas de filtrado (firewall) del lado del servidor que ha dejado el puerto 53 como "inalcanzable".

---

[Informe-de-incidente-de-ciberseguridad-Análisis-de-tráfico-de-red.pdf (Gabriel Ternero)](pdf/Informe-Gabriel-Ternero.pdf)