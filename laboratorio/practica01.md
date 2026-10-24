# Práctica 1: Línea de comandos y scripts usando Bash

**Tema:** Introducción a la línea de comandos y los scripts para eficientar procesos.<br>
**Lenguaje:** Bash<br>
**Entrega:** Individual a través del almacén privado asignado por el laboratorista.<br>
**Fecha de entrega:** Martes 27 de octubre de 2026 a las 11:00 PM.<br>
**Elaboró:** [Leonardo Gallo](https://github.com/lngallo)

## Descripción 

En esta práctica se integrarán conocimientos previamente adquiridos sobre el uso de la línea de comandos para administrar un equipo de cómputo mediante una construcción de un script usando Bash.

## Objetivo

Utilizar los comandos básicos de la consola de Linux para navegar por directorios, crear y manipular archivos, consultar su contenido y ejecutar un script en Bash que automatice una tarea sencilla.

## Ejercicio de exploración

Abre una terminal y realiza lo siguiente. Todo se realiza a través de la terminal.

1. Muestra el directorio en el que te encuentras.

2. Lista los archivos y directorios de tu ubicación actual.

3. Crea un directorio llamado _src/bash_.

4. Entra al directorio recién creado.

5. Crea un archivo vacío llamado _contenido.md_.

6. Considerando que el archivo presentará de manera organizada el contenido de la carpeta escribe dentro algo referente en _contenido.md_.

7. Muestra en consola lo que hay dentro del archivo.

8. Crea una copia llamada _copia.md_.

9. Cambia el nombre de _copia.md_ a _respaldo.md_.

10. Busca la palabra Computación en _contenido.md_, suponiendo que la hayas escrito en el archivo.

Comandos sugeridos: pwd, ls, mkdir, cd, touch, echo, cat, cp, mv y grep.

Puedes consultar la ayuda de un comando con man, por ejemplo, _$man cp_. Para salir de la ayuda, presiona q.

## Actividad principal

Un script es un archivo que contiene instrucciones que el intérprete de comandos ejecuta de manera secuencial. Permite automatizar tareas que, de otro modo, tendríamos que realizar manualmente.

### Problema

Elabora un script llamado organizar.sh que automatice la preparación de una carpeta de trabajo para una actividad escolar.

El script deberá:

1. Mostrar un mensaje de bienvenida.

2. Solicitar el nombre del alumno.

3. Crear un directorio llamado _src/bash/practica01_.

4. Crear dentro de ese directorio dos archivos vacíos: notas.md y reporte.md.

5. Guardar el nombre del alumno en reporte.md.

6. Mostrar un mensaje que indique que la estructura se creó correctamente.

7. Mostrar el contenido del reporte.

8. Guardar en el reporte las últimas 50 líneas del historial.

9. Tomar captura de pantalla del contenido final del reporte, visto en la consola, y guarda la imagen de la siguiente manera _img/evidenciaP01.jpg_ y enlace la imagen al inicio del reporte.

### Indicaciones

1. Escribe las instrucciones necesarias para resolver el problema.

2. Guarda el archivo.

3. Otorga permisos de ejecución al script.

4. Ejecuta el programa desde la terminal.

5. Comprueba que se creó el directorio y que los archivos tienen el contenido esperado.

Pista: Investiga el uso de read, las variables, mkdir -p, touch, echo y la ejecución de scripts mediante bash o permisos de ejecución.

## Punto extra

Adecua el ejercicio visto en clase para que el archivo _notas.md_ siempre se cree por defecto en la carpeta principal del usuario que está en sesión en caso de no existir y posteriormete debe agregar las nuevas notas en dicho archivo.

## Preguntas de reflexión

No es necesario entregarlas, sólo debes meditar las respuestas.

¿Cuál es la diferencia entre un comando ejecutado directamente en la terminal y un script?

¿Qué función cumple la primera línea #!/bin/bash cuando se utiliza en un script ejecutable?

¿Qué diferencia existe entre cp y mv?

¿Para qué sirven los permisos de ejecución?

¿Qué ventaja ofrece automatizar estas tareas mediante Bash?

¿Qué sucedería si se intenta crear un directorio que ya existe utilizando mkdir sin la opción -p?
