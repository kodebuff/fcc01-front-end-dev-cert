# FCC Basic Javascript

**Stand In Line**

```javascript
function nextInLine(arr, item) {
  // Your code here
  arr.push(item);
  return arr.shift(); // Change this line
}

// Test Setup
var testArr = [1,2,3,4,5];

// Display Code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6)); // Modify this line to test
console.log("After: " + JSON.stringify(testArr));
```



**Golf Code**

```javascript
function golfScore(par, strokes) {
  // Only change code below this line
  if (strokes == 1) {
    return "Hole-in-one!";
  } else if (strokes <= (par - 2)) {
    return "Eagle";
  } else if (strokes == (par - 1)) {
    return "Birdie";
  } else if (strokes == par) {
    return "Par";
  } else if (strokes == (par + 1)) {
    return "Bogey";
  } else if (strokes == (par + 2)) {
    return "Double Bogey";
  } else {
     return "Go Home!";
  }
  // Only change code above this line
}

// Change these values to test
golfScore(5, 4);
```



**Counting Cards**

```javascript
var count = 0;

function cc(card) {
  // Only change code below this line
  switch (card) {
    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
      count += 1;
      break;
    case 7:
    case 8:
    case 9:
      count += 0;
      break;
    case 10:
    case 'J':
    case 'Q':
    case 'K':
    case 'A':
      count += -1;
      break;
  }
  
  if (count <= 0) {
    return count + " Hold";
  } else {
     return count + " Bet";
  } 
 
  // Only change code above this line
}

// Add/remove calls to test your function.
// Note: Only the last will display
cc(2); cc(3); cc(7); cc('K'); cc('A');
```



**Profile Lookup**

```javascript
//Setup
var contacts = [
    {
        "firstName": "Akira",
        "lastName": "Laine",
        "number": "0543236543",
        "likes": ["Pizza", "Coding", "Brownie Points"]
    },
    {
        "firstName": "Harry",
        "lastName": "Potter",
        "number": "0994372684",
        "likes": ["Hogwarts", "Magic", "Hagrid"]
    },
    {
        "firstName": "Sherlock",
        "lastName": "Holmes",
        "number": "0487345643",
        "likes": ["Intriguing Cases", "Violin"]
    },
    {
        "firstName": "Kristian",
        "lastName": "Vos",
        "number": "unknown",
        "likes": ["Javascript", "Gaming", "Foxes"]
    }
];


function lookUpProfile(firstName, prop){
// Only change code below this line
  for (var i = 0; i < contacts.length; i++) {
    if (contacts[i].firstName === firstName) {
      if (contacts[i].hasOwnProperty(prop)) {
        return contacts[i][prop];
      }
      return "No such property";
    }
  }  
  return "No such contact";
// Only change code above this line
}

// Change these values to test your function
lookUpProfile("Kristian", "number");
```



**Generate Random Whole Numbers within a Range**

Here's the formula we'll use. Take a moment to read it and try to understand what this code is doing:

```
Math.floor(Math.random() * (max - min + 1)) + min
```

```javascript
function randomRange(myMin, myMax) {
  return Math.floor(Math.random() * (myMax - myMin + 1)) + myMin;
}

// Change these values to test your function
var myRandom = randomRange(5, 15);
```



**Sift through Text with Regular Expressions**

Regular expressions are used to find certain words or patterns inside of strings. For example, if we wanted to find the word the in the string The dog chased the cat, we could use the following regular expression: /the/gi

Let's break this down a bit:

**/** is the start of the regular expression.

***the*** is the pattern we want to match.

**/** is the end of the regular expression.

***g*** means global, which causes the pattern to return all matches in the string, not just the first one.

***i*** means that we want to ignore the case (uppercase or lowercase) when searching for the pattern.



```javascript
// Select all the occurrences of the word and in testString.

// Setup
var testString = "Ada Lovelace and Charles Babbage designed the first computer and the software that would have run on it.";

var expression = /and/gi;

// This code counts the matches of expression in testString
var andCount = testString.match(expression).length;

```



**Find Numbers with Regular Expressions**

We can use special selectors in Regular Expressions to select a particular type of value. One such selector is the digit selector **\d** which is used to retrieve one digit (e.g. numbers 0 to 9) in a string.

In JavaScript, it is used like this: **/\d/g**

Appending a **plus sign (+)** after the selector, e.g. **/\d+/g**, allows this regular expression to match one or more digits. The trailing **g** is short for 'global', which allows this regular expression to find all matches rather than stop at the first match.

```javascript
// Use the \d selector to select the number of numbers in the string, allowing for the possibility of one or more digit.

// Setup
var testString = "There are 3 cats but 4 dogs.";

var expression = /\d+/g;

// This code counts the matches of expression in testString
var digitCount = testString.match(expression).length;
```



**Find Whitespace with Regular Expressions**

We can also use regular expression selectors like **\s** to find whitespace in a string. The whitespace characters are **" " (space), \r (the carriage return), \n (newline), \t (tab), and \f (the form feed).**

The whitespace regular expression looks like this: **/\s+/g**

```javascript
// Use \s to select all the whitespace characters in the sentence string.

// Setup
var testString = "How many spaces are there in this sentence?";

var expression = /\s+/g;

// This code counts the matches of expression in testString
var spaceCount = testString.match(expression).length;
```



**Invert Regular Expression Matches with JavaScript**

You can invert any match by using the uppercase version of the regular expression selector. For example, **\s** will match any whitespace, and **\S** will match anything that isn't whitespace.

```javascript
// Use /\S/g to count the number of non-whitespace characters in testString

// Setup
var testString = "How many non-space characters are there in this sentence?";

var expression = /\S/g;

// This code counts the matches of expression in testString
var nonSpaceCount = testString.match(expression).length;
```











