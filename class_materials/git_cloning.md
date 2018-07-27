<!-- comienza la sección de título generado automáticamente -->
# Clonación de un repositorio
<!-- fin de la sección autogenerada -->


## Duracion

12 minutos


## Resumen

Con un fork del proyecto en su repositorio de GitHub, es hora de `` clonar` el proyecto en su computadora local, por lo que tiene una copia local en su máquina para trabajar. El proyecto con el que comenzaremos es un proyecto que no tiene ningún código. Es un proyecto lleno de poemas famosos. Esto es a propósito. Queremos comenzar por

* practicar ** la mecánica ** de hacer cambios y proponer esos cambios al dueño
MIENTRAS
* ** minimizamos el miedo ** de romper cualquier cosa Y
* ** evitar ** tener que descubrir los matices del código de otra persona

## Qué hacer

Asegúrese de estar en su directorio de proyectos `mytest`. Si aún no estás allí, puedes usar el comando `cd`.

```bash
$ cd / path / to / my / dev / directory / mytest
```

Use el comando `git clone` para clonar una copia del repositorio en el directorio` mytest`.

** Nota: ** Como usted no es Johnny Appleseed, ** ASEGURE ** que cambie `johnny_appleseed` por el nombre de ** SU ** cuenta.

```bash
$ git clone https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project.git
```

El comando `clone` creará una nueva carpeta en el directorio` mytest`. Cambie los directorios a la nueva carpeta, usando el siguiente comando:

```bash
$ cd intro_to_sprinting_codeless_project
```
A continuación, agregue una referencia al repositorio ** original (es decir, el repositorio de Chalmer) ** utilizando el comando `git remote`. La referencia a menudo se denomina 'ascendente':

```bash
$ git remote add upstream https://github.com/chalmerlowe/intro_to_sprinting_codeless_project.git
```

** Nota: ** Solo hará esto ** una vez por cada proyecto ** en el que desee trabajar.

! [nota adhesiva verde](images/Sticky-Note-02-Green-300px.png)


## El panorama

Antes de que pueda comenzar a agregar a un proyecto, deberá clonar el proyecto en su computadora local en su directorio de trabajo local. En esta imagen, supongamos que queremos trabajar en un proyecto de calculadora RPN. Se ha hecho fork a nuestro repositorio de GitHub y luego se ha clonado en nuestro disco duro local. Copias de todas las carpetas en la calculadora RPN ahora están disponibles en nuestra computadora local.

! [clonación](images/git.png)


## Sumérgete

La siguiente discusión le dará más información sobre los repositorios de clonación y lo que ocurre en segundo plano durante cada uno de estos comandos.

** Nota: ** Como usted no es Johnny Appleseed, ** ASEGURE ** que cambie `johnny_appleseed` por el nombre de ** SU ** cuenta.

```bash
$ git clone https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project.git
```

El comando `clone` crea una carpeta, que debe estar llena de archivos de proyecto. `git` configurará automáticamente un enlace a un repositorio y le dará el nombre predeterminado:`origen` como un repositorio ** remoto **. En este caso, apuntará a ** su bifurcación de ** GitHub del repositorio.

Si tiene curiosidad y desea confirmar el enlace y el nombre del repositorio remoto, puede usar el comando `git remote -v`:

```bash
$ git remote -v
origen https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project (fetch)
origen https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project (push)
```
Aquí vemos que para el repositorio remoto `origin`, tenemos la capacidad de obtener datos de él y enviar datos a él. Esta capacidad de enviar datos al repositorio tiene sentido, ya que poseemos ese repositorio.

Como parte del compromiso con los proyectos de fuente abierta, queremos obtener actualizaciones del repositorio original (a menudo llamado el repositorio "ascendente") siempre que el desarrollador del proyecto realice cambios para que podamos confirmar que nada de lo que hayamos hecho interferirá con ningún otro trabajo. hecho en el proyecto.

Para habilitar `git` para encontrar` upstream` usamos el siguiente comando:

```bash
$ git remote add upstream https://github.com/chalmerlowe/intro_to_sprinting_codeless_project.git
```

De nuevo, si tiene curiosidad, puede confirmar que `git` ha almacenado el repositorio de flujo ascendente correcto con el comando` git remote -v`. Y ahora vemos que `git` reconoce tanto nuestro repositorio de GitHub como el repositorio del proyecto original.

```bash
$ git remote -v
origen https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project (fetch)
origen https://github.com/johnny_appleseed/intro_to_sprinting_codeless_project (push)
en sentido ascendente https://github.com/chalmerlowe/intro_to_sprinting_codeless_project (fetch)
```

** Nota: ** Solo hará esto ** una vez por cada proyecto ** en el que desee trabajar.


## Recursos

* [Conceptos básicos de Git: obtener un repositorio de Git](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository))

<!-- comience la sección de enlaces de navegación generados automáticamente -->
| Anterior | Arriba | Siguiente |
|: --------- |: ---: | -----: |
| [Conceptos de Git](./git_concepts.md) | [Usando Git](./git_Resumen.md) | [Git Primary Workflow: Add, Commit, Push](./git_main_lifecycle.md) |
<!-- fin de la sección autogenerada -->