# Indicaciones del proyecto

## Objetivo

En esta actividad, crearás un reporte de incidente utilizando el conocimiento que has adquirido sobre redes a lo largo de este curso para analizar un incidente de red. Analizarás la situación utilizando el Marco de Ciberseguridad del Instituto Nacional de Estándares y Tecnología (NIST CSF). El CSF es un marco voluntario que consta de normas, directrices y mejores prácticas para gestionar los riesgos de ciberseguridad. Crear un informe de incidentes de ciberseguridad de calidad y aplicar el CSF puede demostrar un enfoque proactivo de la seguridad, mejorar la comunicación y la transparencia con las partes interesadas y mejorar las prácticas de seguridad dentro de su organización. También puede añadir el informe de incidentes que cree a su cartera de ciberseguridad cuando lo complete.

El CSF es escalable y puede aplicarse en una amplia variedad de contextos. A medida que continúe aprendiendo más y perfeccionando su comprensión de las habilidades clave de ciberseguridad, puede utilizar las plantillas proporcionadas en esta actividad en otras situaciones. Saber identificar qué medidas de seguridad aplicar en respuesta a las necesidades de la empresa le ayudará a determinar cuáles son las mejores opciones disponibles cuando se trata de la seguridad de la red.

Asegúrese de completar esta actividad antes de continuar. En el siguiente punto del curso, podrá autoevaluar su respuesta. Después de eso, habrá un ejemplar completado para comparar con su propio trabajo. También tendrá la oportunidad de responder a las preguntas de la rúbrica que le permitirán reflexionar sobre los elementos clave de su declaración profesional.

## Escenario

A continuación, complete las instrucciones paso a paso.

Usted es un analista de ciberseguridad que trabaja para una empresa multimedia que ofrece servicios de diseño web, diseño gráfico y soluciones de marketing en redes sociales a pequeñas empresas. Su organización ha sufrido recientemente un ataque DoS, que comprometió la red interna durante dos horas hasta que se resolvió.

Durante el ataque, los servicios de red de su organización dejaron de responder repentinamente debido a una avalancha de paquetes ICMP entrantes. El tráfico normal de la red interna no pudo acceder a ningún recurso de la red. El equipo de gestión de incidentes respondió bloqueando los paquetes ICMP entrantes, deteniendo todos los servicios de red no críticos fuera de línea y restableciendo los servicios de red críticos.

A continuación, el equipo de ciberseguridad de la empresa investigó el incidente de seguridad. Descubrieron que un actor malicioso había enviado una avalancha de pings ICMP a la red de la empresa a través de un cortafuegos no configurado. Esta vulnerabilidad permitió al atacante malicioso saturar la red de la empresa mediante un ataque de denegación de servicio (DoS).

Para solucionar este problema de seguridad, el equipo de seguridad de la red implementó:

- Una nueva regla de cortafuegos para limitar la tasa de paquetes ICMP entrantes
- Verificación de la dirección IP de origen en el cortafuegos para comprobar si hay direcciones IP falsificadas en los paquetes ICMP entrantes
- Software de supervisión de red para detectar patrones de tráfico anómalos
- Un sistema IDS/IPS para filtrar parte del tráfico ICMP basado en características sospechosas

Como analista de ciberseguridad, tiene la tarea de utilizar este evento de seguridad para crear un plan para mejorar la seguridad de la red de su empresa, siguiendo el Marco de Ciberseguridad (CSF) del Instituto Nacional de Estándares y Tecnología (NIST). Utilizarás el CSF para ayudarte a navegar por los diferentes pasos del análisis de este evento de ciberseguridad e integrar tu análisis en una estrategia de seguridad general. Hemos dividido el análisis en diferentes partes en la plantilla que figura a continuación.

Puede explorarlas aquí:

