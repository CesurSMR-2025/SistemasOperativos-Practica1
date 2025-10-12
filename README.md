# Sistemas Operativos en Red - Unidad 1: Automatización
## Introducción a la Automatización
Automatizar tareas consiste en crear scripts (**archivos de texto con comandos**) que el sistema ejecuta automáticamente.
Sirven para ahorrar tiempo, evitar errores y mantener los sistemas funcionando sin intervención manual. Algunos ejemplos de tareas que se pueden automatizar incluyen la gestión de archivos, la instalación de software y la configuración de servicios.

Para lograr esto, se pueden utilizar diferentes herramientas y enfoques, dependiendo del sistema operativo en uso, los objetivos a alcanzar y las preferencias del administrador. Por un lado necesitamos un lenguaje de scripting que nos permita escribir estos scripts y por otra parte sistemas de automatización que faciliten su ejecución y gestión.

Los lenguajes de scripting son lenguajes de programación interpretados diseñados para facilitar la creación de scripts. Algunos de los lenguajes de scripting más populares incluyen:

- **Bash**: Utilizado principalmente en sistemas Linux (y Unix), donde viene preinstalado. Aunque también es posible utilizarlo en Windows a través de herramientas WSL para realizar ciertas tareas.
- **Python**: Lenguaje de programación, utilizado también para scripting por su simplicidad, legibilidad y amplia biblioteca de librerías.
- **PowerShell**: Método estándar en sistemas Windows para la automatización de tareas.
- **JavaScript**: En desarrollo web, puede ser utilizado para scripting del lado del servidor.

Los lenguajes de scripting son solo una parte de la automatización. También se requieren herramientas y sistemas que faciliten la ejecución y gestión de los scripts. Algunas de estas herramientas incluyen:

- **Cron**: Utilizado en sistemas Linux (y Unix) para programar tareas que se ejecutan en intervalos regulares.
- **Systemd**: En sistemas Linux modernos, se utiliza para gestionar servicios y puede ejecutar scripts en respuesta a eventos del sistema.
- **Task Scheduler**: Herramienta de Windows que permite programar la ejecución de scripts y tareas en momentos específicos.
- **Ansible**: Herramienta de automatización que permite gestionar configuraciones y despliegues.


## Automatización en Linux
En Linux, la automatización se realiza principalmente mediante scripts de Bash y herramientas del sistema como Cron y Systemd que permiten programar y ejecutar esas tareas automáticamente, en momentos específicos o en respuesta a eventos del sistema. 

La estructura de un script de Bash es bastante simple. Comienza con la línea shebang (`#!/bin/bash` bash en este caso), que indica al sistema que programa debe interpretar el contenido del script. Este programa puede ser el propio Bash o cualquier otro intérprete de comandos, como Python (`#!/usr/bin/python`) o JavaScript (`#!/usr/bin/node`). A continuación, se pueden incluir una serie de comandos que se ejecutarán de forma secuencial. Por ejemplo:

```bash
#!/bin/bash
# Script de ejemplo
echo "Hola, mundo"
```

```bash
#!/usr/bin/python
# Script de ejemplo en Python
print("Hola, mundo")
```

```bash
#!/usr/bin/node
// Script de ejemplo en JavaScript
console.log("Hola, mundo");
```

Cabe aclarar que de hecho, los tres scripts anteriores, son scripts Bash. De hecho, si le pasáramos los ejemplos anteriores al intérprete de Python o JavaScript, obtendríamos un error. Lo que sucede cuando los ejecutamos con Bash es que Bash lee la primera línea del script para determinar qué intérprete utilizar en el resto del archivo.

De ahora en adelante nos centraremos en el scripting con **Bash**. 

Al utilizar Bash, podemos utilizar exactamente los mismos comandos que utilizamos en la terminal. Reciprocamente, cualquier fragmento de script que escribamos en Bash puede ser ejecutado directamente en la terminal.

### Permisos
Recuerdo que como funcionan los permisos en linux, cada archivo y directorio tiene un conjunto de permisos que determinan quién puede leer, escribir o ejecutar el archivo. Estos permisos se dividen en tres categorías: usuario propietario, grupo propietario y otros. Para ver los permisos de un archivo, se puede utilizar el comando `ls -l`, que muestra una lista detallada de los archivos y sus permisos. 

Los símbolos que se utilizan para representar los permisos son:

- `r`: Permiso de lectura
- `w`: Permiso de escritura
- `x`: Permiso de ejecución
- `-`: Sin permiso

Las 3 primeras posiciones representan los permisos del propietario, las 3 siguientes los del grupo y las 3 últimas los de otros. 

![Permisos en Linux](img/permisos.png)

Los permisos se pueden modificar utilizando el comando `chmod`, que permite cambiar los permisos de lectura, escritura y ejecución de archivos y directorios. Con `chmod`, se pueden agregar o quitar permisos de forma específica.

```bash
# Agregar permiso de ejecución para el propietario
chmod u+x nombre_del_script.sh
# Agregar permiso de lectura para el grupo
chmod g+r nombre_del_script.sh
# Quitar permiso de ejecución para el propietario
chmod u-x nombre_del_script.sh
# Agregar permiso de ejecución a todos
chmod +x nombre_del_script.sh
```

Los permisos predeterminados de un archivo nuevo vienen dados por la máscara de creación de archivos (umask) del usuario. Se puede utilizar el comando `umask` para ver la configuración actual de la máscara. 

Para que un script de Bash pueda ser ejecutado, es necesario que tenga permisos de ejecución. Le podemos agregar permisos de ejecución con el siguiente comando:

```bash
chmod +x nombre_del_script.sh
```

### Cron


## Automatización en Windows