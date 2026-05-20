# Análisis y desarrollo del laboratorio

## Paso 1: Auditoría inicial del entorno

Antes de realizar modificaciones, se procedió a listar de forma detallada todos los elementos del directorio `projects`:

```bash
researcher2@ubuntu:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research 4096 May 20 18:30 .
drwxr-xr-x 4 root        root     4096 May 20 18:25 ..
drwxrwxr-x 2 researcher2 research 4096 May 20 18:30 drafts
-rw-rw-rw- 1 researcher2 research  128 May 20 18:30 .project_x.txt
-rw-rw-rw- 1 researcher2 research  850 May 20 18:30 project_k.txt
-rw-rw-r-- 1 researcher2 research  412 May 20 18:30 project_t.txt
```

### Diagnóstico de vulnerabilidades detectadas

1. `project_k.txt` (`-rw-rw-rw-`): La categoría "Otros" (cualquier cuenta en el sistema) tiene permiso de escritura, lo que permite que personal no autorizado altere o sabotee los resultados de la investigación.

2. `.project_x.txt` (`-rw-rw-rw-`): Es un archivo oculto (inicia con un punto .) que presenta la misma vulnerabilidad crítica de acceso de escritura global.

3. `drafts` (`drwxrwxr-x`): La carpeta de borradores permite la ejecución al grupo de usuarios, violando la política restrictiva de la empresa.

## Paso 2: Remoción de accesos en archivos estándar (`project_k.txt`)

La directiva exige que la categoría de "Otros" pierda la capacidad de alterar los archivos. Se ejecutó la remoción de este privilegio mediante modo simbólico:

```bash
researcher2@ubuntu:~/projects$ chmod o-w project_k.txt
researcher2@ubuntu:~/projects$ ls -la project_k.txt
-rw-rw-r-- 1 researcher2 research 850 May 20 18:30 project_k.txt
```

* Explicación: El argumento `o-w` le indica al sistema sustraer (`-`) el permiso de escritura (`w`) a la categoría Otros (`o`).

* Equivalente profesional octal: `chmod 664 project_k.txt`.

## Paso 3: Gestión de permisos críticos en archivos ocultos archivados (`.project_x.txt`)

El archivo oculto `.project_x.txt` ha sido archivado. La directiva corporativa exige que nadie (incluido el creador) tenga permiso de escritura para evitar modificaciones accidentales, debiendo asegurar únicamente el acceso de lectura para el usuario y el grupo de trabajo.

```bash
researcher2@ubuntu:~/projects$ chmod u-w,g-w,o-w .project_x.txt
researcher2@ubuntu:~/projects$ chmod g+r .project_x.txt
researcher2@ubuntu:~/projects$ ls -la .project_x.txt
-r--r----- 1 researcher2 research 128 May 20 18:30 .project_x.txt
```

* **Explicación:** Al remover la escritura global (`u-w,g-w,o-w`) y garantizar la lectura al grupo (`g+r`), blindamos el activo a un estado robusto e inalterable (`-r--r-----`).

* **Optimización avanzada en un solo paso:** `chmod 440 .project_x.txt` (4 para el dueño, 4 para el grupo, 0 para otros).

## Paso 4: Restricción perimetral en directorios (`drafts`)

La organización determinó que únicamente el usuario líder (researcher2) debe poseer privilegios de ejecución (capacidad de ingresar mediante cd) a la carpeta `drafts`.

```bash
researcher2@ubuntu:~/projects$ chmod g-x drafts
researcher2@ubuntu:~/projects$ ls -la
drwxr--r-x 2 researcher2 research 4096 May 20 18:30 drafts
```

* **Explicación:** Quitando el permiso de ejecución al grupo (`g-x`), impedimos que los miembros del grupo exploren el directorio, preservando el acceso legítimo del dueño (`rwx`).

* **Equivalente profesional octal:** `chmod 745 drafts`.

---

## Conclusiones e impacto

A través de la ejecución de esta auditoría y la aplicación de tareas de robustecimiento (hardening), se mitigaron proactivamente múltiples vectores de riesgo interno. La transición consciente desde el entendimiento visual de la cadena simbólica hasta el dominio del sistema octal permite un control de accesos ágil y alineado con los estándares internacionales de gobernanza en seguridad informática.
