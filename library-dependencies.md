# Library dependencies

```text
thread_dep = dependency('threads')

executable('app', [src] , include_directories : [incdir], dependencies : thread_dep)
```



