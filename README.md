# C/C++ Translator for Minimalist Programming Language

## Overview

This project implements a translator for a minimalist programming language in C/C++. The language supports variable declarations, array definitions, assignments, decision structures (if-else), loops (while), print statements, and read statements. The goal is to generate equivalent C code from programs written in this minimalist language.

## Build

To build the translator, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/human416c6578/Translator.git
cd Translator
```

2. Create a build directory and navigate into it:

```bash
mkdir build
cd build
```

3. Generate build files with CMake:

```bash
cmake ..
```

4. Build the translator:

```bash
make
```

## Usage

After building the translator, you can run it with an input file:

```bash
./translator input_file.txt >> out.cpp
```

## Example

Suppose you have the following minimalist program in a file named `example.txt`:

```plaintext
# Example program
var x
var y[5]
x = 10
y[2] = x + 5
if x > 5
    print "x is greater than 5"
else
    print "x is not greater than 5"
end
while y[2] > 0
    print y[2]
    y[2] = y[2] - 1
end
```

Run the translator:

```bash
./Translator example.txt
```

The translated C code will be printed to the console.

## Implementation Details

### Lexer

The lexer processes the input script and converts it into a sequence of tokens. Tokens include keywords, identifiers, numbers, symbols, and more.

### Abstract Syntax Tree (AST)

The AST represents the hierarchical structure of the input program. It is generated by parsing the tokens obtained from the lexer.

### Translator

The translator converts the AST into equivalent C code. It handles variable declarations, assignments, control structures, and expressions.

### Main Program

The main program orchestrates the entire process by reading the input file, invoking the lexer and parser, generating the AST, and finally, translating the AST into C code.

## Extending the Language

To extend the supported features of the minimalist language, modify the lexer, AST, and translator accordingly. Ensure that the grammar rules are appropriately handled in the parser.

Feel free to contribute to this project by opening issues or pull requests.

## Grammar Rules

### Comments

- Comments start with the '#' symbol and continue until the end of the line.
  
  Example:
  ```plaintext
  # This is a comment
  ```

### Variable Declaration

- Variables are declared using the `var` keyword followed by the variable name.

  Example:
  ```plaintext
  var x
  ```

### Array Declaration

- Arrays are declared using the `var` keyword, followed by the array name and the number of elements in square brackets.

  Example:
  ```plaintext
  var y[5]
  ```

### Assignment

- Assignments are done using the assignment operator `=`.
  
  Example:
  ```plaintext
  x = 10
  y[2] = x + 5
  ```

### Decision (if-else)

- Decision structures are created using the `if`, `else`, and `end` keywords.
  
  Example:
  ```plaintext
  if x > 5
      # do something
  else
      # do something else
  end
  ```

### Loop (while)

- While loops are defined with the `while`, `end` keywords.

  Example:
  ```plaintext
  while y[2] > 0
      # loop body
  end
  ```

### Print Statement

- Print statements are formed using the `print` keyword followed by the variable or a string literal.

  Example:
  ```plaintext
  print "Hello World"
  ```

### Read Statement

- Read statements use the `read` keyword followed by the variable to store the input.

  Example:
  ```plaintext
  read x
  ```

### Expressions

- Arithmetic expressions can include variables, array elements, and numerical values. Supported operators are `+`, `-`, `*`, `/`.
  
  Example:
  ```plaintext
  y[2] = x + 5
  ```

### Relational and Logical Operators

- Relational operators (`>`, `<`, `==`) can be used in conditions for decision structures and loops.
- Logical operators (`|`, `&`) are supported for combining conditions.

  Example:
  ```plaintext
  if x > 5 && y[2] < 10
      # do something
  end
  ```

### Grouping with Parentheses

- Parentheses can be used to group expressions and control the order of evaluation.

  Example:
  ```plaintext
  if (x > 5) | (y[2] < 10)
      # do something
  end
  ```

### String Literals

- Strings can be included in print statements using double quotes.

  Example:
  ```plaintext
  print "Hello, World!"
  ```