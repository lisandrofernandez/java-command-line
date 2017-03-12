java-command-line
=================

A (very simple) Java project example for compiling and running Java code
from the command line.

Requirements
------------

* ``git`` to download the project, although it can be downloaded as a
zip file via ``wget``, ``curl``, a web browser, etc.
* ``javac`` and ``java`` to compile  and run the code.
* ``jar`` to package the project.

Compile and run
---------------

Download the repository:

```bash
$ git clone --depth 1 https://github.com/lisandrofernandez/java-command-line.git
```

Get into the project root directory and prepare its structure to
compile:

```bash
$ cd java-command-line
$ mkdir -p target/classes
```

Compile:

```bash
$ javac -sourcepath src/main/java -classpath "src/main/lib/*" -d target/classes src/main/java/org/lisandro/Hello.java
```

Run:

```bash
$ java -classpath "target/classes:src/main/lib/*" org.lisandro.Hello "Lisandro"
```

> These commands work on a \*nix OS. In order to make them work on
> Windows, change the ``CLASSPATH`` directory delimiter ``:`` for ``;``.
> See
> [Wikipedia](https://en.wikipedia.org/wiki/Classpath_%28Java%29#OS_specific_notes)
> for more information.

Package
-------

Package application into a JAR file:

```bash
$ jar cvfm target/java-command-line.jar src/main/resources/META-INF/MANIFEST.MF -C target/classes .
```

Run from the JAR file:

```bash
$ cd target
$ java -jar java-command-line.jar "Lisandro"
```

Copyright
---------

Copyright &copy; 2017 [Lisandro Fernandez](https://github.com/lisandrofernandez).
See [LICENSE](https://github.com/lisandrofernandez/java-command-line/blob/master/LICENCE.md)
for details.
