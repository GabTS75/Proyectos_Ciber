# Indicaciones del proyecto

## Objetivo

En esta actividad, asumirás el papel de un analista de ciberseguridad que trabaja para una empresa que aloja el sitio web de cocina, [yummyrecipesforme.com](http://yummyrecipesforme.com/). Los visitantes del sitio web experimentan un problema de seguridad al cargar la página web principal. Tu trabajo consiste en investigar, identificar, documentar y recomendar una solución al problema de seguridad.

Cuando investigue el evento de seguridad, revisará un registro `tcpdump`. Tendrás que identificar los Protocolos de red utilizados para establecer la conexión entre el usuario y la página web. Los Protocolos de red son las reglas y estándares de comunicación que los dispositivos en red utilizan para transmitir datos. Desafortunadamente, los actores maliciosos también pueden utilizar protocolos de red para invadir y atacar redes privadas. Saber identificar los protocolos utilizados habitualmente en los ataques le ayudará a proteger la red de su organización contra este tipo de eventos de seguridad.

Para completar la tarea, también tendrá que documentar lo que ocurrió durante el incidente de seguridad y seguidamente, recomendar una medida de seguridad para prevenir problemas de seguridad similares en el futuro.

---

## Escenario

Revise el escenario que aparece a continuación. Luego complete las instrucciones paso a paso.

Usted es un analista de ciberseguridad para yummyrecipesforme.com, un sitio web que vende recetas y libros de cocina. Un antiguo empleado ha decidido atraer a los usuarios a un sitio web falso con malware.

El antiguo empleado/hacker ejecutó un ataque de fuerza bruta para obtener acceso al host web. Introdujeron repetidamente varias contraseñas predeterminadas conocidas para la cuenta administrativa hasta que acertaron con la correcta. Una vez obtenidas las credenciales de inicio de sesión, pudieron acceder al panel de administración y cambiar el código fuente del sitio web. Incrustaron una función javascript en el código fuente que pedía a los visitantes que descargaran y ejecutaran un archivo al visitar el sitio web. Después de incrustar el programa malicioso, el hacker cambió la contraseña de la cuenta administrativa. Cuando los clientes descargaban el archivo, eran redirigidos a una versión falsa del sitio web que contenía el programa malicioso.

Varias horas después del ataque, varios clientes enviaron correos electrónicos al servicio de asistencia de yummyrecipesforme. Se quejaban de que el sitio web de la empresa les había incitado a descargar un archivo para acceder a recetas gratuitas. Los clientes afirmaron que, tras ejecutar el archivo, la dirección del sitio web cambió y sus ordenadores personales empezaron a funcionar más lentamente.

En respuesta a este incidente, el propietario del sitio web intenta acceder al panel de administración, pero no lo consigue, por lo que se pone en contacto con el proveedor de alojamiento del sitio web. Usted y otros analistas de Ciberseguridad reciben el encargo de investigar este incidente de seguridad.

Para abordar el incidente, creas un entorno sandbox para observar el comportamiento sospechoso del sitio web. Ejecutas el analizador de protocolos de red `tcpdump` y escribes la URL del sitio web, yummyrecipesforme.com. En cuanto se carga el sitio web, se le pide que descargue un archivo ejecutable para actualizar su navegador. Aceptas la descarga y dejas que se ejecute el archivo. Entonces observa que su navegador le redirige a una URL diferente, greatrecipesforme.com, que contiene el malware.

Los registros muestran el siguiente proceso

1. El navegador inicia una petición DNS: Solicita la dirección IP de la URL yummyrecipesforme.com al servidor DNS.
2. El DNS responde con la dirección IP correcta.
3. El navegador inicia una petición HTTP: Solicita la página web yummyrecipesforme.com utilizando la dirección IP enviada por el servidor DNS.
4. El navegador inicia la descarga del malware.
5. El navegador inicia una petición DNS para recetasriquitasforme.com.
6. El servidor DNS responde con la dirección IP de greatrecipesforme.com.
7. El navegador inicia una petición HTTP a la dirección IP de greatrecipesforme.com.

Un analista senior confirma que el sitio web ha sido comprometido. El analista comprueba el código fuente del sitio web. Observan que se ha añadido código javascript para pedir a los visitantes del sitio web que descarguen un archivo ejecutable. El análisis del archivo descargado encontró un script que redirige los navegadores de los visitantes de yummyrecipesforme.com a greatrecipesforme.com.

El equipo de ciberseguridad informa de que el servidor web fue afectado por un ataque de fuerza bruta. El hacker descontento pudo adivinar fácilmente la contraseña porque la contraseña de administrador seguía siendo la contraseña por defecto. Además, no había controles para prevenir un ataque de fuerza bruta.

Tu trabajo es documentar el incidente en detalle, incluyendo la identificación de los protocolos de red utilizados para establecer la conexión entre el usuario y el sitio web. También debes recomendar una acción de seguridad a tomar para prevenir ataques de fuerza bruta en el futuro.

---

## Instrucciones

Siga las instrucciones y responda a la siguiente pregunta para completar la actividad. A continuación, vaya al siguiente elemento del curso para comparar su trabajo con un ejemplo completado.

### Paso 1: Acceder a la plantilla

Para utilizar la plantilla para este elemento del curso, haga clic en el enlace siguiente

[Security-incident-report-template.pdf](docs/Security-incident-report-template.pdf)

[Plantilla-de-informe-de-incidente-de-seguridad.pdf](docs/Plantilla-de-informe-de-incidente-de-seguridad.pdf)

### Paso 2: Acceda a los materiales de apoyo

Los siguientes materiales de apoyo le ayudarán a completar esta actividad. Manténgalos abiertos mientras realiza los siguientes pasos.

Para utilizar los materiales de apoyo para este elemento del curso, haga clic en el enlace de abajo

[tcpdump-traffic-log.pdf](docs/tcpdump-traffic-log.pdf)

[How-to-read-the-tcpdump-traffic-log.pdf](docs/How-to-read-the-tcpdump-traffic-log.pdf)

[Como-leer-el-registro-de-trafico-de-tcpdump.pdf](docs/Como-leer-el-registro-de-trafico-de-tcpdump.pdf)

### Paso 3: Identificar el protocolo de red implicado en el incidente

Como uno de los analistas de ciberseguridad en este escenario, se le ha encomendado la tarea de redactar un informe de incidente para este evento de seguridad. Utilizando el archivo de registro `tcpdump`, determine qué protocolo de red se identifica en las capturas de paquetes durante la investigación. Utilizará lo que aprendió sobre las cuatro capas del Modelo TCP/IP y qué protocolos ocurren en cada capa. A continuación, revise el registro de tráfico `tcpdump` y anote qué protocolo ha identificado en la primera sección de la plantilla de informe de incidentes de seguridad.

### Paso 4: Documente el incidente

Resuma el incidente en la segunda sección del informe. Proporcione tantos detalles y hechos como sea posible en su documentación. Al redactar la documentación, asegúrese de:

- Evite utilizar un lenguaje emocional fuerte (bueno, terrible, pésimo, etc.).
- Incluya tantos hechos sobre el asunto como pueda, incluyendo dónde ocurrió el incidente, cómo sucedió, si alguien lo presenció, cómo se descubrió, etc.
- Indique sus fuentes de información y pruebas.

Redactar una documentación precisa y detallada de los incidentes de ciberseguridad puede servir como punto de referencia para otros analistas de ciberseguridad. Además, una documentación de calidad puede utilizarse para educar a otros empleados sobre las medidas de ciberseguridad adoptadas en la empresa cuando se producen incidentes y puede ayudar a las empresas a cumplir con las distintas auditorías de seguridad.

### Paso 5: Recomiende una solución para los ataques de fuerza bruta

Tras documentar el incidente, escriba una recomendación para ayudar a su organización a prevenir los ataques de fuerza bruta en el futuro.

Algunos de los métodos de seguridad más utilizados para prevenir los ataques de fuerza bruta son:

- Exigir contraseñas seguras
- Imponer la Autenticación de dos factores (2FA)
- Supervisar los intentos de inicio de sesión
- Exigir cambios de contraseña más frecuentes
- Impedir el uso de contraseñas anteriores
- Limitar el número de intentos de inicio de sesión

Seleccione una medida de seguridad y explique por qué es eficaz en la sección tres de la plantilla de informe sobre incidentes de seguridad.

Cuantas más medidas de seguridad se apliquen, menos probabilidades habrá de que un actor malintencionado pueda acceder a información confidencial.

---

### Qué debe incluir en su respuesta

Asegúrese de abordar los siguientes criterios en su actividad finalizada:

- Nombre un protocolo de red identificado durante la investigación
- Documente el incidente
- Recomiende una medida de seguridad
