LXD debian package
======

This repository contains `debian/` directory of source package for LXD.  
It was derived from `debian/` directory in [lxd-pkg-ubuntu ](https://github.com/lxc/lxd-pkg-ubuntu/) so many thanks to LXD contributors.

# Notes

You will need some golang 1.17 installed.

You don't need libraft and libdqlite installed (in fact you can't) as this package builds raft and dqlite that are bundled with LXD releases.

# Compilation

Download LXD [source release tarball](https://github.com/lxc/lxd/releases).

```
wget https://github.com/lxc/lxd/releases/download/lxd-4.24/lxd-4.24.tar.gz
```

Rename source tarball.

```
mv lxd-4.24.tar.gz lxd_4.24.orig.tar.gz
```

Unpack source tarball.

```
tar -xf lxd_4.24.orig.tar.gz
```

Change working directory to unpacked sources

```
cd lxd-4.24/
```

Clone lxd-pkg-debian repository into `debian/`

```
git clone https://github.com/fihufil/lxd-pkg-debian.git debian
```

Make sure you have all the build-deps from `debian/control` installed.

Now you can build the package!

```
dpkg-buildpackage -us -uc
```

Enjoy your fresh packages!

# TODO

* 
