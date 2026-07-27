# Indicaciones el proyecto

## Resumen de la actividad

En esta actividad, llevará a cabo una evaluación de vulnerabilidades para una pequeña empresa. Una evaluación de la vulnerabilidad es el proceso de revisión interna de los sistemas de seguridad de una organización. Evaluará los riesgos de un sistema de información vulnerable y esbozará un plan de corrección.

## Escenario

Usted es un analista de ciberseguridad recién contratado para una empresa de comercio electrónico. La empresa almacena información en un servidor de base de datos remoto, ya que muchos de los empleados trabajan a distancia desde lugares de todo el mundo. Los empleados de la empresa consultan, o solicitan, regularmente datos del servidor para encontrar clientes potenciales. La base de datos ha estado abierta al público desde el lanzamiento de la empresa hace tres años. Como profesional de la ciberseguridad, usted reconoce que mantener el servidor de la base de datos abierto al público es una vulnerabilidad grave.

Se le encomienda completar una evaluación de la vulnerabilidad de la situación para comunicar los riesgos potenciales a los responsables de la toma de decisiones en la empresa. Debe crear un informe escrito que explique cómo el servidor vulnerable supone un riesgo para las operaciones de la empresa y cómo se puede asegurar.

## Instrucciones paso a paso

Siga las instrucciones para completar cada paso de la actividad.

### Parte 1 - Abrir una plantilla de informe

#### Paso 1: Acceder a la plantilla

Utilice la siguiente plantilla para elaborar su informe escrito. Haga clic en el siguiente enlace:

[Vulnerability-assessment-report-template.pdf](docs/Vulnerability-assessment-report-template.pdf)

[Informe de Evaluación de Vulnerabilidades.pdf](docs/Informe_de_Evaluacin_de_Vulnerabilidades.pdf)

#### Paso 2: Acceda a los materiales de apoyo

Los siguientes materiales le ayudarán a completar esta actividad. Manténgalos abiertos mientras avanza hacia los siguientes pasos. Utilizará este recurso en la Parte 2 de esta actividad. Haga clic en el siguiente enlace:

[NIST-SP-800-30-Rev.-1.pdf](docs/NIST-SP-800-30-Rev.-1.pdf)

[NIST-SP-800-30-Rev.-1 (ES).pdf](docs/NIST-SP-800-30-Rev.-1_(ES).pdf)

#### Paso 3: Revisar la información sobre el servidor vulnerable

En esta actividad, le hemos proporcionado la **Descripción del** sistema y el **Alcance** del *Informe de evaluación de vulnerabilidades* en la plantilla proporcionada. Las evaluaciones de vulnerabilidades incluyen una descripción del sistema que se está evaluando y el Alcance del proyecto.

Revíse la **Descripción del sistema** y el **Alcance del informe** de *Evaluación de vulnerabilidades*.

La **Descripción del sistema** destaca los componentes relevantes, la arquitectura y las dependencias del sistema que se está evaluando. Todas estas partes y conexiones conforman la superficie de ataque del sistema de Información vulnerable.

El **Alcance** especifica el enfoque y los límites de la evaluación. Por ejemplo, puede especificar que el alcance de esta evaluación sólo se refiere a la confidencialidad, disponibilidad e integridad de los Datos en el servidor - no a la seguridad física del servidor o de sus sistemas informáticos relacionados.

### Parte 2 - Realizar la Evaluación de riesgos

#### Paso 1: Explicar la finalidad del sistema de información

Utilice el recurso **NIST SP 800-30 Rev. 1** para completar esta actividad.

Una vez que haya revisado la descripción y el alcance del sistema, redactará una declaración de propósito. La sección de propósito ayuda a las partes interesadas a comprender el objetivo subyacente y el resultado previsto de su análisis. Una declaración de propósito también conecta los objetivos técnicos de su análisis con las metas de la organización.

Considere lo que sabe sobre el servidor:

- *¿Qué valor tiene el servidor de base de datos para la empresa?*
- *¿Por qué es importante para la empresa proteger los datos del servidor?*
- *¿Cómo podría afectar al negocio la desactivación del servidor?*

En la sección **Propósito** del informe, utilice las preguntas proporcionadas y escriba **de 3 a 5 frases** (de 60 a 100 palabras) que describan la(s) razón(es) para realizar este análisis de vulnerabilidad.

#### Paso 2: Identificar las posibles fuentes de amenaza

Explore la sección *Fuentes de amenazas* del recurso *NIST SP 800-30 Rev. 1*. Utilizando lo que sabe sobre el servidor de Base de datos vulnerable, fíjese en los tipos de amenazas y ejemplos descritos.

En la columna Fuente de **amenazas** de la tabla Evaluación de riesgos de su plantilla, **identifique tres** posibles amenazas. Elija las amenazas basándose en la información que ha recopilado de la descripción del sistema, el Alcance, el Propósito y el recurso *NIST SP 800-30 Rev.* 1.

#### Paso 3: Identificar posibles eventos de amenaza

*NIST SP 800-30 Rev.* 1 proporciona una lista exhaustiva de posibles eventos de seguridad que podrían comprometer un sistema de Información vulnerable - etiquetados como *Eventos de Amenaza*. Esta Lista cubre lo que los atacantes de diferentes grupos suelen intentar conseguir y lo buenos que son en ello. Por ejemplo, un competidor empresarial podría tener las capacidades técnicas necesarias para llevar a cabo un ataque de denegación de servicio.

Explore la sección de *Eventos de Amenaza* en el recurso. A continuación, **identifique tres** eventos de amenaza que podrían iniciarse basándose en las fuentes de amenaza que haya identificado. Escriba los tres eventos de amenaza en la columna **Evento de amenaza** de la tabla de Evaluación de riesgos de su plantilla.

