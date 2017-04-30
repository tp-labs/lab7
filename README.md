## Laboratory work VII

Данная лабораторная работа посвещена изучению систем документирования исходного кода на примере **Doxygen**

```bash
$ open https://www.stack.nl/~dimitri/doxygen/manual/index.html
```

## Tasks

- [ ] 1. Создать публичный репозиторий с названием **lab7** на сервисе **GitHub**
- [ ] 2. Выполнить инструкцию учебного материала
- [ ] 3. Ознакомиться со ссылками учебного материала

## Tutorial

```bash
$ export GITHUB_USERNAME=<имя_пользователя>
```

```bash
$ git clone https://github.com/${GITHUB_USERNAME}/lab6 lab7
$ cd lab7
$ git remote remove origin
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab7
```

```bash
$ mkdir docs
$ doxygen -g docs/doxygen.conf
$ nano docs/doxygen.conf
```

```bash
$ sed -i '' 's/\(PROJECT_NAME.*=\).*$/\1 printf/g' docs/doxygen.conf
$ sed -i '' 's/\(EXAMPLE_PATH.*=\).*$/\1 examples/g' docs/doxygen.conf
$ sed -i '' 's/\(INCLUDE_PATH.*=\).*$/\1 examples/g' docs/doxygen.conf
$ sed -i '' 's/\(INPUT *=\).*$/\1 README.md include/g' docs/doxygen.conf
$ sed -i '' 's/\(USE_MDFILE_AS_MAINPAGE.*=\).*$/\1 README.md/g' docs/doxygen.conf
$ sed -i '' 's/\(OUTPUT_DIRECTORY.*=\).*$/\1 docs/g' docs/doxygen.conf
```

```bash
$ git add .
$ git commit -m"added doxygen.conf"
$ git push origin master
```

```
$ doxygen docs/doxygen.conf
$ ls | grep "[^docs]" | xargs rm -rf
$ mv docs/html/* . && rm -rf docs
$ git checkout -b gh-pages
$ git add .
$ git commit -m"added documentation"
$ git push origin gh-pages
$ git checkout master
```

```bash
$ mkdir artifacts && cd artifacts
$ screencapture -T 10 screenshot.jpg
<Command>-T
$ open https://${GITHUB_USERNAME}.github.io/lab7
```

## Links

- [HTML](https://ru.wikipedia.org/wiki/HTML)
- [LAΤΕΧ](https://ru.wikipedia.org/wiki/LaTeX)
- [man](https://ru.wikipedia.org/wiki/Man_(%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0_Unix))
- [CHM](https://ru.wikipedia.org/wiki/HTMLHelp)
- [PostScript](https://ru.wikipedia.org/wiki/PostScript)
