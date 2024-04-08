# Ex-2 IMPLEMENTATION-OF-SYMBOL-TABLE
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char expression[20];
    int i = 0, x = 0, n, flag = 0;
    void *add[5];
    char d[15], c, srch;

    printf("Enter the Expression: ");
    scanf("%s", expression);

    n = strlen(expression);

    printf("Given Expression: %s\n", expression);

    printf("Symbol Table\n");
    printf("Symbol\taddr\ttype\n");
    while (i < n)
    {
        c = expression[i];
        if (isalpha(c))
        {
            add[x] = &expression[i];
            d[x] = c;
            printf("%c\t%p\tidentifier\n", c, (void *)&expression[i]);
            x++;
        }
        i++;
    }

    printf("\nThe symbol to be searched: ");
    scanf(" %c", &srch);
    for (i = 0; i < x; i++)
    {
        if (srch == d[i])
        {
            printf("\nSymbol Found");
            printf("\n%c\t@address %p\n", srch, (void *)add[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("\nSymbol Not Found");

    return 0;
}

```
# OUTPUT
<img width="254" alt="image" src="https://github.com/manomadhivanan/IMPLEMENTATION-OF-SYMBOL-TABLE-/assets/115543366/7b555891-a37b-4c77-9911-6169b6ce0965">

# RESULT
### The program to implement a symbol table is executed and the output is verified.
