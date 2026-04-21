# Análisis para el desarrollo de este proyecto

## Análisis de la comunicación en la capa de red

Desglosaré este incidente paso a paso para que se entienda mejor la "historia" que cuentan esos datos.

## Introducción

En este ejercicio, me puse en los zapatos de un analista de seguridad para investigar un problema real: varios usuarios no podían entrar a la web `www.yummyrecipesforme.com`.
Mi objetivo fue "escuchar" la red para entender en qué punto de la comunicación se estaba rompiendo el flujo de datos.

---

### Parte 1: Resumen del problema (Lo que dicen los datos)

Al analizar los registros (logs) de la comunicación, esto es lo que encontré:

- **El protocolo UDP nos cuenta que:** El ordenador intentó varias veces preguntarle al servidor DNS (en la dirección `203.0.113.2`) cuál era la dirección "física" (IP) de la web.
- **Sabemos que algo falló porque:** En lugar de recibir la respuesta con la dirección IP, el servidor nos mandó de vuelta un mensaje de error ICMP que decía: `udp port 53 unreachable` (udp puerto 53 inalcanzable).
- **¿Para qué sirve ese puerto?:** El puerto 53 es como la "ventanilla" específica donde se atienden las consultas de nombres de dominio (DNS).
- **Mi conclusión inicial:** El servidor está encendido y nos escucha, pero la "ventanilla" del servicio DNS está cerrada. Por eso la web no carga: no podemos traducir el nombre a una dirección IP.

---

### Parte 2: Mi análisis y el origen del incidente

Aquí explico cómo llegué a estas conclusiones y qué fue lo que pasó:

- **¿Cuándo pasó?:** Todo empezó a las **13:24:32**, según las marcas de tiempo de los registros.
- **¿Cómo nos enteramos?:** Los clientes empezaron a quejarse de que la página tardaba mucho en cargar y al final les salía un error de "puerto inalcanzable". Yo mismo lo comprobé al intentar entrar.
- **¿Qué hice para investigar?:** Usé una herramienta llamada `tcpdump`. Lo que hace es capturar los paquetes de datos que viajan por el cable (o por el aire) para que podamos leerlos. Intenté entrar a la web mientras la herramienta estaba encendida para ver el tráfico en vivo.
- **Descubrimientos clave:**
    1. Mis peticiones de ayuda (paquetes UDP) salieron bien de mi ordenador.
    2. El servidor de destino respondió, pero lo hizo con un error ICMP.
    3. Esto confirma que no es un problema de mi conexión, sino de la "otra parte".
- **Causa más probable:** Creo que el servicio que se encarga de los nombres (DNS) se ha caído en el servidor de destino, o quizás alguien configuró mal el muro de seguridad (firewall) y bloqueó ese puerto por error.

---

## Conclusiones

Este ejercicio me ayudó a entender que la red no solo envía datos, sino también "mensajes de error" (**ICMP**) que son como pistas para los analistas.
Comprendí que se debe *aprender a leer estas pistas*, ya que esto es la diferencia entre "adivinar qué pasa" y "saber exactamente dónde está el problema".

[Informe-Análisis-de-tráfico-de-red.pdf (Gabriel Ternero)](docs/Informe-Gabriel-Ternero.pdf)

😉👍
