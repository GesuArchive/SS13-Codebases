
# BUILDING

[Back](../README.md)

> Guide to download [Graphviz](https://graphviz.org/) graph project, written on the [DOT description language](https://en.wikipedia.org/wiki/DOT_(graph_description_language)) from the [CthulhuOnIce/SS13-Codebases](https://github.com/CthulhuOnIce/SS13-Codebases) network.

### Table of content
- [BUILDING](#building)
		- [Table of content](#table-of-content)
	- [Dependencies](#dependencies)
		- [Windows](#windows)
		- [Ubuntu](#ubuntu)
	- [Building](#building-1)
		- [Visual Studio Code (VS Code)](#visual-studio-code-vs-code)
		- [Automatic (via scripts)](#automatic-via-scripts)
			- [Windows](#windows-1)
			- [Ubuntu](#ubuntu-1)
		- [Manual](#manual)
			- [Windows](#windows-2)
			- [Ubuntu](#ubuntu-2)


## [Dependencies](https://en.wikipedia.org/wiki/Dependency)

A program may require one or more other programs to run (the "dependencies").

 * [Graphviz](https://graphviz.org/)


### [Windows](https://www.microsoft.com/windows)

In [OS](https://en.wikipedia.org/wiki/Operating_system) [Windows](https://www.microsoft.com/windows) [Graphviz app](https://graphviz.org/) can be installed via:

 * Manual install from [official website](https://graphviz.org/download/);
 * [chocolatey](https://community.chocolatey.org/packages/Graphviz) (needs to install it first, **plus** `choco.exe` needs to be in the [`PATH` environment variable](https://en.wikipedia.org/wiki/PATH_(variable))):

```bash
CHOCO.EXE install graphviz
```


### [Ubuntu](https://ubuntu.com/)

In [OS](https://en.wikipedia.org/wiki/Operating_system) [Ubuntu](https://ubuntu.com/) [Graphviz app](https://graphviz.org/) can be installed via two simple [commands](https://en.wikipedia.org/wiki/Bash_(Unix_shell)):

```shell
$ sudo apt update -y && sudo apt upgrade -y
$ sudo apt-get install graphviz libgraphviz-dev pkg-config -y
```


## [Building](https://en.wikipedia.org/wiki/Software_build)

### [Visual Studio Code](https://code.visualstudio.com/) (VS Code)

 1. Open this repository root folder as project;
 1. Press `Ctrl+Shift+B` to build.

### Automatic (via scripts)

#### [Windows](https://www.microsoft.com/windows)

 * Run (Double-click of [LMB](https://en.wikipedia.org/wiki/LMB)) `./scripts/compile.bat` to build (will closes immediately in end).

#### [Ubuntu](https://ubuntu.com/)

 * Run `./scripts/compile.sh` to build (will closes immediately in end).

### Manual

#### [Windows](https://www.microsoft.com/windows)

 1. Open bash (cmd.exe) in this project directory;
 1. Type next commands:

```bash
DOT.EXE -Tsvg builds_all.dot > builds_all.svg
DOT.EXE -Tpng builds_all.dot > tree.png
```

Where keys is:
 1. `-T***` - mode (example: `-Tsvg`, `-Tpng`);
 1. `tree` before `>` symbol - input file name;
    * `.***` before `>` symbol - input file name extension (example: `.dot`);
 2. `tree` after `>` symbol - output file name;
    * `.***` after `>` symbol - output file name extension (example: `.svg`, `.png`) [(more)](https://graphviz.org/docs/outputs/).

Graphviz without specify path will output files in current directory.

But you can specify path like in next examle:

```bash
DOT.EXE -Tsvg "./src/builds_all.dot" > "./out/builds_all.svg"
DOT.EXE -Tpng "./src/builds_all.dot" > "./out/tree.png"
```

More information can be founded on the [official website](https://graphviz.org/doc/info/command.html).

#### [Ubuntu](https://ubuntu.com/)

 1. Open shell in this project directory;
 1. Type next commands:

```shell
dot -Tsvg builds_all.dot > builds_all.svg
dot -Tpng builds_all.dot > tree.png
```

Where keys is:
 1. `-T***` - mode (example: `-Tsvg`, `-Tpng`);
 1. `tree` before `>` symbol - input file name;
    * `.***` before `>` symbol - input file name extension (example: `.dot`);
 2. `tree` after `>` symbol - output file name;
    * `.***` after `>` symbol - output file name extension (example: `.svg`, `.png`) [(more)](https://graphviz.org/docs/outputs/).

Graphviz without specify path will output files in current directory.

But you can specify path like in next examle:

```shell
dot -Tsvg ".\\src\\builds_all.dot" > ".\\out\\builds_all.svg"
dot -Tpng ".\\src\\builds_all.dot" > ".\\out\\tree.png"
```

More information can be founded on the [official website](https://graphviz.org/doc/info/command.html).

---
