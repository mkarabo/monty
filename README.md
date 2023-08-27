# Monty Programming Language

Monty 0.98 is a scripting language that is designed to be compiled into Monty byte codes, similar to how Python code is compiled. It features a unique stack with specialized instructions for manipulating it. The primary objective of this project is to create an interpreter for Monty ByteCodes files.

## Monty Byte Code Files

Files containing Monty byte codes are usually named with the `.m` extension. While this naming convention is commonly used in the industry, it is not mandatory according to the language specification. Each line in a Monty byte code file contains only one instruction. The opcode and its argument may have any number of spaces before or after them. For example:

```plaintext
push 0$
push 1$
push 2$
  push 3$
                   pall    $
push 4$
    push 5    $
      push    6        $
pall$
```

Blank lines in Monty byte code files are allowed, and any additional text following the opcode or its required argument is disregarded. Here's an example:

```plaintext
push 0 Push 0 onto the stack$
push 1 Push 1 onto the stack$
$
push 2$
  push 3$
                   pall    $
$
$
                           $
push 4$
$
    push 5    $
      push    6        $
$
pall This is the end of our program. Monty is awesome!$
```

## Usage

To compile the Monty interpreter, use the following command:

```shell
gcc -Wall -Werror -Wextra -pedantic *.c -o monty
```

To run the interpreter, use the following command:

```shell
./monty bytecode_file
```

## Available Opcodes

The following operation codes (opcodes) are available for use in Monty byte code files:

| Opcode | Description |
|--------|-------------|
| push   | Pushes an element onto the stack (e.g., `push 1` pushes 1 onto the stack). |
| pall   | Prints all values on the stack, starting from the top. |
| pint   | Prints the value at the top of the stack. |
| pop    | Removes the top element from the stack. |
| swap   | Swaps the top two elements on the stack. |
| add    | Adds the top two elements on the stack, storing the result in the second node. |
| nop    | No operation; does nothing. |
| sub    | Subtracts the second top element from the top element, storing the result in the second node. |
| div    | Divides the second top element by the top element, storing the result in the second node. |
| mul    | Multiplies the second top element by the top element, storing the result in the second node. |
| mod    | Computes the remainder of the second top element divided by the top element, storing the result in the second node. |
| #      | Indicates a comment; the line is ignored. |
| pchar  | Prints the ASCII value of the integer at the top of the stack. |
| pstr   | Prints a string of ASCII values until reaching 0, the end of the stack, or a non-ASCII value. |
| rotl   | Rotates the top element to the bottom of the stack. |
| rotr   | Rotates the bottom element to the top of the stack. |
| stack  | Sets the stack format (default behavior). |
| queue  | Sets the queue format. |

Feel free to use this information as a starting point for creating a clear and organized README file for your Monty interpreter project!
