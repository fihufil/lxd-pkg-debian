LXD debian package
======

This repository contains `debian/` directory of source package for LXD.  
It was derived from `debian/` directory in [lxd-pkg-ubuntu ](https://github.com/lxc/lxd-pkg-ubuntu/) so many thanks to LXD contributors.

# Compilation

Download LXD [source release tarball](https://github.com/lxc/lxd/releases).

```
wget https://github.com/lxc/lxd/releases/download/lxd-4.0.4/lxd-4.0.4.tar.gz
```

Rename source tarball.

```
mv lxd-4.0.4.tar.gz lxd_4.0.4.orig.tar.gz
```

Unpack source tarball.

```
tar -xf lxd_4.0.4.orig.tar.gz
```

Change working directory to unpacked sources

```
cd lxd-4.0.4/
```

Clone lxd-pkg-debian repository into `debian/`

```
git clone https://github.com/rapidrage/lxd-pkg-debian.git debian
```

Make sure you have all the build-deps from `debian/control` installed.

Now you can build the package!

```
dpkg-buildpackage -us -uc
```

Enjoy your fresh packages

# TODO

* Allow for go packages to come from debian packages (i.e. use `USE_BOUNDLED_LIBS` in `rules` file)
