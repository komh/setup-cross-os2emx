# setup-cross-os2emx

GitHub action to setup cross-os2emx

Example:
```
uses: komh/setup-cross-os2emx@v1
with:
  version: 1.2.0
  platform: linux-x64
```

*** **NOTE** *** Since `setup-cross-os2emx v1.2.0`, only `cross-os2emx v1.4.0` or later are supported.

* Possible values:
  * version: latest(default), 1.2.0 or later(See https://github.com/komh/cross-os2emx/tags)
  * platform: auto(default), linux-x64, macos-arm64, macos-x64
  * use-exp-rpm: true, false(default). Use experimental repo for RPMs, too.
  * rpm-arch: i386, i686, pentium4(default). See https://rpm.netlabs.org/release/00/pentium4/
              This applies to rpm-deps only
  * rpmzip-deps: package names of ZIP versions of RPMs used by installrpmzip
  * zip-deps: URLs for ZIPs used by installzip
  * rpm-deps: package names of RPMs used by installrpm

Example for `aout` mode of `meson`:
```
meson setup builddir -Dos2_emxomf=false --cross-file=$OS2EMX_MESON_CROSS_FILE_AOUT
```

If you omit `-Dos2_emxomf` option, `-Dos2_emxomf=false` is default.

Example for `omf` mode of `meson`:
```
meson setup builddir -Dos2_emxomf=true --cross-file=$OS2EMX_MESON_CROSS_FILE_OMF
```

Example for `cmake`:
```
cmake -S . -B builddir -G Ninja -DCMAKE_TOOLCHAIN_FILE=$OS2EMX_CMAKE_TOOLCHAIN_FILE
```

# History

* v1.2.0 (2026/07/23)
  * Added `use-exp-rpm`, `rpm-arch`, `rpmzip-deps`, `zip-deps`, and `rpm-deps` inputs
  * Set `PKG_CONFIG_LIBDIR` and `ACLOCAL_PATH`
  * Added workaround for missing `CMAKE_SYSTEM_PREFIX_PATH` in cmake tool chain file untili `cross-os2emx v1.4.0`
  * Since v1.2.0, only cross-os2emx v1.4.0 or later are supported

* v1.1.2 (2026/06/19)
  * Fixed libtoolize fails

* v1.1.1 (2026/06/18)
  * Fixed include path for os2tk45

* v1.1.0 (2026/06/18)
  * Set env vars for cross-os2emx
    * `OS2EMX_PREFIX`, `OS2EMX_BINDIR`, `OS2EMX_INCLUDEDIR`, `OS2EMX_LIBDIR`, `OS2EMX_TARGET_PREFIX`, `OS2EMX_TARGET_BINDIR`, `OS2EMX_TARGET_INCLUDEDIR`, `OS2EMX_TARGET_LIBDIR`, `OS2EMX_MESON_CROSS_FILE_AOUT`, `OS2EMX_MESON_CROSS_FILE_OMF`, `OS2EMX_CMAKE_TOOLCHAIN_FILE`
  * Install `pthread` and `os2tk45` by default

* v1.0.0 (2026/06/17)
  * Initial release

# Donation

If you are satisfied with this program and want to donate to me, please visit
the following URL.

https://www.os2.kr/komh/os2factory/

Or, please click the Ads in the following blog.

https://lvzuufx.blogspot.com/

# Contact

Please use the issue tracker of github:

https://github.com/komh/setup-cross-os2emx/issues

KO Myung-Hun
