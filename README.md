*This project has been created as part of the 42 curriculum by zben-ham.*

# Libft

## Description

Libft is my first project in the 42 curriculum: a static C library (`libft.a`) that reimplements a selection of standard libc functions, adds some extra utility functions, and provides a small linked list API. The goal is to understand how these functions work internally, and to build a toolbox that I can reuse in my future C projects.

The library is written in C, follows the 42 Norm, and is compiled with `-Wall -Wextra -Werror`. It uses no global variables and has no memory leaks.

### Library content

**Part 1: libc functions** (same prototypes and behavior as the originals, with the `ft_` prefix)

| Group | Functions |
|---|---|
| Character checks | `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint` |
| Case conversion | `ft_toupper`, `ft_tolower` |
| Strings | `ft_strlen`, `ft_strlcpy`, `ft_strlcat`, `ft_strchr`, `ft_strrchr`, `ft_strncmp`, `ft_strnstr`, `ft_atoi` |
| Memory | `ft_memset`, `ft_bzero`, `ft_memcpy`, `ft_memmove`, `ft_memchr`, `ft_memcmp` |
| Allocation | `ft_calloc`, `ft_strdup` |

**Part 2: additional functions**

| Function | Description |
|---|---|
| `ft_substr` | Returns a substring of a string. |
| `ft_strjoin` | Returns the concatenation of two strings. |
| `ft_strtrim` | Removes a set of characters from both ends of a string. |
| `ft_split` | Splits a string into an array of words using a delimiter. |
| `ft_itoa` | Converts an integer to a string. |
| `ft_strmapi` | Applies a function to each character and builds a new string. |
| `ft_striteri` | Applies a function to each character of a string, in place. |
| `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd` | Write a character, string, string with newline, or integer to a file descriptor. |

**Part 3: linked list** (uses the `t_list` structure)

`ft_lstnew`, `ft_lstadd_front`, `ft_lstsize`, `ft_lstlast`, `ft_lstadd_back`, `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`

### Technical choices

- `ft_calloc` returns a pointer that can be freed when `count` or `size` is 0, and checks that `count * size` does not overflow.
- `ft_split` frees everything it allocated if one allocation fails, and the same goes for `ft_lstmap`.
- Helper functions are `static`, so they only exist in their own file.

## Instructions

**Compile the library** (from the root of the repository):

```sh
make
```

This creates `libft.a`. Running `make` again does nothing if no file changed.

**Other rules:**

```sh
make clean    # removes the object files
make fclean   # removes the object files and libft.a
make re       # fclean, then all
```

**Use it in a program:**

```c
#include "libft.h"
```

```sh
cc -Wall -Wextra -Werror main.c -L. -lft -o program
```

## Resources

- The `man` pages of the original functions (`man 3 strlcpy`, `man 3 memmove`, ...)
- The 42 Norm
- The Libft subject (v19.0)

### Use of AI

AI was used as a learning tool: to explain concepts, to review my code for bugs and Norm errors, and, for some functions, to provide code that I studied and traced by hand.