# LLDB Tutorial

## Access to help files
```
(lldb) help
(lldb) help <commmand>
(lldb) help <command> <subcommand>
```

## Run a program using LLDB
```
lldb <program> <program_parameters>
(lldb) run
```
Alternatively, you could do:

```
lldb
(lldb) file <program_path>
(lldb) run
```

## Breakpoints
### To set a breakpoint to a line in a file
```
(lldb) breakpoint set --file <file> --line <number>
```

### To set a breakpoint to a function or several functions at a time
```
(lldb) breakpoint set --name foo --name bar
```

### To set a breakpoint to a C++ method
```
(lldb) breakpoint set --method foo
```

## Walking on the program
### Go to next instruction
```
(lldb) thread step-over
(lldb) next
(lldb) n
```

### Step into an instruction
```
(lldb) thread step-in
(lldb) step
(lldb) s
```

### Step out an instruction
```
(lldb) thread step-out
(lldb) finish
(lldb) f
```

## Examining variables and expressions
### Inspecting all frame's argument and local variables
```
(lldb) frame variable
```

### Inspecting a specific variable
```
(lldb) frame variable <variable_name>
```

### Evaluates an expression
```
(lldb) expression <expression_to_evaluate>
```

Example: `(lldb) expression a_string.length()`

## Backtrace
```
(lldb) thread backtrace
```

## Set alias to common commands
For example, to set `bfl` as an alias to command `breakpoint set --file <file> --line <line>`:
```
(lldb) command alias bfl breakpoint set --file %1 --line %2
```

To remove an alias you do:
```
(lldb) command unalias <alias>
```

As you're going to loose your alias when you terminate lldb programa, you can store them in the `~/.lldbinit` file to
be loaded by `lldb` when it starts.
