### Template Literals
problems with strings
- to concaneate and using spaces we have to write long eg. first+" "+middle+" "+last
- can't use `''` , `""`
- string + integer + integer concaneate but not add
- multiline strings create problems (have to use \\n)


literals solve them by 
- to concaneate use \`${first} ${middle} ${last}\`
- can use '' , ""
- to add use \`${first} {num1 + num2}\`
- to concaneate use ${first} {num1} {num2}
- can be used for multiline strings 
### Destructuring Objects
- used to use object in better ways
`let player = {name : "asdfk",
					team : "asf",
					address : { city : "lsadf",
											country : "sdklf"
											}
											}`
	now to use any of it's key we have to use dot notation which can go long eg. player.address.city
	- to make easy we can use destructuring of objects
	`const {name,team,address : {city}} = player`
	- now we can directly use name, team, city
	`console.log(name)` will give asdfk
	console.log(\`${name} lives in ${city}\`)
#### Destructuring Arrays
- gives a variable name to indexes
`[first, middle] = ['satyam','raj','purohit']`
- first corresponds to 0th index and middle to 1st
- if don't want any index value leave it empty (`[,fd]`)
#### Object Literal
- to assign value to key whose value variable name/value is same as keys
`let city = "jlsj"
  let state = "ksdf" 
  const address = {city , state}`
  now address will be {city : "jlsj", state : "ksdf"}
  we can partially use it also
`   const newAddress = {
		city,
		state,
		country: 'United States'
		};`
### For of Loop
-for iterals -> string, array, sets, maps ...etc.
` let incomes = [62000, 67000, 75000];
	let total = 0;
	for (let inc of incomes) {
	console.log(inc)
	total += inc;
}`
### Spread Operator
- to make new copy of array
- same like .copy()
- can add also to
`let contacts = ["lsf", "jsf" ," jssfkjs"]`
- to copy this array( as directly assigned will be reference to same and any change in new will create change in old too) ->
`cont = [...contacts]`
- to add something 
`cont = ["skfjs",...contacts,"sdkfds"]`
this will add "skfjs" at beginning and "sdkfds" at last
- can copy objects too
`let cricketer = {
									...player,
									career : 12
									}`  player object from above mentioned

### Rest operator
- used when no. of arguements are unknown in a function use it
- in parameter use ...parameter so that that parameter will be an array of arguements
# Arrow function
- `normal functions`
function function_name(para1) { .... body of function }
- `anonymous function`
const function_name = function(para1){ .... body of the function }
- `arrow function`
	- syntax ==const function_name = (para1) => { .... body of the function }==
	***if function is only returning a value we can use***
	- const function_name = (para1) => return_value(no brackets) ;    
		- all in one line only
		- if only one parameter no need of bracket around parameter
- to call all have same method i.e. function_name()
### Default Parameters
- same as in c++ at parameter assign them default value

### include()
#### indexof 
- it will give index of an element in an array syntax -> array_name.typeof(element_value)
- gives -1 it it is not present

- include() gives if element is present or not( output as true or false)
### Export and Import
- export
	- use `export variable_name/function_name/class_name/object_name...`
- import
	- use `import {variable_1, function_1} from "file_location_with_name"`
	- if in same folder use `./file_name.extention` 
	- only function name in case of objects/function/classes... no (),{}
# Class
Syntax
`class class_name{
constructor(var1,var2){
this.var1 = var1;
this.var2 = var2;  }
function_name(){ ... }
}`
- `constructor()` function is used to make constructor(here class name not used)
- no need to define variable earlier with let/const/var if used with `this` keyword but variable name should be same as arguement name 
- if declared using `this` then if we have to use it inside class we have to use this.var1
- `this` can also be used in any function of class(not compulsory constructor)
- `this` keyword states that var1 of this class
- no compulsory semicolon in JS so no need to end class with semi colon
- no need of `function`  keyword while declaring function inside class
declaring Objects
`let object_name = new class_name(var1,var2);`
if we don't pass arguements for constructors it won't throw error but assign them as undefined
## Static Function
- using static we create function which can be used without using instances/objects
- we can use them from class only
syntax -> inside class
`static function_name(){ ... }`
to use it
`class_name.function_name();`
### Get keyword
if we use get in front of function name and return something then to get that return value we can use object.function_name . no need of brackets
 ## Inheritance
 use `class child_class_name extends base/parent_class { ... }`
 ## Overwriting constructor
 - if we declare a constructor inside base class and then want to declare a constructor with some additional variable we overwrite constructor
 - we use `super()` function
 - we have to take parameters in child class as parameters_of_base_class + new parameters
 - then declare them in super function
 - eg.  Declaration
 `class Employee{
constructor(name, age){
this.name = name;
this.age = age;  }  }`
`class Head extends Employee{
constructor(name, age, position){
super(name, age);
this.position = position;  }  }`
Using
`let person1 = new Head(name,age,position);`
name and age will go to constructor of base class(Employee) and position to child class(Head)
- if we don't use `super()` then by default this would be variables of child class only
 
### Function overwriting
if we make same function in child class it will be used by default if we call that function from a object defined from child class