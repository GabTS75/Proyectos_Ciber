# Indicaciones del proyecto

## Resumen de la actividad

En esta actividad, crearás un nuevo documento de portafolio para demostrar tu experiencia usando SQL. Para crear este documento de portafolio, revisarás un escenario y seguirás una serie de pasos.

Este escenario está relacionado con el uso de los operadores **AND**, **OR** y **NOT** en SQL para filtrar información. Explica cada una de las consultas que realices.

---

## Escenario

Usted es un profesional de seguridad en una gran organización. Parte de su trabajo es investigar problemas de seguridad para ayudar a mantener el sistema seguro. Recientemente descubrió algunos problemas potenciales de seguridad que involucran intentos de inicio de sesión y máquinas de empleados.

Su tarea es examinar los datos de la organización en sus tablas **employees** y **log_in_attempts**. Deberá utilizar filtros SQL para recuperar registros de diferentes conjuntos de datos e investigar los posibles problemas de seguridad.

---

## Instrucciones paso a paso

Siga las instrucciones para completar cada paso de la actividad. A continuación, responda a las 8 preguntas del siguiente punto del curso antes de comparar su trabajo con un modelo completado.

### Paso 1: Acceder a la plantilla

Descargue la plantilla para utilizarla en el desarrollo de la actividad. En los siguientes pasos se incluirán más instrucciones sobre cómo utilizar la plantilla.

[Apply filters to SQL queries.pdf](docs/Apply_filters_to_SQL_queries.pdf)

---

### Paso 2: Acceder al material de apoyo

Los siguientes materiales de apoyo te ayudarán a completar esta actividad. Manténgalos abiertos mientras continúa con los siguientes pasos.

Descargue los materiales de apoyo para el desarrollo de la actividad.

[Instructions for including SQL queries.pdf](docs/Instructions_for_including_SQL_queries.pdf)

[Table formats.pdf](docs/Table_formats.pdf)

---

### Paso 3: Recuperar después de horas de intentos fallidos de inicio de sesión

Recientemente ha descubierto un posible incidente de seguridad ocurrido fuera del horario laboral.

Para investigarlo, necesita consultar la tabla **log_in_attempts** y revisar la actividad de inicio de sesión fuera del horario laboral. Utilice filtros en SQL para crear una consulta que identifique todos los intentos de inicio de sesión fallidos que se produjeron después de las 18:00.

> *La hora del intento de inicio de sesión se encuentra en la columna **login_time**. La columna **success** contiene un valor de **0** cuando un intento de inicio de sesión falló; puede utilizar un valor de **0** o **FALSE** en su consulta para identificar los intentos de inicio de sesión fallidos.*

Describa su consulta y cómo funciona en la sección Recuperar tras horas de intentos de inicio de sesión fallidos de la plantilla.

---

### Paso 4: Recuperar los intentos de inicio de sesión en fechas concretas

Un evento sospechoso ocurrió el 2022-05-09.

Para investigar este evento, desea revisar todos los intentos de inicio de sesión que se produjeron ese día y el día anterior. Utilice filtros en SQL para crear una consulta que identifique todos los intentos de inicio de sesión que se produjeron el 2022-05-09 o el 2022-05-08.

> *La fecha del intento de inicio de sesión se encuentra en la columna **login_date**.*

Describa su consulta y cómo funciona en la sección Recuperar intentos de inicio de sesión en fechas específicas de la plantilla.

---

### Paso 5: Recuperar intentos de inicio de sesión fuera de México

Ha habido actividad sospechosa con intentos de inicio de sesión, pero el equipo ha determinado que esta actividad no se originó en México.

Ahora, necesita investigar los intentos de inicio de sesión que ocurrieron fuera de México. Utilice filtros en SQL para crear una consulta que identifique todos los intentos de inicio de sesión que se produjeron fuera de México.

> *Cuando se refiere a México, la columna de **país** contiene valores tanto de **MEX** como de **MEXICO**, y necesita usar la palabra clave **LIKE** con **%** para asegurarse de que su consulta refleje esto.*

Describa su consulta y cómo funciona en la sección Recuperar intentos de inicio de sesión en fechas específicas de la plantilla.

---

### Paso 6: Recuperar empleados en Marketing

Su equipo desea realizar actualizaciones de seguridad en máquinas específicas de empleados en el departamento de Marketing.

Usted es responsable de obtener información sobre estos equipos de empleados y necesitará consultar la tabla de **employees**. Utilice filtros en SQL para crear una consulta que identifique a todos los empleados del departamento de Marketing de todas las oficinas del edificio Este.

> *El departamento del empleado se encuentra en la columna **departamento**, que contiene valores que incluyen **Marketing**. La oficina se encuentra en la columna oficina. Algunos ejemplos de valores en esta columna son **Este-170**, **Este-320** y **Norte-434**. Tendrá que utilizar la palabra clave **LIKE** con **%** para filtrar el edificio "Este".*

Describa su consulta y cómo funciona en la sección Recuperar empleados en Marketing de la plantilla.

---

### Paso 7: Recuperar empleados en Finanzas o Ventas

Su equipo necesita ahora realizar una actualización de seguridad diferente en las máquinas para los empleados de los departamentos de Ventas y Finanzas.

Utilice filtros en SQL para crear una consulta que identifique a todos los empleados de los departamentos de Ventas o Finanzas.

> *El departamento del empleado se encuentra en la columna **departamento**, que contiene valores que incluyen **Ventas** y **Finanzas.***

Describa su consulta y cómo funciona en la sección Recuperar empleados en Finanzas o Ventas de la plantilla.

---

### Paso 8: Recuperar a todos los empleados que no estén en IT

Su equipo necesita realizar una actualización más en las máquinas de los empleados. Los empleados que pertenecen al departamento de tecnología de la información ya han recibido esta actualización, pero los empleados de todos los demás departamentos la necesitan.

Utilice filtros en SQL para crear una consulta que identifique a todos los empleados que no pertenezcan al departamento de informática.

> *El departamento del empleado se encuentra en la columna **departamento**, que contiene valores que incluyen **Tecnología de la información.***

Describa su consulta y cómo funciona en la sección Recuperar todos los empleados que no pertenecen a TI de la plantilla.

---

### Paso 9: Finalice su documento

Para finalizar el documento, asegúrate de completar las secciones Descripción del proyecto y Resumen de la plantilla “Aplicar filtros a consultas SQL”.

En la sección Descripción del proyecto, ofrece una visión general del escenario y de lo que consigues mediante SQL. Escribe de dos a cuatro frases.

En la sección Resumen, proporcione un breve resumen de las tareas anteriores y conéctelas con el escenario. Escribe aproximadamente de dos a cuatro frases.

---

## Qué incluir en tu respuesta

Asegúrate de incluir lo siguiente en tu actividad completada:

- Capturas de pantalla de las consultas o versiones mecanografiadas de las mismas
- Explicaciones de las consultas
- Una descripción del proyecto al principio
- Un resumen al final
- Detalles sobre el uso de **LIKE** para buscar un patrón
- Detalles sobre el filtrado de fechas y horas
- Detalles sobre el uso de **AND** y **OR** para filtrar según varias condiciones
- Detalles sobre el uso de **NOT** en los filtros

🎉
