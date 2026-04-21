# Análisis y desarrollo

Estamos ante uno de los ataques más famosos y efectivos de la capa de transporte (Capa 4): la **Inundación SYN (SYN Flood)**.

## 1. Entender el saludo

Antes de ver el ataque, miremos un momento las primeras líneas del archivo Excel (las filas que están en verde en la pestaña `Color coded TCP log`).

1. **Línea 47:** El cliente (`198.51.100.23`) envía un **[SYN]**. Es como si alguien llamara por teléfono y dijera "Hola, ¿podemos hablar?".
2. **Línea 48:** El servidor (`192.0.2.1`) responde con **[SYN, ACK]**. "Hola, sí podemos, estoy listo".
3. **Línea 49:** El cliente responde **[ACK]**. "Genial, empecemos".
4. **Líneas 50-51:** Se intercambian datos (**HTTP GET** y **200 OK**). La web de viajes carga perfectamente.

**Esto es lo que debería pasar siempre.** Es el famoso saludo de tres vías (three-way handshake).

---

## 2. Identificando el ataque

Ahora veamos a partir de la **línea 52** (en rojo). Aquí es donde la cosa se pone fea:

- Aparece una IP desconocida: `203.0.113.0`.
- Empieza a enviar paquetes **[SYN]** uno tras otro, muy rápido (mira la columna de tiempo, ocurren en milisegundos).
- **¿Qué está haciendo el atacante?:** Este envía el "Hola, ¿podemos hablar?", pero cuando el servidor responde "Sí, estoy listo", el atacante **se queda callado** (no envía el tercer paso, el **ACK**).

> **Analogía:** Es como si miles de personas llamaran a la agencia de viajes al mismo tiempo, tú contestas el teléfono, pero nadie habla al otro lado. Te quedas con el auricular en la mano esperando, y mientras tanto, las otras líneas siguen sonando. Al final, no puedes atender a los clientes reales porque todas tus "manos" (recursos del servidor) están ocupadas sosteniendo teléfonos en silencio.

---

## 3. Redactamos el informe

Utilizo la plantilla con el siguiente análisis.

### Sección 1: Identificar el ataque

- **Explicación del "timeout":** El error de tiempo de espera ocurre porque el servidor ha llenado su "memoria de espera" (llamada cola de conexiones semiabiertas). Como está esperando respuestas que nunca llegan del atacante, no tiene espacio para aceptar nuevas peticiones de los empleados.
- **Los registros muestran:** Una cantidad enorme de paquetes con la bandera **[SYN]** provenientes de la IP `203.0.113.0` hacia el puerto **443** del servidor, sin que se completen las conexiones.
- **Tipo de evento:** Este es un ataque de **Denegación de Servicio (DoS)**, específicamente una **Inundación SYN (SYN Flood)**.

### Sección 2: El impacto en el servidor

- **El saludo de tres vías (explicación sencilla):**
    1. **SYN:** El cliente pide conectar.
    2. **SYN-ACK:** El servidor reserva recursos y dice que sí.
    3. **ACK:** El cliente confirma y se abre la sesión.
- **Qué hace el atacante:** Envía miles de `SYN` pero ignora los `SYN-ACK`, dejando al servidor "colgado" esperando el `ACK`.
- **Efecto en el servidor:** Los registros muestran que el servidor se satura. Los empleados legítimos (marcados en amarillo en tu log) intentan conectar, pero el servidor ya no puede responderles o tarda tanto que el navegador se rinde y da el error de "timeout".

---

## 4. Recomendaciones

Como analista de seguridad, también puedo sugerir qué hacer:

1. **SYN Cookies:** Es una técnica que permite al servidor no reservar memoria hasta que la conexión sea realmente legítima. Es como no levantar el teléfono hasta que estés seguro de que alguien va a hablar.
2. **Reducir el tiempo de espera (Timeout):** Hacer que el servidor deje de esperar el tercer paso más rápido para liberar recursos.
3. **Sistemas de detección de intrusos (IDS/IPS):** Para que el cortafuegos detecte automáticamente este patrón de "muchos SYN de una sola IP" y lo bloquee antes de que sature al servidor.

[Informe-DoS-SYN-Flood-Gabriel-Ternero.pdf](docs/Informe-DoS-SYN-Flood-Gabriel-Ternero.pdf)

✨🫵😎
