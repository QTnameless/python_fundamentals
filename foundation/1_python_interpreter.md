# 1. Using the Python Interpreter

## 1️⃣.1️⃣ Invoking the Interpreter

* The Python interpreter is usually installed as `/usr/local/bin/python<version>` on the machine where it is available.

👉 **To launch python, use :**

```console
py
```

or
```console
python
```
👈 **To exit python**, use ***Ctrl + D*** (for Unix) or ***Ctrl + Z*** (for Windows) to exit without a exit status.

Or you can use this command for exiting interpreter :

```python
>>> quit()
```

* The interpreter operates when called with a file name argument or with a file with standard input can read and executes a script from that file

</br>

* **A second way** to start the interpreter in Python :

```console
python -c <command> [arg] ...

# arg is could be script file name
```

which executes the statements in `command`, analogous (tương tự) to the shell's `-c` option. (The `command` should be quote with  a **\`single quote\`**.)

* Some Python modules are also useful as script. They can be invoked when running by : 

```console
python -m <module> [arg] ...

# The module must be spelled out in the full name
```

* It would be very useful to be to **enter interactive mode** after running a script, do it with :

```console
python -i [arg] 

# -i before script file name
```

### **1️⃣.1️⃣.1️⃣ Argument Passing**

When known to the interpreter, the script name and additional arguments thereafter are turned into **a list of strings** and assigned to the `argv` variable in the `sys` module, which can be access by executing `import sys`. 

* The length of the list is **at least one** (no script and no arguments are given) 

```python
sys.argv[0] = ``  # Empty string
```  

* When the script name is given as `-` (standard input) 

```python
sys.argv[0] = '-'
``` 

* When `-c` command is used 

```python
sys.argv[0] = '-c'
```

* When `-m` module is used, 

```python
sys.argv[0] = 'module fullname' # located module
```

***Options found after `-c` command or `-m` module are not consumed by the Python interpreter’s option processing but left in `sys.argv` for the command or module to handle.***

### **1️⃣.1️⃣.2️⃣ Interactive mode**

When commands are read from a tty, the interpreter is said to be in ***interactive mode*** :
* In this mode it prompts for the next command with the primary prompt, usually three greater-than signs `>>>`
* For continuation lines it prompts with the secondary prompt, by default three dots `...`. 

Example:

```python
>>> the_world_is_flat = True
>>> if the_world_is_flat:
...     print("Be careful not to fall off!")
...
# Be careful not to fall off!
```

## 1️⃣.2️⃣