# A small Autotools-like configure script wrapper for the Meson build system.
This project is meant for other projects that want to use the powerful [Meson buildsystem](https://mesonbuild.com),
but have the more familiar and user-friendly interface of the [GNU build system](https://www.gnu.org/software/automake/manual/html_node/GNU-Build-System.html).

# How to use this in your meson project
Just copy the [configure](configure) file to the root of your project
and adjust the `PROJ_` variables at the top of the file.

# How it works
configure just reads the options and passes them to meson.
After that it generates a simple wrapper Makefile.

# TODO
- [x] Basic usability
- [ ] Parse the optional meson\_options.txt for the help screen
- [ ] Parse the name and version of the project (replace manual editing of PROJ_\* variables)
- [ ] Out-of-tree builds (eg. mkdir build; cd build; ../configure)
- [ ] Allow overwriting install paths when running make (eg. `make install prefix=/bin`)
- [ ] [config.site](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html\_node/Sharing-Defaults.html)
- [ ] configure options:
    - [x] -h, --help
    - [x] -V, --version
    - [x] -q, --quiet, --silent
    - [x] --prefix=
    - [ ] --exec-prefix=
    - [x] --bindir=
    - [x] --sbindir=
    - [x] --libexecdir=
    - [-] --sysconfdir= (needs --exec-prefix)
    - [-] --sharedstatedir=
    - [-] --localstatedir=
    - [x] --libdir=
    - [-] --includedir=
    - [-] --datadir=
    - [-] --infodir=
    - [-] --localedir=
    - [-] --mandir=
    - [ ] --build= (maybe not possible)
    - [ ] --host=
    - [ ] --target=
    - [ ] --program-prefix=
    - [ ] --program-suffix=
    - [ ] --program-transform-name=
    - [ ] -n, --no-create
    - [ ] --srcdir=
    - [ ] --help=short
    - [ ] --help=recursive
    - [ ] -c, --config-cache & --config-file= (if possible)
    - [ ] Allow passing environment variables (eg. `./configure CC='gcc'`)
- [ ] Makefile rules:
    - [x] all
    - [x] clean
    - [x] install
    - [ ] dist
    - [ ] help
    - [ ] full-clean -> distclean
    - [ ] check
    - [ ] installcheck
    - [ ] install-strip
    - [ ] uninstall
    - [ ] distcheck
