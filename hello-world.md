# Hello World

## Set-up Created files

* main.c 
* meson.build 

Contents of _meson.build_ file

```text
project('tutorial', 'c')
executable('demo', 'main.c')
```

### Create Build directory

```bash
$ meson builddir
The Meson build system
Version: 0.48.1
Source dir: /Users/Niall/Documents/programming/meson_test/hello_world
Build dir: /Users/Niall/Documents/programming/meson_test/hello_world/builddir
Build type: native build
Project name: tutorial
Project version: undefined
Native C compiler: cc (clang 10.0.0 "Apple LLVM version 10.0.0 (clang-1000.11.45.5)")
Build machine cpu family: x86_64
Build machine cpu: x86_64
Build targets in project: 1
Found ninja-1.6.0 at /usr/local/bin/ninja
```

```text
project(project_name, list_of_languages, ...)
```

* project name - any string; doesn't appear to be used but stored in manifest 
* languages \(of interest to us\) - c, cpp

### File structure: 

```bash
$ tree
.
├── builddir
│ ├── build.ninja
│ ├── compile_commands.json
│ ├── meson-logs
│ │ └── meson-log.txt
│ └── meson-private
│ ├── build.dat
│ ├── coredata.dat
│ ├── install.dat
│ ├── meson.lock
│ ├── meson_benchmark_setup.dat
│ ├── meson_test_setup.dat
│ ├── sanitycheckc.c
│ └── sanitycheckc.exe
├── main.c
└── meson.build

3 directories, 13 files
```

### Build

```bash
$ cd builddir/
$ ninja
[2/2] Linking target demo.
```

Build dir structure

```text
$ tree
.
├── build.ninja
├── compile_commands.json
├── demo
├── demo@exe
│ └── main.c.o
├── meson-logs
│ └── meson-log.txt
└── meson-private
├── build.dat
├── coredata.dat
├── install.dat
├── meson.lock
├── meson_benchmark_setup.dat
├── meson_test_setup.dat
├── sanitycheckc.c
└── sanitycheckc.exe

3 directories, 13 files
```

### Run

```bash
$ ./demo
Hello there.
```

### Clean

```bash
$ ninja clean
```

### Logfile

```bash
$ more meson-logs/meson-log.txt
Build started at 2018-11-02T14:58:37.564209
Main binary: /Library/Frameworks/Python.framework/Versions/3.7/bin/python3.7
Python system: Darwin
The Meson build system
Version: 0.48.1
Source dir: /Users/Niall/Documents/programming/meson_test/hello_world
Build dir: /Users/Niall/Documents/programming/meson_test/hello_world/builddir
Build type: native build
Project name: tutorial
Project version: undefined
Sanity testing C compiler: cc
Is cross compiler: False.
Sanity check compiler command line: cc /Users/Niall/Documents/programming/meson_test/hello_world/builddir/meson-private/sanitycheckc.c -o /Users/Niall/Documents/programming/meson_test/hello_world/builddir/meson-private/sanitycheckc.exe
Sanity check compile stdout:

-----
Sanity check compile stderr:

-----
Running test binary command: /Users/Niall/Documents/programming/meson_test/hello_world/builddir/meson-private/sanitycheckc.exe
Native C compiler: cc (clang 10.0.0 "Apple LLVM version 10.0.0 (clang-1000.11.45.5)")
Build machine cpu family: x86_64
Build machine cpu: x86_64
Build targets in project: 1
Found ninja-1.6.0 at /usr/local/bin/ninja
Running compile:
Working directory: /var/folders/tf/jrgp3xgn6v513wl8d80q08sh0000gn/T/tmposvk66ab
Command line: cc /var/folders/tf/jrgp3xgn6v513wl8d80q08sh0000gn/T/tmposvk66ab/testfile.c -pipe -c -o /var/folders/tf/jrgp3xgn6v513wl8d80q08sh0000gn/T/tmposvk66ab/output.obj -O0 --print-search-dirs

Code:

Compiler stdout:
programs: =/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin
libraries: =/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/10.0.0

Compiler stderr:
```

