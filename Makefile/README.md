- Name: `Makefile`
- `make` will always run first target it will find
- `all:` this target is used as standard as a first target in a fie. This act as main target which runs other targets. Use for basic info like help if only make command is executed
- Use `@` before any command to suppress its output to the terminal
- Use TABS only (not spaces) before each command
- Each command runs in its own shell. If you want to run multiple command to run in same shell use semicollons or external scripts
  ```
  target1:
    command1; command2; command3

  target2:
    ./myscript.sh
  ```
- The working dir is the same in which make is executed

## Variables
- There is no number all are strings
- some community standard ways to name var in *c language*
  - `CC`: program for compiling C programs; default cc
  - `CXX`: program for compiling C++ programs; default g++
  - `CFLAGS`: Extra flags to give to compiler
  - `CXXFLAGS`: Extra flags to give to the C++ compiler
  - `CPPFLAGS`: Extra flags to give to the C preprocessor
  - `LDFLAGS`: Extra flags to five to the linker
- `make -p`: to get the list of all predefined variables
#### Assignment rules
- `=` Lazy set, which means variable on right side are expanded at the point of its use with current value, not the one at the time of decleration. Overwrite previous value.
- `:=` immediate Set, simple one time expansion at the time of decleration
- `?=` only set variables if they have not been set. This is also Lazy set
- `+=` append

## Patterns
- $@: the file name of the target
- $<: the name of the first dependency
- $^: the names of all prerequisites
- $?: the name of all dependencies that are newer than the target

```makefile
%.o: %.cc
	$(CXX_COMPILER_CALL) -c $< -o $@
```

## Wildcard
```makefile
CXX_SOURCES = $(wildcard *.cc)
CXX_SOURCES = $(patsubst %.cc, %.o $(CXX_SOURCES))
```

## Conditional
Check if variable is empty `ifeq($(strip $(VAR)), )`

Check if a variable is defined `ifdef VAR`

-----------------
```makefile
include another_makefile.mk

.PHONY: target			# phony means that target is not a file or it is not dependent on any file. Useful for the case if target exist as a file and you want to run the command regardless of file is outdated or not
target: perquisites...			# perquisites are file names, separated by spaces
	command1
	command2

```
