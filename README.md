# setup-build2

![License](https://img.shields.io/packagist/l/doctrine/orm.svg)
![build2](https://github.com/build2/setup-build2/actions/workflows/build2.yml/badge.svg)

This action provides setup routines to use [build2](https://build2.org) with GitHub Workflows.
Currently Linux, MacOS and Windows based runners are supported.

## Usage

After using the `setup-build2` action all `build2` related command line tools - like `b` or `bdep` - are available within your runner.

```yaml
steps:
- uses: actions/checkout@v2
- uses: build2/setup-build2@v2
- run: bdep init -C @gcc cc config.cxx=g++
- run: b
- run: b test
```

The action also provides parameters to customize the `build2` toolset for your runner:#

| option | description |
|--------|-------------|
| `build2-version` | Version of `build2` which should be installed. Default is `latest`. Can also be `staged` or a specific version like `0.14.0`. |
| `build2-windows-compiler` | Used in Windows runners only. Defines the compiler which is used to build `build2`. Default is `msvc`. Can also be `mingw` or `clang`. |


```
- uses: build2/setup-build2@v2
  with:
    build2-version: staged
    build2-windows-compiler: mingw
```