<!-- comienza la sección de título generado automáticamente -->
# Git flujo de trabajo primario: Add, Commit, Push
<!-- fin de la sección autogenerada -->


## Duracion

10 minutos


## Resumen

En esta sección, cubriremos una serie de comandos, pero los principios son bastante sencillos:

* Determine el ** estado ** de su directorio local
* ** Agregar ** un archivo al área de preparación
* ** Commit ** ese archivo para el registro histórico
* ** Presione ** el archivo a su repositorio de GitHub

## Qué hacer

Esta parte del taller supone lo siguiente:

1. tu virtualenv `mytest` está ** activo **
1. Has ** hecho fork ** del [Proyecto sin código] (https://github.com/chalmerlowe/intro_to_sprinting_codeless_project/) a tu repositorio
1. has ** clonado ** el repositorio de Proyecto sin código en tu directorio local "mytest"
1. estás en el directorio `intro_to_sprinting_codeless_project` en tu línea de comandos

Con un repositorio recién clonado, podemos hacer algunas ediciones y revisiones del Proyecto sin código, que está lleno de archivos de poesía.

* Si escribe `ls` (o` dir` en Windows), debería ver varios archivos.

### Comprobación del estado
En cualquier momento, podemos verificar el estado de nuestro repositorio `git`. Antes de cambiar cualquier archivo, vamos a verificar cuál es el estado de nuestro repositorio, usando `git status`

`` `bash
$ git status
`` `
** NOTA **: todos los detalles sobre los mensajes que aparecen se detallan a continuación en la discusión ** Big Picture / Sumérgete **.

** NOTA **: El uso de `git status` es completamente ** opcional **, pero muy recomendado.


### Elige un archivo y edítalo.

1) Abra su editor de texto favorito o entorno de desarrollo integrado (IDE).

2) Seleccione un archivo para editar y abra el archivo en su editor / IDE.

** NOTA **: este taller está dirigido a todos los públicos (y puede incluir a los jóvenes), por lo que al realizar los siguientes cambios, evite todo lo inapropiado o que no sea seguro para el trabajo (NSFW). ** Juega como un campeón **.

2) Haz un cambio simple:

* Cambiar cualquier línea, palabra o frase
* Agregue una nueva línea
* Eliminar una línea

3) Guarde el archivo.

### Comprobación del estado
Antes de ir más allá, a menudo es útil volver a verificar el estado usando `git status`. Deberíamos observar que una línea en el resultado identifica que un archivo de texto ha sido modificado, pero no ha sido organizado.

```bash
$ git status
# abbreviated for clarity
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)
  modified: johnny_appleseed.txt

```

### Agregar el archivo
`git add` el archivo ** editado **, al área de preparación de git usando el comando` git add`. ** ASEGURE ** reemplaza `johnny_appleseed.txt` con el nombre real del archivo.

`` `bash
$ git add johnny_appleseed.txt
`` `

### Comprobación del estado
Echa un vistazo a las cosas ahora que el archivo se ha creado, de nuevo usando `git status` ... Deberíamos notar que una línea en el resultado identifica que un archivo de texto ha sido modificado Y ahora está listo para ser confirmado.

```bash
$ git status
# abbreviated for clarity
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  modified:   johnny_appleseed.txt
```

### Confirma tus cambios


`git commit` sus cambios cuando esté listo para hacer un registro permanente de ellos. Es habitual agregar un breve mensaje descriptivo (utilizando la opción `-m`) que describa sus cambios, siempre que lo haga.

`` `bash
$ git commit -m "Descripción de los cambios"
`` `

** NOTA **: los mensajes de confirmación deben ser cortos (normalmente 50 caracteres o menos). Consulte los ** Recursos ** a continuación para obtener más detalles sobre los mensajes de confirmación.

### Comprobación del estado
Echa un vistazo a las cosas ahora que se ha confirmado el archivo, una vez más usando `git status` ... Deberíamos notar que una línea en el resultado identifica que tus archivos están adelantados o que ya no están sincronizados con los archivos en ** tu Repo de GitHub **.

```bash
$ git status
# abbreviated for clarity
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
```

### Presione sus cambios a su repositorio de GitHub:
Presione el compromiso a ** su ** repositorio GitHub con `git push`:

```bash
$ git push origin master
```

En este caso, está subiendo a su rama `master` (es decir, la rama principal en la que ha estado trabajando) a ** origen **, su repositorio de GitHub. Discutiremos los branches con más profundidad más adelante.

### Verificación del estado, local
Echa un vistazo a las cosas ahora que el archivo ha sido subido, nuevamente usando `git status` ... Deberíamos notar que una línea en el resultado identifica que tu rama` master` está actualizada / o sincronizada con ** su repositorio de GitHub ** (`origen`).

```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
```
### Verificación de estado, remota
Ahora vaya a ** su GitHub Repo ** y confirme que los cambios que realizó en su computadora local están realmente presentes en los archivos en GitHub. ¡Debería poder navegar al archivo que editó y ver los cambios!

## Hecho con comandos por ahora!

Si usted (y su pareja, si está trabajando en parejas) han terminado, ¡puede poner su verde adhesivo! Así es como sabemos que terminaste.

