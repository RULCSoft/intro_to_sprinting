<!-- comienza la sección de título generado automáticamente -->
# Instalación del software que necesitará
<!-- fin de la sección autogenerada -->


## Duracion

15 minutos


## Resumen

La colaboración en sprints generalmente requiere el uso de herramientas de software para ser realmente eficaz y eficiente. Para este taller, usaremos `git` y` miniconda (conda) `para practicar nuestras habilidades.

### Objetivos

* Descargar las herramientas
* Instalar las herramientas
* Prueba para una instalación exitosa
* Revise el propósito de las herramientas

## Qué hacer

### Paso uno: Descarga e instala `git`

Primero verifique si `git` ya está instalado en su computadora.

Abra un símbolo del sistema / terminal y escriba `git`

Verás una de estas dos cosas.

- **Un montón de texto**, que es un documento que explica algunos de los comandos `git` más comunes. Si ve esto, vaya a las instrucciones sobre [descargar e instalar Conda.](#Download-and-install-conda) porque git ya está instalado.

```bash
usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]

These are common Git commands used in various situations:
...
```

- `git: Comando no encontrado. ¡Esto es bueno! Significa que **seguirás nuestras instrucciones para instalar git!** Sigue leyendo.`

#### <img src="images/windows_icon.jpg" width="24" height="24"> Windows 

1. Descargue el [instalador git](https://git-scm.com/downloads) (** NOTA: ** Si no está seguro de si necesita la versión de 32 o 64 bits, puede [siga estos pasos](https://support.microsoft.com/en-us/help/15056/windows-7-32-64-bit-faq))

3. Ejecute el archivo .exe que descargó y siga las instrucciones.

#### <img src = "images/mac_icon.png" width="24" height="24"> Mac OS 

1. Descargue el [instalador git](https://git-scm.com/downloads)

2. Abra el archivo .dmg que descargó. Ejecute el instalador dentro y siga las instrucciones.

##### Alternativamente, instale usando homebrew

Muchos usuarios de Mac usan [homebrew](http://brew.sh/) para instalar programas.

`` `bash
brew instalar git
`` `

#### <img src = "images/linux_icon.jpg" width="24" height="24"> Linux 

Si está ejecutando Linux, es muy probable que ya tenga `git` instalado. Si no es así, instálelo escribiendo uno de estos comandos en el símbolo del sistema.

** Los sistemas basados ​​en Red Hat ** (Red Hat, Centos, Fedora) usan:

`` `bash
$ sudo yum install git-all
`` `

** Los sistemas ** basados ​​en Debian (Ubuntu, Debian) usan:

`` `bash
$ sudo apt-get install git-all
`` `

### Paso dos: confirma tu instalación de `git`

En un símbolo del sistema, escriba `git config`. Si `git` está instalado correctamente, verá texto que explica algunas de las opciones de configuración comunes para` git`.

### Paso tres: Descarga e instala `conda`

Siga las instrucciones para su sistema operativo en la [guía de inicio rápido de miniconda](http://conda.pydata.org/docs/install/quick.html). Use una versión ** de Python 3 ** de conda.

### Paso cuatro: confirma tu instalación `conda`

En un símbolo del sistema, escriba `conda list`. Si `conda` está instalado correctamente, verá un resumen de los paquetes instalados por` conda`.

### Solución de problemas

Aquí hay una lista de mensajes de error y cómo solucionarlos.

- `conda: comando no encontrado. Esto significa que debe cerrar y reiniciar su terminal. Si eso no lo soluciona, solicite ayuda. ([Detalles aquí.] (Https://unix.stackexchange.com/questions/86012/what-is-the-purpose-of-the-hash-command))

## Listo con los comandos por ahora!

Si (si trabajas en parejas, tú y tu pareja) ya terminaron, ¡ahora puedes poner tu verde pegajoso! Así es como sabemos que terminaste con los comandos.

! [nota adhesiva verde](images/Sticky-Note-02-Green-300px.png)

Si le gusta leer, también puede seguir leyendo esta página.

## El panorama

### ¿Qué es `git` y por qué lo instalamos?

`git` es un sistema de control de versiones distribuidas para administrar archivos. Permite que varias personas trabajen en colecciones de archivos (generalmente código fuente) y luego * fusionar fácilmente * el trabajo de otros para que todos puedan tener la versión más actualizada del proyecto. Una lección posterior proporcionará más detalles sobre `git`.

### ¿Qué es miniconda (`conda`) y por qué lo instalamos?

Miniconda contiene el administrador de paquetes `conda` y` Python`. `conda` es independiente del idioma, por lo que también puede usarlo para respaldar la entrega de este taller con lenguajes de programación además de` Python`. Una vez que esté instalado Miniconda, podrá:

* crear entornos virtuales y
* administrar instalaciones separadas de `Python`
* administrar una gran cantidad de paquetes / bibliotecas de Python

Siempre que trabaje en un nuevo proyecto, debe crear un entorno separado para ese proyecto. `conda` te permite hacer esto de manera fácil y eficiente. Una lección posterior proporcionará más detalles sobre los entornos virtuales y el uso del administrador de paquetes `conda`.

** NOTA ** Para este tutorial, usaremos `conda`. Existen otras herramientas que logran objetivos similares y funcionan de manera similar, como `venv`,` pip`, y `virtualenv`. Durante PyCon Sprints, asegúrese de usar cualquier herramienta de entorno virtual que sugiera el mantenedor de su proyecto. Ver Recursos para más información.

## Recursos

* [Usando conda](http://conda.pydata.org/docs/using/index.html): Un tutorial sobre cómo usar `conda`

* [conda cheatsheet](https://conda.io/docs/_downloads/c
