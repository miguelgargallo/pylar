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

# Syntax highlighting for .pylar files

## File extensions

- .pylar

## Filename patterns

- \*.pylar

## First-line patterns

- #!\*/usr/bin/env pylar

## MIME types

- text/x-pylar

## Scope names

- source.pylar
