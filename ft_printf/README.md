# ft_printf

## Description
ft_printf is a project in the 1337 (42 Network) curriculum that requires students to recode the printf() function from the C standard library. This project deepens understanding of variadic functions, type conversions, and formatted output in C.

The implementation handles various format specifiers and flags, teaching students about:
- Variadic functions in C
- Format string parsing
- Type conversions and casting
- String and number formatting

## Usage

### Building the Library
To compile the library, use the Makefile provided:

```bash
# Compile all source files and create libftprintf.a
make

# Compile with all flags
make all
```

### Available Make Rules
- `make` or `make all` - Compiles all source files and creates the library archive (libftprintf.a)
- `make clean` - Removes all object files (.o)
- `make fclean` - Removes all object files and the library archive
- `make re` - Performs fclean followed by all (recompiles everything)

### Using the Library
After building, include the library in your C projects:

```c
#include "ft_printf.h"
```

Compile your project with:
```bash
cc your_file.c -L. -lftprintf -o your_program
```

### Example Usage
```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello %s!\n", "World");
    ft_printf("Number: %d\n", 42);
    ft_printf("Hex: %x\n", 255);
    return (0);
}
```

## Supported Conversions
- `%c` - Character
- `%s` - String
- `%p` - Pointer address
- `%d` / `%i` - Signed decimal integer
- `%u` - Unsigned decimal integer
- `%x` / `%X` - Hexadecimal (lowercase/uppercase)
- `%%` - Percent sign
