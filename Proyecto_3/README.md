# Indicaciones del proyecto

## Objetivo

En esta actividad, estudiará un escenario en el que un cliente de la empresa para la que trabaja experimenta un problema de seguridad al acceder al sitio web de la empresa. Identificará la causa probable de la interrupción del servicio. A continuación, explicará cómo se produjo el ataque y el impacto negativo que tuvo en el sitio web.

En este curso, ha aprendido sobre varios ataques de red comunes. Ha aprendido sus nombres, cómo se llevan a cabo y las características de cada ataque desde la perspectiva del objetivo. Comprender cómo afectan los ataques a una red le ayudará a solucionar los problemas de la red de su organización. También le ayudará a tomar medidas para mitigar los daños y proteger una red de futuros ataques.

---

## Escenario

Revise el siguiente escenario. A continuación, complete las instrucciones paso a paso.

Usted trabaja como analista de seguridad para una agencia de viajes que anuncia ventas y promociones en el sitio web de la empresa. Los empleados de la empresa acceden regularmente a la página web de ventas de la empresa para buscar paquetes vacacionales que puedan gustar a sus clientes.

Una tarde, recibe una alerta automática de su sistema de supervisión que le indica un problema con el servidor web. Intenta visitar la página web de la empresa, pero recibe un mensaje de error de tiempo de espera de conexión en su navegador.

Utiliza un rastreador de paquetes para capturar los paquetes de datos en tránsito hacia y desde el servidor web. Observa un gran número de solicitudes TCP SYN procedentes de una dirección IP desconocida. El servidor web parece estar desbordado por el volumen de tráfico entrante y está perdiendo su capacidad para responder al número anormalmente elevado de peticiones SYN. Usted sospecha que el servidor está siendo atacado por un actor malicioso.

Usted desconecta temporalmente el servidor para que la máquina pueda recuperarse y volver a un estado operativo normal. También configura el cortafuegos de la empresa para que bloquee la dirección IP que estaba enviando el número anormal de peticiones SYN. Sabe que su solución de bloqueo de IP no durará mucho, ya que un atacante puede suplantar otras direcciones IP para burlar este bloqueo. Tiene que alertar rápidamente a su jefe sobre este problema y discutir los pasos a seguir para detener a este atacante y evitar que este problema se repita. Tendrá que estar preparado para contarle a su jefe el tipo de ataque que ha descubierto y cómo estaba afectando al servidor web y a los empleados.

---

## Instrucciones

Siga las instrucciones y responda a la pregunta para completar la actividad.

### Paso 1: Acceder a la plantilla

Para utilizar la plantilla para este elemento del curso, haga clic en el enlace siguiente:

[Cybersecurity-incident-report.pdf](docs/Cybersecurity-incident-report.pdf)

[Informe-de-incidente-de-Ciberseguridad.pdf](docs/Informe-de-incidente-de-Ciberseguridad.pdf)

---

### Paso 2: Acceso a los materiales de apoyo

Los siguientes materiales de apoyo te ayudarán a completar esta actividad. Manténgalos abiertos mientras continúa con los siguientes pasos.

Para utilizar los materiales de apoyo para este elemento del curso, haga clic en los siguientes enlaces:

- Registro TCP/HTTP de Wireshark:

    [TCP_HTTP-log.xlsx](docs/TCP_HTTP-log.xlsx)

- Cómo leer un registro TCP/HTTP de Wireshark:

    [How-to-read-a-Wireshark-TCP_HTTP-log.pdf](docs/How-to-read-a-Wireshark-TCP_HTTP-log.pdf)

    [Cómo-leer-un-registro-Wireshark-TCP_HTTP-log (resumen).pdf](docs/Como-leer-un-registro-Wireshark-TCP_HTTP-log_(resumen).pdf)

---

### Paso 3: Identificar el tipo de ataque causante de esta interrupción de la red

Reflexione sobre los tipos de ataques de intrusión en la red que ha conocido hasta ahora en este curso. Como analista de seguridad, identificar el tipo de ataque a la red en función del incidente es el primer paso para gestionar el ataque y prevenir ataques similares en el futuro.

He aquí algunas preguntas a tener en cuenta a la hora de determinar qué tipo de ataque se ha producido:

- ¿Qué entiende actualmente sobre los ataques a la red?
- ¿Qué tipo de ataque provocaría probablemente los síntomas descritos en el escenario?
- ¿Cuál es la diferencia entre una denegación de servicio (DoS) y una denegación de servicio distribuida (DDoS)?
- ¿Por qué el sitio web tarda mucho en cargarse e informa de un error de tiempo de espera de conexión?

Revise la lectura de Wireshark del paso 2 e intente identificar patrones en el tráfico de red registrado. Analice los patrones para determinar qué tipo de ataque de red se ha producido. Escriba su análisis en la sección uno de la plantilla de informe de incidentes de ciberseguridad proporcionada.

---

### Paso 4: Explicar cómo el ataque está provocando el mal funcionamiento del sitio web

Revise la lectura de Wireshark del paso 2 y, a continuación, escriba su análisis en la sección dos de la plantilla de Informe de Incidentes de Ciberseguridad que se proporciona.

Cuando redacte su informe, hable de los dispositivos y actividades de red implicados en la interrupción. Incluya la siguiente Información en su explicación:

- Describa el ataque. ¿Cuáles son los principales síntomas o características de este tipo específico de ataque?
- Explique cómo afectó a la red de la organización. ¿Cómo afecta este ataque específico a la red a la página web y a su funcionamiento?
- Describa las posibles consecuencias de este ataque y cómo afecta negativamente a la organización.
- *Opcional:* Sugiera posibles formas de asegurar la red para poder evitar este ataque en el futuro.

---

## Qué incluir en su respuesta

Asegúrese de abordar lo siguiente en su actividad completada:

- El nombre del ataque de intrusión en la red
- Una descripción de cómo el ataque afecta negativamente al rendimiento de la red.
