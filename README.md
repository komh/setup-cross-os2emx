# setup-cross-os2emx
GitHub action to setup cross-os2emx

Example:
```
uses: komh/setup-cross-os2emx@v1
with:
  version: 1.2.0
  platform: linux-x64
```

* Possible values:
  * version: latest(default), 1.2.0 or later(See https://github.com/komh/cross-os2emx/tags)
  * platform: auto(default), linux-x64, macos-arm64, macos-x64

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
* v1.1.1 (20206/06/18)
  * Fixed include path for os2tk45

* v1.1.0 (2026/06/18)
  * Set env vars for cross-os2emx
    * `OS2EMX_PREFIX`, `OS2EMX_BINDIR`, `OS2EMX_INCLUDEDIR`, `OS2EMX_LIBDIR`, `OS2EMX_TARGET_PREFIX`, `OS2EMX_TARGET_BINDIR`, `OS2EMX_TARGET_INCLUDEDIR`, `OS2EMX_TARGET_LIBDIR`, `OS2EMX_MESON_CROSS_FILE_AOUT`, `OS2EMX_MESON_CROSS_FILE_OMF`, `OS2EMX_CMAKE_TOOLCHAIN_FILE`
  * Install `pthread` and `os2tk45` by default
  
* v1.0.0 (2026/06/17)
  * Initial release
