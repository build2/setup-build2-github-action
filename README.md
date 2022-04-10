# setup-build2

![License](https://img.shields.io/packagist/l/doctrine/orm.svg)
![build2](https://github.com/Rookfighter/setup-build2/actions/workflows/build2.yml/badge.svg)

This action provides setup routines to use [build2](https://build2.org) with GitHub Workflows.
Currently Linux, MacOS and Windows based runners are supported.

## Usage

After using the setup-build2 action all build2 related command line tools - like `b` or `bdep` - are available within your runner.

```yaml
steps:
- uses: actions/checkout@v2
- uses: Rookfighter/setup-build2@v1
- run: bdep init -C @gcc cc config.cxx=g++
- run: b
- run: b test
```