- **Identificar** los riesgos de seguridad a través de auditorías periódicas de las redes internas, sistemas, dispositivos y privilegios de acceso para identificar posibles brechas en la seguridad.
- **Proteger** los activos internos mediante la aplicación de políticas, procedimientos, formación y herramientas que ayuden a mitigar las amenazas a la ciberseguridad.
- **Detectar** posibles incidentes de seguridad y mejorar las capacidades de supervisión para aumentar la rapidez y eficacia de las detecciones.
- **Responder** para contener, neutralizar y analizar incidentes de seguridad; implantar mejoras en el proceso de seguridad.
- **Recuperar** el funcionamiento normal de los sistemas afectados y restaurar los datos y/o activos de los sistemas que se hayan visto afectados por un incidente.

## Instrucciones paso a paso

A continuación, vaya al siguiente elemento del curso para comparar su trabajo con un ejemplo completado.

### Paso 1: Acceder a la plantilla de análisis de informes de incidentes

Para acceder a la plantilla para este tema del curso, haga clic en el siguiente enlace:

[01_Completed-Example-of-an-Incident-report-analysis.pdf](docs/01_Completed-Example-of-an-Incident-report-analysis.pdf)

[01_Ejemplo-de-analisis-de-informe-de-incidente.pdf](docs/01_Ejemplo-de-analisis-de-informe-de-incidente.pdf)

Enlace a los materiales de apoyo:

[02_Applying-the-NIST-CSF.pdf](docs/02_Applying-the-NIST-CSF.pdf)

[02_Aplicacion-del-NIST-CSF.pdf](docs/02_Aplicacion-del-NIST-CSF.pdf)

[03_Incident-report-analysis.pdf](docs/03_Incident-report-analysis.pdf)

[03_Plantilla-de-analisis-de-informe-de-incidentes.pdf](docs/03_Plantilla-de-analisis-de-informe-de-incidentes.pdf)

### Paso 2: Resumir el incidente de seguridad

Utilizando la plantilla proporcionada, proporcione un resumen del suceso de seguridad ocurrido. Incluye información sobre el suceso de seguridad, su causa, el impacto y la respuesta. También puedes incluir información sobre los sistemas atacados, el origen del ataque y el impacto estimado.

### Paso 3: Identificar el tipo de ataque y los sistemas afectados

Piensa en todos los conceptos tratados en el curso hasta ahora y reflexiona sobre el escenario y define qué tipo de ataque se produjo y qué sistemas se vieron afectados. Enumera esta información en la hoja de trabajo de análisis de informes de incidentes en la sección titulada "Identificar".

### Paso 4: Proteja los activos de su organización para que no corran peligro

A continuación, evaluará dónde puede mejorar la organización para proteger aún más sus activos. En este paso, se centrará en crear un plan de acción inmediato para responder al incidente de ciberseguridad. Al crear este plan, reflexione sobre la siguiente pregunta:

- *¿Qué sistemas o procedimientos deben actualizarse o modificarse para proteger mejor los activos de la organización?*

Escriba su respuesta en la plantilla de análisis de informes de incidentes en la sección "Proteger".

### Paso 5: Detectar incidentes similares en el futuro

Es importante supervisar continuamente el tráfico de red en los dispositivos de red para comprobar si hay actividad sospechosa, como paquetes ICMP externos entrantes procedentes de direcciones IP no fiables que intentan atravesar el cortafuegos de red de la organización.

Para este paso, considere las formas en que usted y su equipo pueden supervisar y analizar el tráfico de red, las aplicaciones de software, realizar un seguimiento de los usuarios autorizados frente a los no autorizados y detectar cualquier actividad inusual en las cuentas de usuario. Escriba su respuesta en la hoja de trabajo de análisis de respuesta ante incidentes, en la sección "Detectar".

### Paso 6: Responder a futuros incidentes de ciberseguridad

Después de identificar las herramientas y métodos que usted y su organización tienen en marcha para detectar posibles vulnerabilidades y amenazas, cree un plan de respuesta en caso de que se produzca un incidente en el futuro. Esto suele ocurrir después de que se haya producido el incidente y haya sido resuelto por usted y su equipo. En este caso, creará un plan de respuesta para futuros incidentes de ciberseguridad. Algunos puntos a tener en cuenta a la hora de crear un plan de respuesta ante cualquier incidente de ciberseguridad:

