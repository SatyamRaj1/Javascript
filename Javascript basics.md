- `consol.log` is used to print value in console (see things in console)
   eg. consol.log("hello")
- every browser can run javascript code
- end all line with semi colon or skip semi colon completely
- to comment out multiple lines use cmd + k + c 
	- to remove use cmd + / it can also be used to comment out
- to use multiline cursor use cmd + d
- `typeof variable_name` gives type of variable( no brackets used)
- `prompt(message_displayed)` display a dialog box with given message and takes input (can be used to get user name). if user clicks cancel then it returns null 
### comments
**same as c++**
inline -> //comments
multiline -> /* this is comment */

# Data Types
### undefined
### null
### boolean
### string
### symbol
- unique
### number
### object
- can store key value pairs
- Details ->  [[#Objects ]]]

***typeof function is used to find data type***

# variable
- declaring 
   ### var
   - `var mtu="hfhhjh"``
    - can be changed later (data type also)  **mtu=8**
    - use variable hoisting
    - scope -> function
    ### let
	- `let a="dhfhg"`
	- don't use variable hoisting
	- scope -> block(if { ... if let inside then it's scope is to if statement only})
- variable hoisting -> if `var` is declared in a if statement and that statement never gets true and we console log out that variable then var being a function scoped will show that variable as undefined(not error). for `let` it will show error whether condition is true or not as let is block scoped so won't exist outside if block
     ### const
	 - never change
	 - read only
	 - these variable are commonly in capital (to remember)
	 - we can change const array through indexes. (not directly reassigning)  similiar objects can be changed
	 - to prevent change use ==object.freeze(object_name); ==
	 - `const pi=3.1415`

- difference between var and let [[#Difference b w var and let]]
***to use global variable declare a variable simply (don't use var) even in any function it will be global***

## using symbols
/'  single quotes
/" double quotes
// backslash
/n newline
/t tab
/r carriage return
/b backspace 
/f form feed

- multiple line string
 	var a=" first line \n \t \\ second line";
- finding length
		string.length
- indexing similar to c++

# Function
### syntax 
function function_name(arguements){   //no arguement type or var in front
...
defination
...
}
 ### use
 function_name(arguements)
 ### example
 function square(x){
 return x\*x;
 }
 console.log(square(5))
 
 ## Anonymous functions 
 - const function_name=function(arguements){
 												return ..
												}
  ## Arrow Function
  					==const function_name= (arguements) => return_value==
 
 ### map and filter functions using arrow function
 eg.  var arrlist=[3,5.4,-9,4,-34.5,45]
 		const squareint=(arr) => {
		const sqlist=arr.filter(num => Number.isInteger(num) && num >0).map(x => x*x)
		
		return sqlist;
		}
 # Array
 var myarr=["jggfh", 7564];
- only declaring
   var arr=[];
 - multidimensional
   var arr=\[[65,87,97,9],[9,6,4,3]\];
   ### push function
   push an element,array to an array
   eg. arr.push([5,78,8]);
   ### pop function
   remove the last element from array and return to variable
   eg. var removed=arr.pop()
   ### shift function
   similiar to pop but remove front element
   ### unshift function
   similar to push but add at front
   
   - JSON.stringify(arr)  -> to change/display array/object as a string
   - JSON.parse(str) -> reverse of above


# equality and strict equality 
\== equlaity -> conerts to common type and then check equality
\=\== strict equality ->doesn't convert
3\=='3'  -> true
3\=\=='3' -> false
- *strict inequality !\==*

# Objects 
  - similiar to arrays except intead of arrays they use properties(keys as in dictionaries of python)
  *eg.   var dog={
  "name": camper,
  "legs":4,
  "tails":1,
  "friends with":["quincy","ba"]
  };
  ### to find values of a property of an object ->
  #### M1   Dot notation
		eg.  dog.name;
#### M2 Bracket notation
		eg. dog["legs"];
==if proprty has space or have to use a variable for object proprty then only bracket notation works ==
		`eg. dog["friend with"]
  		var p="tails"
	    dog[p];`
  
### add new property
dog["sound"]="bow";
*can use dot notation too*
### deleting property
- use delete keyword
  delete dog.tails;

 `to check if a property is present or not use object_name.hasOwnProperty(property_name)`
 
 # Random Number
- Random Fraction
use ==Math.random()==. number between [0,1)
- to create random whole no. multiply fraction with no. and round off
  `Math.floor` -> Greatest Integer Funtion  *Note: if we use round off then no. 0 and last no. will have less probability*
  eg. Math.floor(Math.random()\*20)  -> whole no. between 0 to 19
- to generate number within range
  eg. Math.floor(Math.random\* (max - min + 1)) + min  
# parseInt function
- to convert string to integer
 a=parseInt(str);
 ### redix
 - to define base of integer
 - used with parseInt
 eg. parseInt("10001",2)     -> means base 2 number, return it's decimal value
 
 ## nested ternary operator
 return num>0 ? "positive" : num<0 ? "negative" : "zero"
 
 # Difference b/w var and let
 - let doesn't allow multiple declaration 
   eg. - var a=19;
   			var a=23;    -> will run smoothly , no problem
		 - let a=19;
		    let a=23;     -> will give error 
 - scope of var is upto function while scope of let is upto vlock statement or expression only
     eg.  `var i=5;
	 		  if(true){
			  i=34
			  console.log(i)
			  }
			  console.log(i)
			  `
			  - both console.log will print 34
			  `let i=5;
	 		  if(true){
			  let i=34
			  console.log(i)
			  }
			  console.log(i)
			  `
			  - first will print 34 while second back to i=5
			  - if first line not present(var/let=5) then in let it will throw error at second console.log() `scpe limited to block statement` while print i=34 in case of var
 ### "use strict";
 - used to avoid coomon and coding mistake
 - it will throw error else program will run without getting noticed
			
			
# error handling
***try*** {
....
} ***catch(ex)***{   //if error
console.log(ex)   //error
}
***throw***{
..
}
***finally***{
..
}

# Adding Javascript to HTML
## M1 -> In HTML write JS code
==<\script> 
....javascript_Code....
<\/script>==
*write whole JS code in script tag*
## -> Redirect script code to a javascript file
==<\script src = "index.js"><\/script>==