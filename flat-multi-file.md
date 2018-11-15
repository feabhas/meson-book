# Flat Multi-file

File config:

```bash
.
├── main.c
├── meson.build
├── message.c
└── message.h
```

Set-up

```bash
$ meson builddir && cd builddir
The Meson build system
Version: 0.48.1
Source dir: /Users/Niall/Documents/programming/meson_test/multi-file/flat
Build dir: /Users/Niall/Documents/programming/meson_test/multi-file/flat/builddir
Build type: native build
Project name: how-to
Project version: undefined
Native C compiler: cc (clang 10.0.0 "Apple LLVM version 10.0.0 (clang-1000.11.45.5)")
Build machine cpu family: x86_64
Build machine cpu: x86_64
Build targets in project: 1
Found ninja-1.6.0 at /usr/local/bin/ninja
```

build

```text
$ ninja
[2/2] Linking target app.
```

run

```bash
$ ./app
Hello world
Hello world
Hello world
Hello world
Hello world
Hello world
Hello world
Hello world
Hello world
Hello world
```

meson.build file

```text
project('how-to', 'c')
src = ['main.c', 'message.c']
executable('app', src)
```



