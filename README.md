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
  * version: latest(default), 1.2.0
  * platform: auto(default), linux-x64, macos-arm64, macos-x64
  
# History
* v1.1.0 (2026/06/18)
  * Set env vars for cross-os2emx
    * `OS2EMX_PREFIX`, `OS2EMX_BINDIR`, `OS2EMX_INCLUDEDIR`, `OS2EMX_LIBDIR`, `OS2EMX_TARGET_PREFIX`, `OS2EMX_TARGET_BINDIR`, `OS2EMX_TARGET_INCLUDEDIR`, `OS2EMX_TARGET_LIBDIR`, `OS2EMX_MESON_CROSS_FILE_AOUT`, `OS2EMX_MESON_CROSS_FILE_OMF`, `OS2EMX_CMAKE_TOOLCHAIN_FILE`
  * Install `pthread` and `os2tk45` by default
  
* v1.0.0 (2026/06/17)
  * Initial release
