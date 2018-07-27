<!-- begin auto-generated title section -->
# Branching y Merging
<!-- end auto-generated section -->


## Duración

12 Minutos

## Resumen

Con proyectos más grandes, es muy común crear ** branches ** y luego ** fusionar ** las ramas en el proyecto principal cuando realiza cambios. Has visto referencias a `master` arriba, la rama predeterminada. Una mejora típica sería realizada por:

1. crear una rama (para que tenga un espacio de trabajo separado para trabajar) usando `git checkout -b <branch name>`
1. haciendo su trabajo como una serie de ciclos `git add`,` git commit` a la rama
1. fusionando sus cambios de nuevo en `master`
1. enviar un Pull request al propietario del proyecto (cubierto en una discusión por separado)

Al seguir este patrón, mantendrá su trabajo aislado del resto del proyecto hasta que esté listo para ser compartido o incorporado. Ejemplos incluyen:

* creando nuevas características
* experimentando con cambios al código
* corregir errores

Las branches deben ser pequeñas y autónomas para que puedan fusionarse fácilmente. Los cambios vertiginosos y complicados ​​en el código pueden hacer que sea casi imposible fusionar los cambios. Además, es habitual que las branches se centren en problemas específicos, es decir, una corrección de errores por rama o una característica nueva por rama.

## ¿Que hacer?

Una iteración típica de la creación de una característica (a veces llamada 'rama de característica') se vería así:

**Crea una nueva rama** y haz que `git` comience a rastrear los cambios en esa rama

```bash
$ git checkout -b appleseed-feature     # "-b" creates a new branch named "appleseed-feature"
```

** Trabaja / edita archivos ** en tu editor o IDE ... es decir, cambia la línea 23 en el archivo "jabberwocky.txt".

** `git add` ** cambia al área de ensayo ... 

```bash
$ git add jabberwocky.txt
$ git commit -m 'my first bit of work'
```

** Continuar editando si lo deseas ** ...

** `git add` ** estos nuevos cambios al área de staging ...

```bash
$ git add jabberwocky.txt
$ git commit -m 'my second bit of work'
```

**revise la rama principal** y prepárese para fusionar todos nuestros cambios con cualquier otro cambio que haya sido aceptado en la base de código original ...

```bash
$ git checkout master     # this checks out the master branch
```

** Actualice nuestra copia local ** ... Antes de intentar fusionar nuestros cambios en master, actualicemos nuestra copia local del repositorio con las actualizaciones que puedan haber ocurrido en la versión 'original' utilizando `git pull`.

```bash   
$ git pull                # this pulls any upstream changes into master 
```          

** fusiona los cambios locales en nuestra copia local de master ** ... Con los cambios más recientes y más importantes de 'upstream' en tu máquina local, intenta fusionar tu rama en tu copia local de `master`

```bash
$ git merge appleseed-feature
```

** `git push` ** cambia a nuestro ** repositorio de GitHub ** ... presumiendo una fusión exitosa (no te preocupes discutirá ¿Que hacer? si la fusión no es exitosa) ahora puedes` git push` tu cambios a su ** repositorio de GitHub ** (sus cambios NO van a la corriente ascendente, aún ...)

```bash
$ git push origin master
```

** elimine su rama innecesaria ** ... presumiendo una inserción exitosa, puede eliminar la rama de manera segura:

```bash
$ git branch -d appleseed-feature
```

Si usted (y su pareja, si está trabajando en parejas) han terminado, ¡puede poner su verde adhesivo! Así es como sabemos que terminaste.

! [nota adhesiva verde](images/Sticky-Note-02-Green-300px.png)

## El panorama

Imaginemos que está trabajando en un proyecto con varias commits para la rama principal y una sola rama de corrección de errores para reparar el Issue # 53 llamado `iss53`. Confirma `C3` y` C5` son los cambios que se hicieron commit en la rama, y ​​`C4` es un cambio realizado por otra persona a la rama principal durante ese mismo período de tiempo.

