# FCC Object Oriented and Functional Programming



**Declare JavaScript Objects as Variables**

```javascript
// Give your motorBike object a wheels, engines and seats attribute and set them to numbers.

var motorBike = {

  // Only change code below this line.
  "wheels": 2,
  "engines": 1,
  "seats": 2
};
```



**Construct JavaScript Objects with Functions**

We are also able to create objects using constructor functions.A constructor function is given a capitalized name to make it clear that it is a constructor.

Here's an example of a constructor function:

```javascript
var Car = function() {
  this.wheels = 4;
  this.engines = 1;
  this.seats = 5;
};
```



In a constructor the this variable refers to the new object being created by the constructor. So when we write  ```this.wheels = 4;```  inside of the constructor, we are giving the new object it creates a property called wheels with a value of 4. You can think of a constructor as a description for the object it will create.

```javascript
// Have your MotorBike constructor describe an object with wheels, engines and seats properties and set them to numbers.

var MotorBike = function() {
  this.wheels = 2;
  this.engines = 1;
  this.seats = 2;
};
```



**Make Instances of Objects with a Constructor Function**

To use a constructor function we call it with the `new` keyword in front of it like:

`var myCar = new Car();`

`myCar` is now an instance of the Car constructor that looks like the object it described:

```javascript
{
  wheels: 4,
  engines: 1,
  seats: 5
}
```

Note that it is important to use the new keyword when calling a constructor. This is how Javascript knows to create a new object and that all the references to this inside the constructor should be referring to this new object.

Now, once the myCar instance is created it can be used like any other object and can have its properties accessed and modified the same way you would usually. For example:

`myCar.turboType = "twin";`

Our `myCar` variable now has a property turboType with a value of "twin".



**Make Unique Objects by Passing Parameters to our Constructor**

The constructor we have is great, but what if we don't always want to create the same object? To solve this we can add parameters to our constructor. We do this like the following example:

```javascript
var Car = function(wheels, seats, engines) {
  this.wheels = wheels;
  this.seats = seats;
  this.engines = engines;
};
```

Now we can pass in arguments when we call our constructor.

`var myCar = new Car(6, 3, 1);`

This code will create an object that uses the arguments we passed in and looks like:

```javascript
{
  wheels: 6,
  seats: 3,
  engines: 1
}
```



**Make Object Properties Private**

Objects have their own attributes, called properties, and their own functions, called methods. We use the `this` keyword to reference `public properties` of the current object. 

We can also create `private properties` and `private methods`, which aren't accessible from outside the object. To do this, we create the variable inside the `constructor` using the `var` keyword we're familiar with, instead of creating it as a `property` of `this`. This is useful for when we need to store information about an object but we want to control how it is used by outside code.

For example, what if we want to store the `speed` our car is traveling at but we only want outside code to be able to modify it by accelerating or decelerating, so the speed changes in a controlled way.

```javascript
var Car = function() {
  // this is a private variable
  var speed = 10;

  // these are public methods
  this.accelerate = function(change) {
    speed += change;
  };

  this.decelerate = function() {
    speed -= 5;
  };

  this.getSpeed = function() {
    return speed;
  };
};
```



**Iterate over Arrays with map**

The `map` method is a convenient way to iterate through arrays. Here's an example usage:

```javascript
var oldArray = [1, 2, 3];
var timesFour = oldArray.map(function(val){
  return val * 4;
});
console.log(timesFour); // returns [4, 8, 12]
console.log(oldArray);  // returns [1, 2, 3]
```



**Condense arrays with reduce**

The array method `reduce` is used to iterate through an array and condense it into one value. To use `reduce` you pass in a callback whose arguments are an accumulator (in this case, `previousVal`) and the current value (`currentVal`). The accumulator is like a total that `reduce` keeps track of after each operation. The current value is just the next element in the array you're iterating through. `reduce` has an optional second argument which can be used to set the initial value of the accumulator. If no initial value is specified it will be the first array element and `currentVal` will start with the second array element. Here is an example of `reduce` being used to subtract all the values of an array:

```javascript
var singleVal = array.reduce(function(previousVal, currentVal) {
  return previousVal - currentVal;
}, 0);
```



**Filter Arrays with filter**

The `filter` method is used to iterate through an array and filter out elements where a given condition is not true. `filter` is passed a callback function which takes the current value (we've called that `val`) as an argument. Any array element for which the callback returns true will be kept and elements that return false will be filtered out. 

Use `filter` to create a new array with all the values from `oldArray` which are less than 6. The `oldArray` should not change.

```javascript
var oldArray = [1,2,3,4,5,6,7,8,9,10];

// Only change code below this line.

var newArray = oldArray.filter(function(val){
  return val < 6;
});

```



**Sort Arrays with sort**

`sort`actually alters the array in place. However, it also returns this sorted array. `sort` can be passed a compare function as a callback. The compare function should return a negative number if `a` should be before `b`, a positive number if `a` should be after `b`, or `0` if they are equal.

If no compare (callback) function is passed in, it will convert the values to strings and sort alphabetically.

```javascript
var array = [1, 12, 21, 2];
array.sort(function(a, b) {
  return a - b;
});
```

Use `sort` to sort `array` from largest to smallest.

```javascript
var array = [1, 12, 21, 2];

// Only change code below this line.

array.sort(function(a, b){
  return a < b;
});
```



**Reverse Arrays with reverse**

You can use the `reverse` method to reverse the elements of an array. `reverse` is another array method that alters the array in place, but it also returns the reversed array.

```javascript
var myArray = [1, 2, 3];
myArray.reverse();

// returns [3, 2, 1]
```



**Concatenate Arrays with concat**

`concat` can be used to merge the contents of two arrays into one. `concat` takes an array as an argument and returns a new array with the elements of this array concatenated onto the end.

Here is an example of `concat` being used to concatenate `otherArray` onto the end of `oldArray`:

`newArray = oldArray.concat(otherArray);`

Use `.concat()` to concatenate `concatMe` onto the end of `oldArray` and assign it to `newArray`.

```javascript
var oldArray = [1,2,3];
var newArray = [];

var concatMe = [4,5,6];

// Only change code below this line.

newArray = oldArray.concat(concatMe);

```



**Split Strings with split**

You can use the `split` method to split a string into an array. `split` uses the argument you pass in as a delimiter to determine which points the string should be split at.

Here is an example of `split` being used to split a string at every `s` character:

`var array = string.split('s');`

Use `split` to create an array of words from `string` and assign it to `array`.

```javascript
var string = "Split me into an array";
var array = [];

// Only change code below this line.

array = string.split(" ");

// array value will be ["Split", "me", "into", "an", "array"]
```



**Join Strings with join**

We can use the `join` method to join each element of an array into a string separated by whatever delimiter you provide as an argument.

The following is an example of using `join` to join all of the elements of an array into a string with all the elements separated by word `and`:

```javascript
var veggies = ["Celery", "Radish", "Carrot", "Potato"];
var salad = veggies.join(" and ");
console.log(salad); // "Celery and Radish and Carrot and Potato"
```

Use the `join` method to create a string from `joinMe` with spaces in between each element and assign it to `joinedString`.

```javascript
var joinMe = ["Split","me","into","an","array"];
var joinedString = '';

// Only change code below this line.

joinedString = joinMe.join(" ");

// joinedString value will be [Split me into an array]
```