! [nota adhesiva verde](imágenes/Sticky-Note-02-Green

## El panorama

En esta sección, cubrimos una serie de comandos que se dividen en varios conceptos clave:

* Determine el ** estado ** de su directorio local
* ** Agregar ** un archivo al área de preparación
* ** Commit ** ese archivo para el registro histórico
* ** Presione ** el archivo a su repositorio de GitHub

Con sus propios proyectos, para el 95% de lo que hace, esto es suficiente para realizar un seguimiento regular de su progreso y obtener sus cambios en Internet. Usará estos comandos más que cualquier otro.

** NOTA: ** Cubriremos varios conceptos más avanzados tanto en ** Sumérgete ** como en discusiones posteriores.


## Sumérgete

Especialmente para principiantes, comprender el estado de su directorio local es fundamental para aumentar sus habilidades. Y afortunadamente, para el 95% de lo que haces, solo unos pocos comandos te ayudará a alcanzar la mayor parte del camino.

### Comprobación de estado

Como algunos de nuestros mensajes anteriores fueron abreviados para mayor claridad, veamos más profundamente lo que realmente obtenemos del `estado de git`. Adquiera el hábito de leer los mensajes de estado después de cada comando que escriba y rápidamente obtendrá los comentarios que necesita. El siguiente comando le dice que, en este momento, su copia local coincide con la última escucha de su computadora en su servidor GitHub ... todo está ** limpio **.


```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

Si ha cambiado localmente los archivos que están ** en estado ** de trabajo ** (aún no ** en etapas **), verá algo como esto:

```bash
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Esto dice que el archivo llamado "README.md" se cambió localmente pero aún no está organizado. Note particularmente que hay varios mensajes de ayuda que me dicen cómo:

* ** agregue ** el archivo README.md al área de ensayo
* ** revertir ** el archivo README.md (es decir, volverlo a poner como antes de hacer mi cambio)

### Archivos en commit

Luego quiero mover el archivo al área de preparación (es decir, `git add`):

```bash
$ git add README.md
```

Esta vez, el mensaje de estado es ligeramente diferente. Las sugerencias son diferentes y los anuncios de estado son nuevos. Una vez más, la lectura de estos mensajes de estado lo ayudará a familiarizarse con los comandos Y sugerencias, y le llevará a casa los conceptos relacionados con los cambios locales, cambios por etapas, cambios comprometidos, etc.

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  modified:   README.md
```

Ahora podemos ver que el archivo está ** en etapas **, pero aún no está ** comprometido **. También podemos ver la sugerencia `git reset HEAD` para saber a qué escribir si necesitamos mover un archivo dado a un estado no estado.

### Commiting archivos

Luego quiero enviar el archivo (es decir, cargarlo para subir) usando `git commit -m '' una breve descripción` `, donde` -m` es una bandera para mi mensaje de confirmación. Los buenos mensajes de commit deben ser breves, dulces y descriptivos.

```bash
$ git commit -m 'my short description of the work'
[master 206546b] my short description of the work
 1 file changed, 1 insertion(+), 1 deletion(-)
```

En este caso, la salida me dice varias cosas:

* repite mi mensaje de compromiso
* me permite saber qué tipos de cambios ocurrieron: 1 archivo modificado, 1 línea insertada, 1 línea eliminada (es decir, cambié una línea).

En una discusión posterior, veremos cómo ver exactamente qué contenido cambió.

`git status` vuelve al rescate para ayudarnos a confirmar y comprender los cambios que hemos agregago.

```
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean
```

Aquí, como antes, mi árbol de trabajo está de nuevo ** limpio ** (se han confirmado todos los cambios). Sin embargo, a diferencia de antes, tengo algunos cambios en mi repositorio local que aún no están en el servidor remoto. Al igual que todos los demás mensajes de estado, puedo ver el mensaje de sugerencia que me guía sobre qué escribir a `git push` del archivo a mi ** repositorio de GitHub ** (` origen`).

### Subir archivos

Al enviar sus commits a GitHub, el comando `git push` le dará un resumen de todos los cambios que intentó realizar. En el siguiente caso, vemos que `git`:

* envió varios objetos (es normal que se envíen varios objetos incluso si solo ha cambiado un archivo. Esos otros elementos son internos a `git` y no son críticos para que se preocupe ahora).
* Comprimido los datos
* escribió los datos
* informó sobre dónde se enviaron los datos
* muestra varios valores hash que muestran los commits

```bash
$ git push
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 284 bytes | 0 bytes/s, done.
Total 3 (delta 2), reused 0 (delta 0)
To github:myusername/my_repo.git
   98b2f3f..206546b  master -> master
```

** Acerca de Hashes **: sin entrar en la ciencia de la computación detrás de él, `git` crea un valor único llamado` hash` por cada cambio que se compromete. Como los hashes son valores únicos, te permiten:

* elegir commits específicos para examinar o
* commits específicos para volver a, si encuentra que necesita deshacer un cambio en su repositorio.

Los números de siete dígitos que ve en `git` y en GitHub (por ejemplo,` 206546b`) identifican un cambio específico y son una forma abreviada de un número de hash más largo.

Volvamos a usar `git status` para ver los resultados de nuestro trabajo:
```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean
```

... y todo está limpio de nuevo, pero ahora con nuestro cambio local subido a GitHub y disponible para el mundo. ** SI ** va a ** su repositorio de GitHub **, puede ver sus cambios a través de su navegador web.

Adquiera el hábito de usar `git status` con regularidad, probablemente sea el comando más informativo y útil para comprender exactamente lo que está sucediendo.

### Agregar múltiples archivos

Si necesita agregar más de un archivo al área de ensayo, simplemente separe los nombres de archivo con un espacio:

```bash
$ git add <file1> <file2> ...
```


## Recursos

* [Git Basico - Grabando cambios a repositorio](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)

<!-- comience la sección de enlaces de navegación generados automáticamente -->
| Anterior | Arriba | Siguiente |
|: --------- |: ---: | -----: |
| [Clonación de un repositorio](./git_cloning.md) | [Usando Git](./git_Resumen.md) | [Operaciones comunes de Git](./git_common_operations.md) |
<!-- fin de la sección autogenerada -->