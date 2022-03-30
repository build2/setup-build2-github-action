# setup-build2

This action provides setup routines to use [build2](https://build2.org) with GitHub Workflows.
Currently Linux, MacOS and Windows based runners are supported.

## Usage

After using the setup-build2 action all build2 related command line tools - like `b` or `bdep` - are available within your runner.

```yaml
steps:
- uses: actions/checkout@v2
- uses: Rookfighter/setup-build2@v2
- run: bdep init -C @gcc cc config.cxx=g++
- run: b
- run: b test
```
