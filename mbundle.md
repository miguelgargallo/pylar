For a Pylar language bundle file, mbundle.md, we include the following information:

# Pylar Language Bundle

## File Types

Pylar files are saved with the .pylar extension.

## Syntax Highlighting

Pylar code can be highlighted using the following scopes:

- keyword.control.pylar
- keyword.operator.pylar
- keyword.other.pylar
- support.function.pylar
- support.type.pylar
- constant.language.pylar
- string.quoted.single.pylar

## Snippets

Pylar includes the following snippets:

### If statement

```pylar
ifis ${1:condition}:
    ${2:code block}
```

For loop

```pylar
for ${1:variable} in ${2:iterable}:
    ${3:code block}
```

While loop

```pylar
while ${1:condition}:
    ${2:code block}
```

Function definition

```pylar
fn ${1:function_name}(${2:arguments}):
    ${3:code block}
```

Class definition

```pylar
class ${1:class_name}:
    ${2:code block}
```

Keybindings

Pylar includes the following keybindings:

```pylar
    shift+enter: Execute code block
    ctrl+/: Comment/uncomment code block
    ctrl+]: Indent code block
    ctrl+[: Outdent code block
```

For a Pylar language grammar file, `grammar.md`, you may include the following information:

Pylar Language Grammar
Keywords

    ifis: used to specify a condition in an if statement
    else: used to specify an else block in an if statement
    for: used to specify a for loop
    while: used to specify a while loop
    fn: used to define a function
    class: used to define a class
    import: used to import a module
    global: used to specify a global variable
    nonlocal: used to specify a nonlocal variable
    and: used to specify multiple variables in a for loop
    also: used to specify multiple variables in a for loop
    now: used to execute the code block in a loop or conditional statement
    small: used to find the smallest element in a list or collection
    is: used to check if a variable is present in a list or collection
    range: used to specify a range of values in a for loop
    not: used to negate a condition in an if statement
    =: used to assign a value to a variable or to check for equality in a condition
    to: used to specify a range of values in a for loop
    bye: used to break out of a loop
    rest: used to continue to the next iteration of a loop
    say: used to print output to the console