El historial creado por los pasos anteriores se vería así:

<img src = "https://git-scm.com/book/en/v2/book/03-git-branching/images/basic-merging-2.png">
** Fuente **: https://git-scm.com/book/en/v2/book/03-git-branching/images/basic-merging-2.png

Seguir este flujo de trabajo le permite potencialmente trabajar en múltiples características o errores y aún así mantener un conjunto de código limpio, confiable y funcional en todo momento.

## Sumérgete

### Haz un cambio en una rama

Además de `git add`,` git commit`, `git push`, el siguiente paso lógico es familiarizarse con el uso del flujo ** branch-work-merge ** para aislar su trabajo de los cambios realizados por otros.

#### Crear una rama

** Nota: ** reemplace "appleseed-feature" con el nombre de la función que está agregando. El comando `git checkout` te permite cambiar a una nueva rama. Si esa rama aún no existe, se puede crear con la opción `-b`.

```bash
$ git checkout -b appleseed-feature
```

¿Cual sería un buen nombre de branch? ¿Cuáles son las reglas para nombrar branches? Esta es una breve lista de reglas (para obtener una lista completa, consulte las [páginas de git man]) (https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-check-ref-format .html).

* No pueden tener dos puntos consecutivos `..` en cualquier lugar
* No pueden contener un `\`
* No pueden ser el caracter simple `@`
* No pueden comenzar o terminar con una barra `/`
* No pueden tener signo de interrogación `?`, Asterisco `*`, o abrir corchete `[` en cualquier parte
* No pueden tener caracteres de control ASCII (`\ t`,` \ n`), `space`, tilde` ~ `, caret` ^ `o colon`: `en cualquier lugar.

#### Haz tus cambios

El objetivo de crear un branch es crear un lugar seguro para modificar una parte específica del código. Con una 'rama git' creada, es seguro editar sus archivos, antes de continuar con los pasos restantes a continuación.

#### Etapa y confirma tus cambios

Como se describió anteriormente, una vez que esté satisfecho con sus cambios, se deben organizar y luego comprometer.

```bash
$ git add johnny_appleseed.txt
$ git commit -m "added edits to johnny's history"
```

#### Combina tus cambios en la rama principal

Como se señaló anteriormente, `git checkout` le permite cambiar a una rama alternativa. La rama `master` se crea de forma predeterminada por` git` y se usa a menudo como la rama principal para el lanzamiento. Para volver a la rama `master`, use` git checkout master`. A menudo otros pueden estar trabajando en la misma base de código y algunos de esos cambios pueden afectar su base de código, por lo que es fundamental recopilar todos esos cambios (es decir, descargarlos del repositorio "ascendente") para compararlos con su código, utilizando `git pull `.

Por ahora, supondremos que no hay conflictos entre sus cambios y otros cambios. Con esa premisa en mente, puede fusionar su código y su copia local del repositorio "upstream".

```bash
$ git checkout master
$ git pull
$ git merge appleseed-feature
```
Si tiene algún conflicto, deberá resolverlo. GitHub tiene un recurso simple para [resolver conflictos](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/). Una discusión completa de la resolución de conflictos está más allá del alcance de esta lección.

#### Eliminar su rama de características

Cuando haya terminado de usar una bifurcación (es decir, todos los cambios pertinentes se hayan fusionado en el maestro), simplemente puede eliminarla:

```bash
$ git branch -d appleseed-feature
```


## Recursos

* [Git Branching - Branches in a Nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
* [Git Branching - Basic Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

<!-- begin auto-generated nav-links section -->
| Previous | Up | Next |
|:---------|:---:|-----:|
| [Git Common Operations](./git_common_operations.md) | [Using Git](./git_Resumen.md) | [Using GitHub](./github_Resumen.md) |
<!-- end auto-generated section -->
