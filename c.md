# C
## Types de variables

| Nom du type | Minimum       | Maximum        |
|-------------|---------------|----------------|
| signed char | -127          | 127            |
| int         | -32 767       | 32 767         |
| long        | 2 147 483 647 | -2 147 483 647 |
| float       | -1 x1037      | 1 x1037        |
| double      | -1 x1037      | 1 x1037        |

## Afficher le contenu d'une variable

| Format | Type attendu |
|--------|--------------|
| "%d"   | int          |
| "%ld"  | long         |
| "%f"   | float        |
| "%f"   | double       |
| "%c"   | character    |

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

| Symbole | Signification |
|---------|---------------|
| &&      | AND           |
| \|\|    | OR            |
| !       | NOT           |