- *¿Cómo pueden usted y su equipo contener los incidentes de ciberseguridad y los dispositivos afectados?*
- *¿Qué procedimientos existen para ayudarle a usted y a su equipo a neutralizar los incidentes de ciberseguridad?*
- *¿Qué datos o información pueden utilizarse para analizar este incidente?*
- *¿Cómo puede mejorarse el proceso de recuperación de su organización para gestionar mejor futuros incidentes de ciberseguridad?*

Escriba su respuesta en la plantilla de análisis de informes de incidentes, en la sección "responder".

### Paso 7: Recuperarse del incidente

Considere qué medidas deben tomarse para ayudar a la organización a recuperarse del incidente de ciberseguridad. Reflexione sobre toda la información que ha recopilado sobre el incidente en los pasos anteriores para considerar qué dispositivos, sistemas y procesos deben restaurarse y recuperarse.

Considere las siguientes preguntas:

- *¿Qué información necesita poder recuperar inmediatamente?*
- *¿Qué procesos existen para ayudar a la organización a recuperarse del incidente?*

Escribe tu respuesta en la parte de "recuperación" de la hoja de trabajo.

---

## Qué incluir en su respuesta

Más adelante, tendrá la oportunidad de evaluar su actuación utilizando los criterios enumerados. Asegúrese de incluir lo siguiente en su actividad completa.

Curso 3 análisis de informes de incidentes

- Resume el evento de seguridad
- Identifica el tipo de ataque y los sistemas afectados por el incidente
- Ofrece un plan de protección contra futuros incidentes de ciberseguridad
- Describe los métodos de detección que pueden utilizarse para identificar posibles incidentes de ciberseguridad
- Incluye un plan de respuesta para el incidente de ciberseguridad y un esquema para futuros incidentes de ciberseguridad
- Esboza planes de recuperación que usted y la organización pueden aplicar en futuros incidentes de ciberseguridad.

---

### Paso 8: Evaluar su actividad

Completará una autoevaluación para su actividad de portafolio de informes de incidentes. Utilice las preguntas que se presentan para revisar su propio trabajo. El proceso de autoevaluación es una parte importante de la experiencia de aprendizaje porque le permite evaluar *objetivamente* su informe de incidentes.

Para completar la autoevaluación, primero abra el Ejemplar de Actividad de Portafolio en el siguiente punto del curso. Compare su documento de informe de incidente completado. Responda sí o no a cada afirmación proporcionada al final de la Actividad del Portafolio.

cuando complete y envíe sus respuestas, recibirá una puntuación porcentual. Esta puntuación le ayudará a confirmar si ha completado los pasos requeridos de la actividad. La nota de aprobado recomendada para este proyecto es de al menos el 80%. Si desea aumentar su puntuación, puede revisar su proyecto y volver a enviar sus respuestas para reflejar los cambios realizados.

Intente conseguir al menos 5 puntos antes de pasar al siguiente tema.

### Evaluación del proyecto

1. **Su Informe de Incidente incluye un resumen del incidente.**
    - [x]  Sí
    - [ ]  No
2. **Su Informe de Incidente identifica el tipo de ataque y el alcance del incidente, incluyendo qué dispositivos y/o sistemas de la red se vieron afectados por el evento de Seguridad.**
    - [x]  Sí
    - [ ]  No
3. **Su Informe de Incidentes ofrece un plan para proteger la red de futuros incidentes.**
    - [x]  Sí
    - [ ]  No
4. **Su Informe de Incidente describe métodos para detectar eventos de Seguridad en el futuro.**
    - [x]  Sí
    - [ ]  No
5. **Su Informe de Incidente describe un proceso que su organización puede utilizar para responder a incidentes de ciberseguridad similares en el futuro.**
    - [x]  Sí
    - [ ]  No
6. **Su Informe de Incidente enumera los Procedimientos para Recuperarse de un Evento de Seguridad similar.**
    - [x]  Sí
    - [ ]  No

---

✨
