# meson\_exe\_wrapper.sh

form [https://hwengineer.github.io/TDD\_qemu\_meson/](https://hwengineer.github.io/TDD_qemu_meson/)

```text
#!/bin/sh
if [ $# = 1 ]; then
  qemu-system-arm -version #at meson startup it makes a testrun with exact 1 parameter
  exit $?
else
  qemu-system-arm -kernel "$@"
  exit $?
fi
```

this bash script need to be stored in a class path where meson-build can find it and call it.

