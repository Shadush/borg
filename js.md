# Javascript
* bibli: `const readlineSync = require("readline-sync");`
```javascript
	let userName = readlineSync.question('Can you give me your name please?');

	let arr = ["Apple", "Pear", "Banana"];

	for (let elem of arr) {
	  console.log("Do you want to eat a " + elem + "?");
	}
```
<hr>

* console.log();
* console.dir(document); : affichier le DOM
    * DOM Properties:
        * innerHTML: holds the HTML inside a set of HTML tags
        * nodeName: the name of an HTML element or element's attribute
        * id : the "id" attribute of an HTML element
        * parentNode : a reference to the node one level up in the DOM
        * childNodes: an array of references to the nodes one level down in the DOM
        * attributes: an array attributes of an HTML element
        * style: an object encapsulating the CSS/HTML styling of an element 
    * DOM Methods:
        * getElementById(id): gets the element with a given ID below this point in the DOM
        * getElementsByTagName(tag): gets all elemnts with the given tag below this point in the DOM
        * appedChild(node): add the given node to the DOM below this point
        * removeChild(node): remove the specified child node from the DOM
* Commentaires :
	* `// pour une seule ligne `
	* `/* commentaires sur plusieurs ou une seule  ligne d'ailleurs */`
* Data types (7) :
	 + Primitive data :
		- number : () -> sans ""
		- string : "..." or '...'
		- Bolean : true or false
		- null : intentional absence of value
		- undefined : absence of value
		- symbol : unique identifier
	+ Complex : 		
		- Object : collections of related data
* Opérations arithmétiques :
	- +
	- -
	- *
	- / : division
	- % : remainder, reste, modulo
	- ** : puissance
* typeof NaN : number
* Concatenation : appending one string to another
* Proprety :
	- length
        - console.log('Hello'.lenght);
								 . -> dot operator
* Objets :
	* console.log (Math.random());
	* Math.random()\*50;
        * arrondi :
			* Math.floor(Math.random()\*50)
			* Math.round
* camelcasing
	- ex. : myName.Uppercased
* var myName 	= 'Arya'
	- > assignement operator. Variable is initialized with a value of 'Arya'
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
		- > placeholder
* typeof operator : checks the value to its right and returns or passes back a string of datatype
# Conditions Statements

* if
```javascript
	if (true) {
		console.log('xx');
	}	else {
		console.log('xx');
	}
```
* differences : double checks for equality of value but not equality of type. Coerces both values to the same type then compares them.
	* < : less than
	* > : greater than
	* <= : less than or equal to
	* >= : greater than or equal to
	* == : equality
	* === :(strict) is equal to
	* != : not equal
	* !== : (strict) is not equal to
		* -> yes = true, no = false
Falsy statements : 
   * false
   * 0
   * ""(empty string)
   * null
   * undefined
   * NaN
Truthy statements : everything else!
## Logical operators
* && : and
* `|| : or`
* ! : not or the bang operator. Inverse
* while
* for : 3 expressions seperate by ;
	> init ; stopping condition ; itertation to update
```javascript

	for (var i=0 ; i<9 ; i++){
		str= str+i;
	}
```
* let tool = pen || "xx"
	// si ce nest pas pen alors ce sera xx
* ternary operator : variable ? console.log('true') : console.log('else');
* else if : before else. Allow multiple outcomes, scenarios.
* Switch :
```javascript
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
In JavaScript, functions are first class objects, this means that like other objects you've encountered, JavaScript functions can have properties and methods.
* function declaration : binds a fonction to a name  
    > function greetworld() { ... }  
    function : function keyword  
    greetworld : identifier, the name  
* parameter : between parentheses
    * call it later, it's an argument
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
```javascript
let myFunction = (a, b) => {
  return a + b;
}

console.log(myFunction(2, 3)); // 5

myFunction = (a, b) => {
  return a * b;
}

console.log(myFunction(2, 3)); // 6
```
```js
const square = function (num){
        return num*num;
}
```

* scopes defines : where variable can be accessed or referenced
* arrays : []. Index start at zéro 0
## Methods
* Methods : functions on objects (properties)
	- instance.methodname()
	- .toUpperCase
	- .trim
```js
const math = {
    multiply : function(x, y){
        return x * y;
    },
    divide : function (x, y){
        return x / y;
    },
    square : function (x){
        return x * x;
    }
};
```
shorthand :
```js
const math = {
    blah: "Hi!",
    add(x, y){
        return x +y;
    },
    multiply(x, y){
        return x * y;
    }
}
math.add(50, 60)  //110
```
# Variables
* const variables inchangeables. Can be mutable : can change the content but cannot reassign an array or a value
* let variables : changeables
# Proprety
* Arrays :
    * .length : number of items
    * .pop : remove last item
    * .push : rajoute à la fin
    * .shift : remove from start
    * .unshift : add to start
    * concat : merge arrays
    * includes : look for a value
    * indexOf : just like string.indexOf
    * reverse : reverse an array
    * slice : copies a portion on an array
    * splice : removes/replaces elements
    * sort : sorts an array
* update une array -> variable [3] = 'mot';
* new Array
* parseInt(); renvoi un entier
* `...`
	* rest parameter : collect all remaining elements into an array
	* spread operator : allows iterables( arrays / objects / strings ) to be expanded into single arguments/elements
		* `const arr = ["Joy", "Wangari", "Warugu"]; const newArr = ["joykare", ...arr];`
## Nested Array
* `[][[x,x]]; const [] []`

* for ... of : iterate on arrays
```javascript
	let arr = [];
	for (let elem of arr)
		{
			console.log("..." + elem + '?');
		}
```
* Recursivity : a fonction calls itself
```javascript
	function count (i) {
	if (i <= 100) {
	console.log(i);
		count (i+1)
	}
}
```
# Loops
* for
```javascript 
for (
        [initialExpression];
        [condition];
        [incrementExpression]
)
```
* for of (great for iterating over arrays)  
    > for (variable of iterable){statement}  
    > for (let var of variable){console.log(var)}
* for in : iterating over objects
* While
* Do While : do it at least once then loop until condition met
```javascript
	let countString = '';
	let i = 0;

	do {
	  countString = countString + i;
	  i++;
	} while (i < 5);

	console.log(countString);
```
* break : keyword allows programs to “break” out of the loop from within the loop's block.

# Higher-order functions
> Higher-order functions are functions that accept other functions as arguments and/or return functions as output.

```javascript
	const announceThatIAmDoingImportantWork = () => {
	    console.log("I’m doing very important work!");
		};
	const busy = announceThatIAmDoingImportantWork;

	busy();
```
# HTML
* document.querySelector('#id').value
* document.querySelector('form').addEventListener('submit', function) 
* Event listeners : 
    * blur
    * change
    * click
    * drag
    * focus
    * keyup
    * load
    * mousedown
    * mouseover
    * mouseup
    * submit
    * touchmove
    * unload

## Ajax
* XMLHttpRequest
    * `var xhttp = new XMLHttpRequest();`
* *onreadystatechange* behavior. Function (anonymous) called when the asynchronous HTTP request has completed. Defines what is expected to change.
* *readyState* property will change from 0 (request not initiliazed) to 1, 2, 3 and 4 (request finished, response ready)
    * the status propety will be 200 (OK)
* Make a asynchonous request using the open() method to define the request and the send() method to actually send it.
```js
function ajax_request(argument)
{
    var aj = new XMLHttpRequest();
    aj.onreadystatechange = function() {
        if (aj.readyState == 4 && aj.status == 200)
            // do something to the page
    };
    
    aj. open("GET", /* url */, true);
    aj.send();
}
```