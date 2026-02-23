<!--
    =====================================
    generator=datazen
    version=3.2.4
    hash=6024d9c4258ef34c533ffce0ab06062d
    =====================================
-->

# picolibc-semihost ([0.3.1](https://github.com/libre-embedded/picolibc-semihost/releases/tag/0.3.1))

[![codecov](https://codecov.io/gh/libre-embedded/picolibc-semihost/branch/master/graph/badge.svg)](https://codecov.io/gh/libre-embedded/picolibc-semihost)
![Build Status](https://github.com/libre-embedded/picolibc-semihost/actions/workflows/yambs-project.yml/badge.svg)

*A bare-metal picolibc-based bootstrapping environment.*

## Documentation

### Generated

* By [sphinx+breathe+exhale](https://vkottler.github.io/cpp/sphinx/picolibc-semihost/)
(What's [sphinx](https://www.sphinx-doc.org/en/master/) /
[breathe](https://breathe.readthedocs.io/en/latest/) /
[exhale](https://exhale.readthedocs.io/en/latest/)?)

## Workflow

Install [vmklib](https://github.com/libre-embedded/vmklib) such that you can
`mk --version` (a `pip install vmklib` to your desired Python environment is
all that's needed).

From a fresh checkout:

```
git submodule update --init
mk dz-sync
mk download-toolchains
mk g
```

This should result in fully compiled code that you can now use or add to.


### Generating Interfaces

Structs and enumerations can be defined for
[ifgen](https://github.com/libre-embedded/ifgen) which can then generate C++ source
code into the project.

Generating configurations based on an
[SVD](https://github.com/libre-embedded/ifgen/tree/master/ifgen/data/svd) file:

```
mk ifgen-svd-XMC4700
```

Generating code from an `ifgen.yaml` in the root directory of the project:

```
mk ifgen
```
