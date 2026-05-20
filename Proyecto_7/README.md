# Auditoría y gestión de permisos de archivos y directorios en Linux

## Descripción de este proyecto

En el ámbito de la ciberseguridad corporativa, la correcta asignación de privilegios es un pilar fundamental para mitigar riesgos. El equipo de investigación de nuestra organización detectó que las configuraciones de permisos dentro del directorio estratégico de proyectos (`projects`) no reflejaban de manera estricta los niveles de autorización requeridos.

Dejar accesos abiertos de forma indebida vulnera el **Principio de Menor Privilegio (Least Privilege)**, el cual dicta que un usuario, proceso o sistema debe tener exclusivamente los accesos necesarios para realizar sus tareas y absolutamente nada más. El objetivo de esta práctica consiste en realizar una auditoría completa del directorio, interpretar detalladamente los niveles de acceso actuales y reconfigurar los permisos utilizando comandos nativos de Linux para asegurar los activos de información del equipo de investigación.

---

## Fundamentos: La cadena de permisos en Linux

Para alguien que se adentra por primera vez en sistemas operativos basados en Unix, el comando `ls -la` expone al inicio de cada línea una cadena aparentemente críptica de 10 caracteres (por ejemplo: `-rw-rw-r--`).
Esta cadena es en realidad un mapa de seguridad perfecto y altamente estructurado:

```bash
-    rw-   rw-   r--
▲     ▲     ▲     ▲
│     │     │     └─── (Other) Permisos de Otros
│     │     └───────── (Group) Permisos de Grupo
│     └─────────────── (User) Permisos de Usuario Propietario
└───────────────────── Tipo de Activo (- = Archivo, d = Directorio)
```

### Los tres permisos clave

* **`r` (Read / Lectura):** Permite abrir y ver el contenido de un archivo. En carpetas, permite listar su contenido (`ls`).
* **`w` (Write / Escritura):** Permite modificar, editar o borrar un archivo. En carpetas, permite crear o eliminar archivos en su interior.
* **`x` (Execute / Ejecución):** Permite correr un script o programa ejecutable. En carpetas, es el permiso que te permite "entrar" a ella usando el comando `cd`.
* **`-` (Guion corto):** Indica que ese permiso específico **no** ha sido concedido.

---

## Mejorando el análisis: Entendiendo el Sistema Octal (Numérico)

Aunque Linux permite modificar permisos usando letras (Modo Simbólico, ej: `u+w`), en entornos profesionales se prefiere el **Modo Octal**. Este sistema asigna un valor matemático binario fijo a cada tipo de permiso y se suman para obtener un identificador de un solo dígito por perfil:

$$\text{Lectura (r)} = 4 \quad|\quad \text{Escritura (w)} = 2 \quad|\quad \text{Ejecución (x)} = 1$$

Al sumar los valores de una tripleta de permisos, obtenemos un número del 0 al 7:

* `rwx` = $4 + 2 + 1 = \mathbf{7}$ (Control total)
* `rw-` = $4 + 2 + 0 = \mathbf{6}$ (Lectura y escritura)
* `r-x` = $4 + 0 + 1 = \mathbf{5}$ (Lectura y ejecución)
* `r--` = $4 + 0 + 0 = \mathbf{4}$ (Solo lectura)
* `---` = $0 + 0 + 0 = \mathbf{0}$ (Sin accesos)

### Modos comunes de seguridad corporativa

* **`755` (`rwxr-xr-x`):** Estándar para carpetas públicas o scripts ejecutables.
* **`644` (`rw-r--r--`):** Estándar para archivos de texto o código fuente seguro.
* **`600` (`rw-------`):** Alta seguridad. Solo el propietario lee y escribe (común para claves privadas SSH o contraseñas).

---

#### Descarga el documento en PDF

* [Auditoría y gestión de permisos en Linux | Gabriel Ternero](docs/Gestion-Permisos-Linux-Portfolio.pdf) 👈
* [File permissions in Linux | English version](docs/File-permissions-in-Linux.pdf) 👈