#### Paso 4: Calcular el riesgo de amenazas potenciales

Puede que recuerde anteriormente sobre el cálculo de riesgos que las amenazas y vulnerabilidades potenciales son factores importantes en los que pensar a la hora de evaluar la Seguridad de un recurso.

Consulte las secciones de probabilidad y gravedad del recurso *NIST SP 800-30 Rev. 1* y hágase las siguientes preguntas sobre cada una de las amenazas que identificó anteriormente:

- *¿Con qué frecuencia podría ocurrir?*
- *¿Se verían afectadas las funciones críticas del negocio?*
- *¿Cómo podría afectar al negocio y a sus Clientes?*

A continuación, calcule una puntuación de **Probabilidad** (1-3) y de **Gravedad** (1-3) para cada amenaza y añada sus puntuaciones a las columnas correspondientes de la tabla de Evaluación de riesgos de su plantilla. Después, calcule una puntuación global de **Riesgo** (1-9) para cada amenaza utilizando la Fórmula (**probabilidad x gravedad = riesgo**).

**Nota:** El número de filas de una tabla de riesgos puede variar en función de la complejidad y el alcance de la evaluación. En general, debe proporcionar a las partes interesadas una visión global de todos los riesgos importantes.

### Parte 3 - Proponer recomendaciones de Seguridad

#### Paso 1: Explique su enfoque

Otra sección que suele incluirse en una evaluación de vulnerabilidad es una explicación de su enfoque. Esto ayuda a las partes interesadas a comprender su proceso de reflexión para evaluar los riesgos que ha identificado, lo que añade un contexto valioso para las partes interesadas.

Usted está llevando a cabo una evaluación *cualitativa* de la vulnerabilidad, que se basa en el juicio subjetivo para evaluar la probabilidad y la gravedad de los riesgos. Su tarea aquí es estimar **lo malos que podrían ser los ataques juzgando sus posibilidades** basándose en sus conocimientos de seguridad. Las evaluaciones cualitativas de vulnerabilidad son útiles para identificar los riesgos de alto nivel a los que se enfrenta una organización. Esta información ayuda a las organizaciones a tomar decisiones informadas sobre la asignación de recursos, la planificación de proyectos y otros aspectos de sus operaciones empresariales.

En la sección **Enfoque** de su plantilla, escriba **de 3 a 5 frases** (de 60 a 100 palabras) explicando por qué ha seleccionado las 3 fuentes/eventos de amenaza específicos que eligió y por qué cree que son riesgos empresariales significativos.

#### Paso 2: Proponer una estrategia de reparación

Después de realizar una evaluación de vulnerabilidades, la creación de una estrategia de remediación bien definida es crucial para proteger sus sistemas y datos. La estrategia de remediación debe proporcionar a las partes interesadas los pasos procesables que se pueden tomar para remediar, o arreglar, las vulnerabilidades para evitar amenazas.

> **Nota:** Algunas amenazas no se pueden arreglar. En esos casos, es igualmente importante considerar una estrategia de *mitigación* : un plan para reducir la gravedad de una amenaza.

Piense en los riesgos que podría remediar y/o mitigar utilizando controles de seguridad como:

- Principio del menor privilegio
- Defensa en profundidad
- Autenticación multifactor (MFA)
- Marco de autenticación, autorización y contabilidad (AAA)

En la sección **Remediación** de la plantilla, escriba **de 3 a 5 frases** (de 60 a 100 palabras) resumiendo los controles de seguridad específicos que podrían implementarse para remediar o mitigar los riesgos del sistema de información.

Alinee sus sugerencias con los riesgos que ha evaluado. Por ejemplo, podría sugerir una Infraestructura de clave pública (PKI) para abordar la exfiltración de información sensible.

## Qué incluir en su respuesta

Asegúrese de abordar los siguientes elementos en su actividad completada:

- de 3 a 5 frases que describan las razones para realizar el análisis de seguridad en la sección **Propósito**
- Una sección de **Evaluación** de riesgos cumplimentada
- 3-5 frases que expliquen su razonamiento sobre los riesgos identificados en la sección **Enfoque**
- 3-5 frases que resuman una estrategia de *corrección* y/o *mitigación* en la sección **Corrección**

## Evaluación de la actividad

**Pregunta 1:** **Su Informe proporciona un propósito claro de por qué la evaluación de la vulnerabilidad del sistema es valiosa para la empresa.**

- [x]  Sí
- [ ]  No

**Pregunta 2: En la sección de Evaluación de riesgos de su Informe, ¿considera las posibles *fuentes de amenazas* de la base de datos vulnerable?**

- [x]  Sí
- [ ]  No

**Pregunta 3:** **En la sección de Evaluación de Riesgos de su Informe, ¿puede cada Evento de Amenaza ser *razonablemente* iniciado por sus fuentes de amenaza relacionadas?**

- [x]  Sí
- [ ]  No

**Pregunta 4:** **¿Contiene la tabla de Evaluación de riesgos de su Informe puntuaciones de probabilidad, gravedad y riesgo para cada fuente potencial de amenaza?**

- [x]  Sí
- [ ]  No

**Pregunta 5:** **Su Informe explica el enfoque que adoptó para analizar el Riesgo y proporciona una estrategia de remediación para asegurar el sistema vulnerable.**

- [x]  Sí
- [ ]  No

---

## INFORME DE EVALUACIÓN DE VULNERABILIDADES

[Informe de Evaluación de Vulnerabilidades | Gabriel Ternero](docs/Informe-de-Evaluación-de-Vulnerabilidades-Gabriel-Ternero.pdf) 👈
