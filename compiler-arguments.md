# Compiler Arguments



### Global arguments <a id="global-arguments"></a>

```text
add_global_arguments('-DFOO=bar', language : 'c')
```

Global arguments have certain limitations. They all have to be defined before any build targets are specified. 

You should set only the most essential flags with this setting, you should _not_ set debug or optimization flags. Instead they should be specified by selecting an appropriate build type.

### Project arguments <a id="project-arguments"></a>

```text
add_project_arguments('-DMYPROJ=projname', language : 'c')
```

### Per target arguments <a id="per-target-arguments"></a>

```text
executable('prog', 'prog.cc', cpp_args : '-DCPPTHING')
```

Here we create a C++ executable with an extra argument that is used during compilation but not for linking.

| C | c\_args |
| :--- | :--- |
| C++ | cpp\_args |

```text
executable('prog', 'prog.cc', link_args : '-Wl,--linker-option')
```

Specifying extra linker arguments is done in the same way:

