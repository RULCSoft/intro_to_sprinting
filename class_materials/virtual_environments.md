<!-- comienza la sección de título generado automáticamente -->
# Configuración de entornos virtuales
<!-- fin de la sección autogenerada -->


## Duracion

15 minutos


## Resumen

Las herramientas de entorno virtual le permiten crear un entorno independiente para su proyecto, de modo que pueda evitar conflictos entre un proyecto y otro en términos de versiones de software (por ejemplo, `python 2.7` o` python 3.6`), así como las versiones de otras bibliotecas de lo que tu proyecto podría depender.

### Objetivos

Al participar en esta sesión, los asistentes podrán:

* Identificar qué es un entorno virtual Y cuando usar un entorno virtual es una solución adecuada para una tarea
* Crea un entorno virtual
* Llene un entorno virtual con el software necesario para completar una tarea de programación / desarrollo


## Qué hacer

* Crea un directorio para tu proyecto, en este caso, crearemos un directorio llamado `mytest`
* En el símbolo del sistema, asegúrese de que se encuentra en un directorio donde desea que se ubique la carpeta del proyecto (muchas personas lo colocan en su carpeta `Mis documentos` O` inicio`. Desde ese directorio, ejecute el siguiente comando:

```bash
$ mkdir mytest
```

* Cambiar directorios en la nueva carpeta:

```bash
$ cd mytest
```

* Crea un entorno virtual con Python 3, usando el siguiente comando:

```bash
$ conda create -n mytest python = 3
```
* Activa tu entorno virtual usando el comando apropiado para tu sistema operativo:

#### <img src="images/mac_icon.png" width = "24" height = "24"> <img src = "images/linux_icon.jpg" width = "24" height = "24"> Mac / Linux

```bash
$ source activate mytest
```

#### <img src = "images / windows_icon.jpg" width = "24" height = "24"> Windows

``` bat
C: \> activate mytest
```

* Instale dos paquetes adicionales en su entorno virtual (como sugerencia, intente con `ipython` y` mock`) usando el siguiente comando:

```bash
conda install ipython simulacro
```

## Listo con los comandos por ahora!

Si (si trabajas en parejas, tú y tu pareja) ya terminaron, ¡ahora puedes poner tu sticker verde! Así es como sabemos que terminaste con los comandos.

![nota adhesiva verde](images/Sticky-Note-02-Green-300px.png)

Si le gusta leer, también puede seguir leyendo esta página.

## El panorama

Un área de confusión que aparece a menudo cuando se trabaja en código abierto proviene del hecho de que en cualquier momento dado, puede haber múltiples copias del código (en su computadora local, en su repositorio de Github O en el repositorio del proyecto original).

A lo largo de este taller, haremos nuestro mejor esfuerzo para ayudar a resaltar con qué copia del código estamos trabajando a través de una serie de imágenes. Específicamente, identificaremos cuándo estamos interactuando con archivos locales O con nuestro Repositorio de Github O con el repositorio del proyecto original, etc.

Para esta lección, visualizamos una estructura de directorios / carpetas bastante típica en su computadora local. En esta imagen, TEN EN CUENTA que tenemos:

* un directorio para su ** proyecto (s) ** que se guardará en
* un directorio asociado con ** miniconda **

![Our Local Directories](images/basic_dir.png)

Cuando creas un virtualenv, conda agregará subdirectorios al directorio miniconda. Específicamente, creará un directorio que contendrá:

* una base de datos y metadatos sobre virtualenv
* software y bibliotecas relacionadas con el proyecto (es decir, Python y cualquier módulo que instale en el virtualenv)

NOTA: estas carpetas son ** NO ** duplicadas entre sí, pero ** están ** vinculadas entre sí.
NOTA: Las carpetas de miniconda virtualenv ** ** incluirán su código de proyecto.

![Dires locales con ambientes conda](images/conda_envs.png)


## Sumérgete

### ¿Qué es un entorno virtual?

Como se mencionó anteriormente, los entornos virtuales (también llamados virtualenvs) son herramientas que se utilizan para mantener los proyectos separados, especialmente en términos de mantener diferentes versiones de software separadas y diferentes versiones de bibliotecas separadas. Por ejemplo, virtualenvs evitan que la carpeta de paquetes de sitios de Python se llene de versiones potencialmente conflictivas de software Y así previene problemas que surgen cuando un proyecto necesita ** versión xx ** de una biblioteca pero otro proyecto necesita ** versión yy ** de la misma biblioteca. En su núcleo, virtualenvs son directorios glorificados que usan scripts y metadatos para organizar y controlar el entorno. Se le permite tener un número esencialmente ilimitado de virtualenvs. Y como viste arriba, son muy fáciles de crear usando varias herramientas de línea de comandos, como `conda`.

### ¿Cuándo deberíamos usar un entorno virtual?

Cada vez que tiene más de un proyecto y existe la posibilidad de conflictos entre sus bibliotecas, es un buen momento para usar virtualenv. Habiendo dicho eso, muchos programadores usan entornos virtuales para ** todas las tareas de programación menos triviales **. Especialmente para principiantes, el uso de virtualenvs desde el principio en su carrera de aprendizaje creará una habilidad valiosa Y ayudará a prevenir errores furtivos relacionados con las discrepancias de versión. Errores que pueden ser difíciles de diagnosticar.

### ¿Cómo se crea un entorno virtual?

Si bien hay varios programas o bibliotecas que pueden generar virtualenvs (consulte la sección [Recursos](#recursos) para obtener una lista). Para la lección de hoy, usaremos el administrador de paquetes `conda`, que incluye la capacidad de producir virtualenvs de manera simple y fácil.

Suponiendo que tiene `conda` instalado, estos pasos le permiten crear y activar un entorno virtual.

```bash
$ conda create -n mytest python = 3
```

Descripción:
* `conda` ejecuta el programa conda.
* `create` le dice que cree un virtualenv
* `-n` identifica el nombre del virtualenv, en este caso,` mytest`
* `python = 3` le dice a conda que quiere instalar Python versión 3 en este virtualenv

** NOTA **: puede usar la versión 2.xo la versión 3.x de Python, e independientemente de cuál elija, conda usará de manera predeterminada la versión más reciente de Python. Sorta ... [ver nota al pie 1](#footnotes). Si necesita seleccionar una versión menor específica de python, use la siguiente sintaxis:

`python = 3.2`

Cuando ejecuta el comando `conda create`,` conda` se prepara para instalar Python y las dependencias de las que depende Python. Mostrará una salida similar a la siguiente.

```bash
MacComputer:intro_to_sprinting username$ conda create -n mytest python=3
Fetching package metadata .......
Solving package specifications: ..........

Package plan for installation in environment /Users/username/miniconda3/envs/mytest:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    openssl-1.0.2k             |                1         3.0 MB
    python-3.6.0               |                0        11.7 MB
    setuptools-27.2.0          |           py36_0         523 KB
    wheel-0.29.0               |           py36_0          87 KB
    pip-9.0.1                  |           py36_1         1.7 MB
    ------------------------------------------------------------
                                            Total:        17.0 MB

The following NEW packages will be INSTALLED:

    openssl:    1.0.2k-1
    pip:        9.0.1-py36_1
    python:     3.6.0-0
    readline:   6.2-2
    setuptools: 27.2.0-py36_0
    sqlite:     3.13.0-0
    tk:         8.5.18-0
    wheel:      0.29.0-py36_0
    xz:         5.2.2-1
    zlib:       1.2.8-3

Proceed ([y]/n)?
```

Para finalizar la creación del virtualenv e instalar el software, presione `y`.

### Activando un virtualenv

Una vez que haya creado un virtualenv, tendrá que activarlo. La activación tiene varios efectos secundarios:

* Cambia temporalmente la variable `$ PATH` para que las llamadas al comando` python` (y comandos similares) se vean primero en el directorio `bin /` del virtualenv.
* Cambia temporalmente el indicador de shell para mostrar qué virtualenv está usando. Es probable que su mensaje se parezca a esto, con el nombre de su virtualenv entre paréntesis delante del mensaje:
     * Mac / Linux: `(mytest) $`
     * Windows: `(mytest) C: \>`

Para activar su virtualenv, ejecute el comando apropiado para su sistema operativo:

#### Mac/Linux

```bash
$ source activate mytest
```

#### Windows

```bat
C:\> activate mytest
```

** Nota: ** Si está utilizando Power Shell, `activate` no funcionará por defecto. Escriba `cmd` primero para obtener un símbolo del sistema normal, * luego *` activate mytest`.

### Agregar software a su virtualenv

Para agregar más software al virtualenv, puede usar `conda` para instalar el software. Los mantenedores de conda proporcionan acceso a muchas bibliotecas Python y no Python, pero no a todas. Si conda no puede instalar una biblioteca particular que necesita, generalmente puede usar `pip` o una herramienta de instalación de paquetes similar para instalarlo en su lugar (cubrir` pip` está fuera del alcance de este taller).

Por ejemplo, para instalar IPython, puede usar el siguiente comando `conda`:

```
conda install ipython
```

Conda se preparará para instalar IPython y cualquier dependencia en la que se base IPython. Mostrará un resultado similar al siguiente (truncado para ahorrar espacio).

```bash
Fetching package metadata .......
Solving package specifications: ..........

Package plan for installation in environment /Users/chalmerlowe/miniconda3:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    conda-env-2.6.0            |                0          601 B
    ...
    ipython-5.3.0              |           py35_0        1021 KB
    conda-4.3.14               |           py35_0         505 KB
    ------------------------------------------------------------
                                            Total:         3.8 MB

The following NEW packages will be INSTALLED:

    appnope:          0.1.0-py35_0
    ...
    wcwidth:          0.1.7-py35_0

The following packages will be UPDATED:

    conda:            4.1.11-py35_0 --> 4.3.14-py35_0
    conda-env:        2.5.2-py35_0  --> 2.6.0-0
    requests:         2.10.0-py35_0 --> 2.13.0-py35_0

Proceed ([y]/n)?
```

Para finalizar la instalación de IPython y sus dependencias, presione `y`.

#### Varios paquetes

Se pueden instalar varios paquetes al mismo tiempo, separando los nombres de paquetes con espacios:

`conda install flake8 funcsigs simulacro`

### Dejando el virtualenv cuando hayas terminado

Cuando haya terminado de trabajar en su virtualenv, puede desactivarlo con el siguiente comando:

#### Mac/Linux

```bash
(mytest) $ source deactivate
$
```

#### Windows

```bat
(mytest) C:\> deactivate
C:\>
```


### Alternativas a Conda

Consulte la sección de Recursos para encontrar enlaces a otras herramientas que a menudo se usan para crear entornos virtuales y / o manejar administración de paquetes, como: `pip`,` venv`, `virtualenv`.

Discutir esto está fuera del alcance de este curso. Usar cualquiera de estas herramientas debería ser muy similar al uso de conda, pero puede haber matices dependiendo de su sistema, la herramienta que elija usar y su versión de Python.


## Recursos

* [Documentación de Conda](http://conda.pydata.org/docs/get-started.html): una guía de introducción sobre cómo usar conda
* [instrucciones de pip](https://docs.python.org/3/installing/): descripción general de un administrador de paquetes orientado a Python: Pip
* [Conda vs Pip](https://jakevdp.github.io/blog/2016/08/25/conda-myths-and-misconceptions/): excelente discusión sobre los beneficios de la conda y las diferencias entre conda y pip
* [venv](https://docs.python.org/3/library/venv.html): una herramienta, incluida con Python, para crear entornos de Python aislados
* [virtualenv](https://virtualenv.pypa.io/en/stable/): una herramienta popular, aunque sea de terceros, para crear entornos de Python aislados



## Footnotes

[1]: the maintainers of conda put together resources for the most recent versions of Python libraries as they get released, but sometimes there may be a short lag.


| Previous | Up | Next |
|:---------|:---:|-----:|
| [Installing the Software You'll Need](./installing_tools.md) | [Environment Set-up](./environment_overview.md) | [Setting up GitHub](./github_setup.md) |
