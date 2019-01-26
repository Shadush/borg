* bibli: ``` const readlineSync = require("readline-sync"); ```
```
let userName = readlineSync.question('Can you give me your name please?');

let arr = ["Apple", "Pear", "Banana"];

for (let elem of arr) {
  console.log("Do you want to eat a " + elem + "?");
}
```
<hr>

* console.log();

* Commentaires : 
			```	// pour une seule ligne ```
			```	/* commentaires sur plusieurs ou une seule  ligne d'ailleurs */ ```
* Data types (7) : 
				- Primitive data : 	
									- number : () -> sans ""
									- string : "..." or '...'
									- Bolean : true or false
									- null : intentional absence of value
									- undefined : absence of value
									- symbol : unique identifier
				- Complex : 		- Object : collections of related data
* Opérations arithmétiques : 
							- +
							- -
							- *
							- / : division
							- % : remainder, reste, modulo
* Concatenation : appending one string to another
* Proprety : 
		- length
			- console.log('Hello'.lenght);
								 . -> dot operator
* Methods : 
			- instance.methodname()
			- .toUpperCase
			- .trim
* Objets : 
				* console.log (Math.random());
				* Math.random()\*50;
	* arrondi : 
				* Math.floor(Math.random()\*50)
				* Math.round
* camelcasing
		- ex. : myName.Uppercased
* var myName 	= 'Arya'
				-> assignement operator. Variable is initialized witg a value of 'Arya'
	* /!\ : pas commencer avec un nombre //
	* case sensitive
	* cannot be the same as keywords
* let variable = "xxx"
			 - can be assigned to a different value
* on peut utiliser une variable sans rien -> "undefined"
* const (constant) var. Cannot be reassigned (or else TypeError)
	- if not declared with a value -> SyntaxError
* parseInt() converts a string to a number
* 
	* +=
	* -=
	* \*=
	* /=
* Increment operator : ++, --
* operator "+" can combine two strings
* insert or interpolate variable into strings using `template literals`
	* Phase 	${MyPet}
				-> placeholder
* typeof operator : checks the value to its right and returns or passes back a string of datatype
# Conditions Statements

* if
```
	if (true) {
		console.log('xx');
	}	else {
		console.log('xx');
	}
```
*	
	* < : less than
	* > : greater than
	* <= : less than or equal to
	* >= : greater than or equal to
	* === : is equal to
	* !== : is not equal to
		* -> yes = true 	no = false
## Logical operators	
	* && : and
	* || : or
	* ! : not or the bang operator. Inverse
* while
* for : 3 expressions seperate by ;
	init ; stopping condition ; itertation to update
	for (var i=0 ; i<9 ; i++){
		str= str+i;
	}
* let tool = pen || "xx"
	// si ce nest pas pen alors ce sera xx
* ternary operator : variable ? console.log('true') : console.log('else');
* else if : before else. Allow multiple outcomes, scenarios.
* Switch : 
	```
	let groceryItem = 'papaya';

	switch (groceryItem) {
	  case 'tomato':
	    console.log('Tomatoes are $0.49');
	    break;
	  case 'lime':
	    console.log('Limes are $1.49');
	    break;
	  case 'papaya':
	    console.log('Papayas are $1.29');
	    break;
	  default:
	    console.log('Invalid item');
	    break;
	}
	
	// Prints 'Papayas are $1.29'
	```
# Fonctions

Specific task multiple times. 
	INPUT & OUTPUT
Reusable block of code that groups together a sequence of statements to perform specific task.
* function declaration : binds a fonction to a name
		function greetworld { ... }
			function : function keyword
			greetworld : identifier
* hoisting : allow access to function 
* écrire une fonction avec "=>"
```javascript	
const square = (num) => {
	return num*num;
	}
```
devient :

```javascript	
const square=num => num*num;
```
* scopes defines : where variable can be accessed or referenced
* arrays : []. Index start at zéro 0
# Variables
* const variables inchangeables. Can be mutable : can change the content but cannot reassign an array or a value
* let variables : changeables
# Proprety
* .length : number of items
* .pop : remove last item
* update une array -> variable [3] = 'mot';
* parseInt(); renvoi un entier
# Nested Array
[][[x,x]]; const [] []

* for ... of : iterate on arrays
```javascript	
	let arr = []
	for (let elem of arr)
		{
			console.log("..." + elem + '?');
		}
```
* Recursivity 
```javascript	
	function count (i) {
	if (i <= 100) {
	console.log(i);
		count (i+1)
	}
}	
```
# Loops
* While