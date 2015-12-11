# molden
Compile molden to create a debian/ubuntu package

## Instructions

- Download molden from the website:

```
$ wget ftp://ftp.cmbi.ru.nl/pub/molgraph/molden/molden$VERSION.tar.gz
```

- Create a source that follows the debian policy:

```
$ tar zxvf molden$VERSION.tar.gz
$ mv molden$VERSION molden-$VERSION
$ tar cvf molden-5.4.tar molden-5.4 && gzip -9 molden-$VERSION.tar
```

- Now enter the directory where the package will be built, and copy the cloned
   `debian/` directory inside:

```
$ cd molden-$VERSION
$ cp -R $PATH/to/debian/directory .

```

- Install the dependencies:

```
# apt-get install debhelper gfortran libxmu-dev libxmuu-dev xutils-dev freeglut3-dev dpatch gcc-4.9 vim dpkg-dev
```

- Create the package:

```
$ dpkg-buildpackage
```

- The package is created in the parent directory. Now you can install the package using

```
# dpkg -i molden_$VERSION-$REVISION_amd64.deb
```
