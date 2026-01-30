# Libft

## Description
Libft is the first project in the 1337 (42 Network) curriculum. It focuses on creating a custom C library by recoding several standard C library functions. This project helps students understand how basic C functions work internally and builds a foundation for future projects.

The library includes functions for:
- Character checking and manipulation
- String manipulation
- Memory management
- Linked list operations

## Usage

### Building the Library
To compile the library, use the Makefile provided:

```bash
# Compile all source files and create libft.a
make all
```

### Available Make Rules
- `make` or `make all` - Compiles all source files and creates the library archive (libft.a)
- `make clean` - Removes all object files (.o)
- `make fclean` - Removes all object files and the library archive
- `make re` - Performs fclean followed by all (recompiles everything)

### Using the Library
After building, include the library in your C projects:

```c
#include "libft.h"
```

Compile your project with:
```bash
cc your_file.c -L. -lft -o your_program
```

## Functions Included
The library includes implementations of the following functions:
- `ft_atoi`, `ft_bzero`, `ft_calloc`
- `ft_isalnum`, `ft_isalpha`, `ft_isascii`, `ft_isdigit`, `ft_isprint`
- `ft_memchr`, `ft_memcmp`, `ft_memcpy`, `ft_memmove`, `ft_memset`
- `ft_strchr`, `ft_strdup`, `ft_strlcat`, `ft_strlcpy`, `ft_strlen`
- `ft_strncmp`, `ft_strnstr`, `ft_strrchr`
- `ft_tolower`, `ft_toupper`