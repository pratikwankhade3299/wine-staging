Deprecation Notice - important Information
------------------

As of February 2018, the Wine Staging project has been discontinued by the original
maintainers. Alistair Leslie-Hughes has volunteered to continue the project
at his own [GitHub repository](https://github.com/wine-staging/wine-staging).

What is Wine Staging?
---------------------

**Wine Staging** is the testing area of winehq.org. It contains bug fixes and
features, which have not been integrated into the development branch yet. The
idea of Wine Staging is to provide experimental features faster to end users and
to give developers the possibility to discuss and improve their patches before
they are integrated into the main branch. More information about Wine Staging
can also be found at [winehq.org](https://www.winehq.org).

Installation
------------

Ready-to-use packages for Wine Staging are available for a variety of Linux
distributions and for Mac OS X. Just follow the
[installation instructions](https://wiki.winehq.org/Download)
for your operating system.

On most distributions the `wine-staging` package is installed to
`/opt/wine-staging`, such that multiple Wine versions can be installed in
parallel. If this is the case for your distribution, you will have to type
`/opt/wine-staging/bin/wine` instead of just `wine`. The same also applies for
other wine-specific programs like `winecfg`. To learn more about how to use
Wine Staging, please take a look at the
[usage instructions](https://github.com/wine-compholio/wine-staging/wiki/Usage).

Building
--------

Wine Staging is maintained as a set of patches which has to be applied on top of
the development branch. In order to build Wine Staging, the first step is to
setup a build environment for Wine, including all required dependencies. A lot
of information about that is collected in the
[WineHQ Wiki](http://wiki.winehq.org/BuildingWine).

In order to apply all Wine Staging patches it is recommended to use the
`patchinstall.sh` utility which takes care of applying all patches in the
correct order. For reference, the possible commandline arguments are:

```
Usage: ./patchinstall.sh [DESTDIR=path] [--all] [-W patchset] [patchset ...]

Autogenerated script to apply all Wine Staging patches on your Wine
source tree.

Configuration:
  DESTDIR=path         Specify the path to the wine source tree
  --all                Select all patches
  --force-autoconf     Run autoreconf and tools/make_requests after each patch
  --help               Display this help and exit
  --no-autoconf        Do not run autoreconf and tools/make_requests
  --no-patchlist       Do not apply patchlist (needed for 'wine --patches')
  --upstream-commit    Print the upstream Wine commit SHA1 and exit
  --version            Show version information and exit
  -W patchset          Exclude a specific patchset

Backends:
  --backend=patch      Use regular 'patch' utility to apply patches (default)
  --backend=eapply     Use 'eapply' to apply patches (Gentoo only)
  --backend=epatch     Use 'epatch' to apply patches (Gentoo only, deprecated)
  --backend=git-am     Use 'git am' to apply patches
  --backend=git-apply  Use 'git apply' to apply patches
  --backend=stg        Import the patches using stacked git
```

If you want to apply *all* patches with the `patch` utility, the commandline
should look similar to this:
```
./patches/patchinstall.sh DESTDIR="/path/to/wine" --all
```

Before you proceed with the compilation, please make sure that you installed all
additional build dependencies required for the Wine Staging features you are
interested in (check output of `./configure`). More information about building
Wine Staging, optional build dependencies, and hints for packagers are collected
in our [Wiki](https://github.com/wine-compholio/wine-staging/wiki/Packaging).

Contributing
------------

Please see CONTRIBUTING.md for more information about contributing to Wine
Staging.
