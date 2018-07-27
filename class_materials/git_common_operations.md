<!-- comienza la sección de título generado automáticamente -->
# Operaciones comunes de Git
<!-- fin de la sección autogenerada -->


## Duracion

10 minutos


## Resumen

Git tiene una serie de capacidades para simplificar su vida, ayudarlo a comprender el estado de su directorio y mejorar su capacidad de comunicar sus cambios.

Cuando usas `git`, a veces quieres saber más sobre los cambios que estás cometiendo ... aquí es donde entra` git diff`.

## Qué hacer

Para este próximo ejercicio, cambiaremos un solo archivo y usaremos la herramienta `git diff` para examinar esos cambios específicos en detalle.

1. Use su editor de texto para abrir el archivo `beowulf.txt` en el repositorio local de Proyecto sin código.
2. Cambia la letra "B" en la primera línea "The Project Getenberg EBook of Beowulf ..." a una "b" minúscula.
1. Ejecute el siguiente comando:

```bash
git diff
```

Esto le mostrará, en detalle, las diferencias entre la última versión del archivo que se confirmó mediante `git` y cualquier cambio que haya creado desde entonces. Para detalles sobre cómo se divide esto, vea la sección ** Sumérgete **.

## Hecho con comandos por ahora!

Si usted (y su pareja, si está trabajando en parejas) han terminado, ¡puede poner su verde adhesivo! Así es como sabemos que terminaste.

! [nota adhesiva verde](images/Sticky-Note-02-Green-300px.png)

## El panorama

Con sus propios proyectos, para el 95% de lo que hace, `git status` y` git diff` deberían ser suficientes para realizar un seguimiento regular de su progreso y confirmar los cambios que ha realizado. Utilizará estos comandos, junto con `git add`,` git commit`, `git push` más que cualquier otro.

** NOTA: ** Cubriremos varios conceptos más avanzados en discusiones posteriores.

## Sumérgete

Puede ser muy útil ver qué hay de diferente entre el archivo en el que está trabajando y la última versión confirmada. Para hacer esto, use el comando `git diff`.

`git diff` representa cambios de una manera conocida generalmente como" formato de diff ". Este formato básicamente representa todos los cambios como la adición o eliminación de líneas de los archivos.

** Nota: ** los ejemplos a continuación están en blanco / negro, pero en la mayoría de los entornos de línea de comandos (`bash`, por ejemplo) también estarán codificados por colores para facilitar su lectura.

Si agrego una línea a un archivo, veré algo como esto:

```bash
$ git diff
diff --git a/test.txt b/test.txt
index 624b469..f8b6f0a 100644
--- a/test.txt
+++ b/test.txt
@@ -10,3 +10,4 @@ line 9
 line 10
 line 11
 line 12
+line 13
```

La primera parte del resultado muestra los nombres de archivo de los archivos que se comparan. Esto es importante, porque la salida de `git diff` puede mostrar muchos archivos si ha cambiado numerosos archivos en su repositorio. También puede especificar archivos individuales o grupos de archivos proporcionando los nombres de los archivos como argumentos al comando `git diff` como lo siguiente:` git diff <archivo1> <archivo2> ... `. Incluso con un solo archivo especificado, la salida siempre le mostrará qué archivo (s) se está (n) comparando con cada cambio.

La línea que comienza con un solo `+` indica que esta línea es nueva en comparación con lo que está actualmente en escena O comprometido. También tenga en cuenta que la herramienta me muestra algunas líneas antes y / o después del cambio para ayudarme a ver el contexto del cambio.

También puede ver qué número (s) de línea están involucrados en el cambio. La línea `@@` le dice que el contenido mostrado comienza en la línea 10 e incluye 3 líneas (`10,3`) del archivo original y luego le dice que el contenido mostrado también comienza en la línea 10 e incluye 4 líneas (` 10,4`) del nuevo archivo.

Del mismo modo, si elimino una línea:


```bash
$ git diff
diff --git a/test.txt b/test.txt
index f8b6f0a..abe1f83 100644
--- a/test.txt
+++ b/test.txt
@@ -9,5 +9,4 @@ line 8
 line 9
 line 10
 line 11
-line 12
 line 13
```

Aquí, el `-` me muestra la línea que se eliminó, es decir, la línea 12. Observe que el valor mostrado para la línea de partida y el número de líneas mostradas puede cambiar: la línea` @@ `le dice que el contenido mostrado comienza en línea 9 e incluye 5 líneas (`9,5`) del archivo original y luego le dice que el contenido mostrado también comienza en la línea 9 e incluye solo 4 líneas (` 9,4`) del nuevo archivo.

Si * cambio * una línea, el cambio aparece realmente como una línea eliminada Y una línea adicional:

```bash
$ git diff
diff --git a/test.txt b/test.txt
index abe1f83..6276304 100644
--- a/test.txt
+++ b/test.txt
@@ -8,5 +8,5 @@ line 7
 line 8
 line 9
 line 10
-line 11
+line eleven
 line 13
```
La línea `@@` le dice que el contenido mostrado comienza en la línea 8 e incluye 5 líneas (`8,5`) del archivo original y luego le dice que el contenido mostrado también comienza en la línea 8 e incluye 5 líneas (` 8,4`) del nuevo archivo.

Un archivo con múltiples cambios se vería así:

```bash
$ git diff
diff --git a/test.txt b/test.txt
index abe1f83..a3fc0c5 100644
--- a/test.txt
+++ b/test.txt
@@ -2,11 +2,11 @@ line 1
 line 2
 line 3
 line 4
-line 5
+line five
 line 6
 line 7
 line 8
 line 9
 line 10
-line 11
+line eleven
 line 13
```

Aquí puedo ver que cambié la línea 5 y la línea 11.

Muchas herramientas basadas en GUI le mostrarán más información, como destacar los caracteres individuales en una línea que se modificaron. Dado que esto varía de una herramienta a otra, no se tratará en detalle aquí.

## Recursos

* [Conceptos básicos de Git: registrar cambios en el repositorio](https://git-scm.com/book/es/v2/Git-Basics-Recording-Changes-to-the-Repository)

<!-- comience la sección de enlaces de navegación generados automáticamente -->
| Anterior | Arriba | Siguiente |
|: --------- |: ---: | -----: |
| [Git Primary Workflow: Add, Commit, Push](./git_main_lifecycle.md) | [Usando Git](./git_Resumen.md) | [Branching and Merging](./git_branch_merge.md) |
<!-- fin de la sección autogenerada -->