# Clue

Clue is an ANSI C compiler that targets high level languages. It suppports ANSI C (C89 and some C99) and compiles to languages like Lua and JavaScript. See the [Clue homepage](http://cluecc.sourceforge.net/) for more information.

## Usage

Clue is not a super polished piece of software, so running it (and the code it generates) requires a bit of setup. `clue` itself is installed to `/opt/clue`. To run the compiler, go to `/opt/clue`, where a program can be compiled like

```
./bin/clue -mc test/helloworld.c >compiled.c
```

This sample line compiles C to C. Running programs compiled by `clue` is done from `/opt/clue` using the `cluerun` script:

```
./cluerun -f compiled.c
```

Which will compile `compiled.c` using `gcc` and run the resulting executable.