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
- [x] Provide a builtin `which` implementation
- [ ] Parse the optional meson\_options.txt for the help screen
- [ ] Parse the name and version of the project (replace manual editing of PROJ_\* variables)
- [x] Out-of-tree builds (eg. mkdir build; cd build; ../configure)
- [ ] Allow overwriting install paths when running make (eg. `make install prefix=/bin`)
- [ ] [config.site](https://www.gnu.org/savannah-checkouts/gnu/autoconf/manual/autoconf-2.70/html\_node/Sharing-Defaults.html)
- [ ] configure options:
    - [x] Allow passing environment variables (eg. `./configure CC='gcc'`)
    - [x] -h, --help
    - [x] -V, --version
    - [x] -q, --quiet, --silent
    - [x] --prefix=
    - [x] --exec-prefix=
    - [x] --bindir=
    - [x] --sbindir=
    - [x] --libexecdir=
    - [x] --sysconfdir=
    - [x] --sharedstatedir=
    - [x] --localstatedir=
    - [x] --libdir=
    - [x] --includedir=
    - [x] --datadir=
    - [x] --infodir=
    - [x] --localedir=
    - [x] --mandir=
    - [x] --srcdir=
    - [x] -n, --no-create
    - [ ] --build= (maybe not possible)
    - [ ] --host=
    - [ ] --target=
    - [ ] --program-prefix=
    - [ ] --program-suffix=
    - [ ] --program-transform-name=
    - [ ] --help=short
    - [ ] --help=recursive
    - [ ] -c, --config-cache & --config-file= (if possible)
- [ ] Makefile rules:
    - [x] all
    - [x] clean
    - [x] install
    - [x] distclean
    - [x] uninstall
    - [x] dist
    - [x] check
    - [ ] help
    - [ ] installcheck
    - [ ] install-strip
    - [ ] distcheck
