# C : foo, bar, baz
```c
#include <stdio.h>

int main(void)
{
    printf("hello world!\n");
}
```
## Types de variables / Data Types

| Nom du type                       | Minimum       | Maximum        |                         |
|-----------------------------------|---------------|----------------|-------------------------|
| signed char                       | -127          | 127            | 1 byte(8 bits)          |
| unsigned char                     | 0             | 255            |                         |
| (signed) int                      | -32 767       | 32 767         |                         |
| long (signed) int                 | 2 147 483 647 | -2 147 483 647 | integers 4bytes(32bits) |
| float (6 chiffres de précision)   | -1 x1037      | 1 x1037        | 4bytes (32 bits)        |
| double (15 chiffres de précision) | -1 x1037      | 1 x1037        | 8 bytes (64 bits)       |

* void is a type but not a data type. It means it doesn't return a value. More of a placeholder. Appelés "procédures"
* typedefs : defined types
### Structures
* structs
```c
typedef struct
{
    string name;
    string dorm;
}
student;
```
* Good practise : If the `struct` contains as a member a pointer to another such `struct`, declare the `struct` as having a name identical to the type, without using underscores:
```c
typedef struct node
{
    int n;
    struct node *next;
}
node;
```
## Afficher le contenu d'une variable

| Format                 | Type attendu | Rôle             |
|------------------------|--------------|------------------|
| "%d"                   | int          | entier           |
| "%ld", "%li"           | long         | entier signé     |
| "%f"                   | float        | float            |
| "%f", "%lf" pour scanf | double       | double           |
| "%c"                   | character    | character unique |
| %s                     | char         | string           |

## math.h

* fabs : valeur absolue d'un nombre **double**
```c
double absolu = 0, nombre = -27;  
absolu = fabs(nombre); // absolu vaudra 27
```
* ceil : nombre entier suivant
* floor : nombre entier précédent
* pow : puissance d'un nombre
* sqrt : racinée carée
* sin, cos, tan : double et en radian
* exp : exponentielle
* log : logarithme
* log 10

## Conditions

| Symbole | Signification           |
|---------|-------------------------|
| ==      | est égal à              |
| >       | est supérieur à         |
| <       | est inférieur à         |
| >=      | est supérieur ou égal à |
| <=      | est inférieur ou égal à |
| !=      | est différent de        |

* if ... else
```c
int x;
if (expr)
{
    x = 5;
}
else
{
    x = 6;
}
```
devient
```c
int x = (expr) ? 5 : 6;
```
* else if
* switch()
    * you can remove the break if you need it in certain cases
        ```c
switch (n)
{
    case -1:
        printf("n is -1\n");
        break;

    case 1:
        printf("n is 1\n");
        break;

    default:
        printf("n is neither -1 nor 1\n");
        break;
}
    ```
* for
* do ...  while

| Symbole | Signification |
|---------|---------------|
| &&      | AND           |
| \|\|    | OR            |
| !       | NOT           |

## Loops
* while
* do ... while
* for    

## C : stdio, stdlib
* dbg : debugger. Add a breakpoint!
* `int main(int argc, char *argv[])` `int main(int argc, string argv[])`
    * command-line arguments
    * argc : argument count, or number of arguments. Integer-type variable will store the number of command-line arguments the user typed when the program was executed.
    * argv : argument vector (or argument list), an array of strings. This array of strings stores, one string per element, the actual text typed at the command-line when the program executed.
        * First element : argv[0]. Often the name of the program.
        * Last element : argv[argc-1]
* Prototype : fonctions declaration before main()
* Compiling : 
    * preprocessing : replace headers by prototypes
    * compiling : converts it into assembly code
    * assembling : translates it in binary called machine code
		* into *.o* or *.obj* files
    * linking : combined the pre-compiled versions of libraries
* `#include <stdio.h>`
* fflush(stdin) : après un scanf
    * efface le buffer, mauvaise pratique
* pas de goto!
### Arrays
* Most variables **are pased by value** in function calls
* Arrays **are passed by reference**. The callee receives the actual array, *not* a copy of it.
* `static int variable;` : variable globale propre à ce fichier
	* variable statique à une fonction à l'intérieur de celle-ci
	* fonctions locale à un fichier : **penser à mettre à jour les prototypes.**
* `\0`. Null character. Ends of an array of a string.
### Headers
* `#include "protoypes.h"`
### Pointers
* `int *pointer = NULL ;`
* *%p* dans printf avec **&**variable