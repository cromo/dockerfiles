# OCLint

A linting tool for C, C++, and Objective C.

## Usage

```sh
$ docker run --rm -it -v $(pwd):/source cromo/oclint
```

Within the container, both `oclint` and `oclint-json-compilation-database` are on the path. See [OCLint's primary documentation](http://docs.oclint.org/en/dev/) for further usage.