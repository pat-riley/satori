#Javascript - Ultimate Reference


##Object Oriented Programming


####Objective Thinking
In Javascript, get in the mindset that every component can be thought of as an object. When defining the problem and drafting out the steps required to solve that problem remember to always think in terms of OOP. It will save you time in the long run.

Objects have:

Properties
* name - user defined
* value - data type

Events
* Something specific happenning

Methods
* retrieve or change values of other object's properties


*If there is more than one object, it is known as different instances of that objects*

##Variables

###Declaring a Variable
Before you can use a variable, you must declare it. *Var* is a JS keyword and the JS interpreter knows that this keyword creates a variable. Sometimes the name is called an identifier.
```
var quantity;
```
#####Rules for Naming Variables
1. Must begin with a letter, dollar sign`$` or underscore`_`
2. Do not use dash`-` or period `.`
3. You cannot use **keywords** or **reserved** words. Keywords tell the interpreter to do something. View List of Keywords.
4. Variables are case sensitive, but do not create `variable` and `Variable`
5. Use a name that describes the kind of information the variable stores. 
6. Use `camelCase` if the variable is two words

###Assign value to Variable
After you declare a variable, you can assign a value. The equal sign is an assignment operator. Until you have a value to a variable, programmers say the value is undefined.
```
quantity = 3:
```

A variable can be anything. 

##Arrays
Arrays are a type of variable.

You should use an array when you are working with a **list** or set of **related** values. Arrays are helpful when you have a list and do not know how many items there will be.

###Creating an Array
#####Aray Ltiteral
You can put any combination of variables into an array. 
```
var colors;						
colors = ['white', 'black', '2'];

```
#####Array Constructor
Uses the *new* keyword to declare and assign all in one statement.
```
var colors = new Array('white',
						'black',
						'custom');
```
###Accessing Arrays
Values in an array are accessed as if they are in a numbered list.  The first item in the list starts at `0`

You can assigned a value in an array to a variable.
```
var itemThree;
itemThree = colors[2];
```
#####Getting number of items in an array
Each array has a property called `length` which holds the number of items in the array.

```
var numColors;
numColors = colors.length;

```
#####Changing value in an array
```

//Update the third item in the array
colors[2] = 'beige';

//Get the element with an id of colors
var el = document.getElemendById('colors');

//Replace with the third item from the array
el.textContent = colors[2];
```


##Functions
###Declaring a Function
To create a function, you give it a **name** and then write the statements needed to achieve its task inside the curly braces. Funcitons are written in camelCase. 

```
function sayHello() {
	document.wite('Hello');
}
```



###Calling a Function
After you Declare a funtion, this is how you call it.
```
sayHello();
```
##Objects

###Creating Objects

####Literal Notation
The easiest and most popular way to create objects.

```
var hotel = {
	//Properties
	name: 'Quay',
	rooms: 40,
	booked: 25,
	
	//Methods
	checkAvailability: function {
		return this.rooms - this.booked;
	}
```

####Creating an object with Constructor Notation

The **new** keyword and the object constructor create a blank object. You can then add properties and methods to the object using dot notation. You can use this syntax to add properties and methods to any object you have creates (No matter which notation you used to create it)

```
var hotel = new Object();		//creates an empty object

hotel.name = 'Quay';
hotel.rooms = 40;
hotel.booked = 25;

hotel.checkAvailability = function() {
	return this.rooms - this.booked;
}
```

To create an empty object using literal notation 

```
var hotel = {}
```

####Creating many Objects at Once (Constructor Notation)
Sometimes you will want several objects to represent similar things. Object contructors can use a function as a template for creating objects. First, create the template with the objects's properties and methods. 

The function has three parameters, and each one sets the value of a property in the object. 
```
function Hotel (name, rooms, booked) {
	
	this.name = name;
	this.rooms = rooms;
	this.booked = booked;
	
	this.checkAvailability = function() {
		return this.rooms - this.booked;
	}
}
```
The **This** keyword is used instead of the objects name to indicate that the property or method belongs to the object that **this** function creates.

Now you can create *instances* of the object using the constructor function. The **new** keyword followed by a call to the vunction creates a new object. The properties of each object are given as arguments to the function.
```
var quayHotel = new Hotel('Quay', 40, 25);
var parkHotel = new Hotel('Park', 120, 77);
```

### Using Objects

####Accessing an object (dot notation)

You can access the properites and methods of an object using dot notation. You can also access properties using square brackets. To access a property of an object, you can use **dot notation**, which is shown below.

The period in dot notation is known as the **member operator**. The property or method on the right is a member of the object on its left. Here, two variables are created to hold the hotel name and the number of vacant rooms. 

```
var hotelName = hotel.name;
var roomsFree = hotel.checkAvailability();
```
####Accessing an object (Square Syntax)
You can also access the properties of an object (but not its methods) using square brackett syntax.  This time, the object name is followed by square brackets, and the property name is inside them. 
```
var hotelNAme = hotel['name'];
```
This notation is most commonly used when:
* The name of the property is a number (technically alllowed, but should generally be avoided)
* A variable is being used in place of the property name

####Updating an Object
To update the value properties, use dot notation or square brackets. If the object does no thave the property you are defining it will be added to the object. Note: The square bracket notation does not work for updating methods.
```
hotel.name = 'Park'
hotel['name'] = 'Parl';
```

####Deleting / Clearing an object properites
Use the keyword **delete** to delete a property.
```
delete hotel.name;
```

To clear the value of a property, you could set it to a blank string
```
hotel.name = '';
```

##Errors

###Try and Catch

The `try` statement allows you to define a blokc of code to be tested for errors while it is being executed

The `catch` statement allows you to define a block of code to be executed, if an error occurs in the try block.

The Javascript statements `try` and `catch` come in pairs:

```
try {
	Block of code to try
}
catch(err) {
	block of code to handle errors
}
```

###Throw

When an error occurs, JavaScript will normally stop and generate an error message. The technical term for this is: JavaScript will *throw* an error.

The `throw` statement allows you to create a custom error.

The technical term for this is **throw an exception**

```
throw "Too Big";	//throw a text
throw 500;			//throw a number
```

###Finally

The **finally** statement lets you execute code, after try and catch, regardless of the result:
```
try {
	Block of code to try	
}
catch (err) {
	Block of code to handle errors
}
finally {
	Block of code to be executed regardless of the try/catch result
}
```




