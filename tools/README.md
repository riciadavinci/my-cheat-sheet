### Command Line Tools Cheatsheet
- [Git](#git)
- [Make & Makefiles](#make)
- [CMake](#cmake)
- [Valgrind](#valgrind)
- [GDB](#gdb)

---

#### Git <a name="git"></a>
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. 

---

#### Make & Makefiles <a name="make"></a>
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. 

---

#### CMake <a name="cmake"></a>
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. 


---

#### Valgrind <a name="valgrind"></a>
_Valgrind_ is a tool primarily used to check for memory leaks in C and C++ programs, but it also has other features. It is mostly used on Linux, but Windows and MacOS versions are avaliable. 

It's best to add the `-g` and `-Og` flags while compiling the source code, since it will help _Valgrind_ in general. Also, some optimisations may make it difficult for _Valgrind_ to find memory leaks, but usually it is good practice to run your compiled executable to check for leaks.

```bash
valgrind ./[executable_filename]
```
The above command will give only the number of allocs, number of frees and total memory allocated on the heap in bytes.

You can rerun it with `--leak-check=full` flag/option to see the see where the memory was allocated (line number in the source file), but you forgot to free it.

```bash
valgrind --leak-check=full ./[executable_filename]
```

It will also show us if we have used any un-initialized variables (i.e., we are using variables having garbage values). 

<br>

With the flag/option `--track-origins=yes` it is possible to track where an un-initialized memory/variable that we are trying to access was allocated on the stack/heap. 

```bash
valgrind --track-origins=yes ./[executable_filename]
```
<br>

We can use the tool `--tool=helgrind` _(helgrind)_ for detecting thread errors. It is basically a thread sanatizer that is used for detecting synchronisation errors in C,C++ and Fortran.

```bash
valgrind --tool=helgrind ./[executable_filename]
```
<br>

We can use the tool `--tool=memcheck` _(memcheck)_ for detecting memory errors. It is basically a memory and address sanatizer.

```bash
valgrind --tool=memcheck ./[executable_filename]
```

<br>

We can use the tool `--tool=callgrind` _(callgrind)_, which allows a stable way of testing the efficiency of our program. In short, it tells us the number of instructions that our program executed.

```bash
valgrind --tool=callgrind ./[executable_filename]
```

It also gives us the `callgrind.out` files (actually `callgrind.out.[pid]`, where `pid` is the process ID that was assigned when the program was executed, ex- `callgrind.out.4661`). These out files contain information such the number of times a function was called.

Another good GUI tool for Linux called `kcachegrind` takes these output files and displays which functions were executed, the memory usage, etc. in that tool.

```bash
kcachegrind [callgrind_out_file]
```

---

#### GDB <a name="gdb"></a>
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. 
