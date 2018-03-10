# Basic Algorithm Scripting



**Reverse a String**

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

```javascript
function reverseString(str) {
  
  // .split('') converts str to array and save each char to array elements
  // .reverse() reverts the sequence of array elements
  // .join('') combines array elements to string
  return str.split('').reverse().join('');
}

reverseString("hello");

// reverseString will be "olleh"
```



**Factorialize a Number**

Factorials are often represented with the shorthand notation `n!`

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

```javascript
function factorialize(num) {
  var i = num;
  var newNum = 1;
  for (i; i > 1; i--) {
    newNum *= i;
  }
  return newNum;
}
```



**Check for Palindromes**

A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

You'll need to remove **all non-alphanumeric characters **(punctuation, spaces and symbols) and turn everything lower case in order to check for palindromes.

```javascript
function palindrome(str) {
  // remove non alphanumeric chars
  var remSpChars = /[\W_]/g; 
    
  // convert chars into lowercase and replace special chars with blank chars    
  var cleanStr = str.toLowerCase().replace(remSpChars, ''); 
  
  // reverse string
  var reverseStr = cleanStr.split('').reverse().join(''); 
  
  // return true if cleanStr is the same with reverseStr, otherwise return false
  return reverseStr === cleanStr;
}

palindrome("eye");
```



**Find the Longest Word in a String**

Return the length of the longest word in the provided sentence.

```javascript
function findLongestWord(str) {
  // separate words and store it in arrays
  var strArr = [];
  strArr = str.split(" "); //
  
  var elementLength = 0;
  var storedMaxLength = 0;
  
  // iterate each arrays and find the length of each arrays
  for (var i = 0; i < (strArr.length); i++) {
    
    elementLength = strArr[i].length;
    
    // compare each array lengths and display the longest lengths
    if (elementLength > storedMaxLength) {
      storedMaxLength = elementLength;
    }
  }
  
  return storedMaxLength;
}
```



**Title Case a Sentence**

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".

```javascript
function titleCase(str) {
  //convert string to lowercase 
  var strLow = str.toLowerCase();
  
  //store each word in array
  var strArr = strLow.split(" ");
  
  //reiterate each array element
  for (var i = 0; i < strArr.length; i++) {
    
    // capitalize each first letter of array
    strArr[i] = strArr[i].charAt(0).toUpperCase() + strArr[i].substr(1);
  }
  
  // convert array to string
  var strStr = strArr.join(" ");
  
  return strStr;
}

titleCase("I'm a little tea pot");
```



**Return Largest Numbers in Arrays**

Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

```javascript
function largestOfFour(arr) {
  var num = 0;
  var largeNum = 0;
  var largeNumArr = [];
  
  // scan through arrays
  for (var i = 0; i < arr.length; i++) {
    
    // scan elements of sub array 
    for (var j = 0; j < arr[i].length; j++) {
      
      // assign value to a variable
      num = arr[i][j];
      
      // get the largest number and store it in largeNum
      if (num > largeNum) {
        largeNum = num;
      }
    }
    
    // save large number in large number array
    largeNumArr.push(largeNum);
    
    // reset the value of the large number for next array element to use
    largeNum = 0;
  }
  
  // display large numbers array
  return largeNumArr;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```



**Confirm the Ending**

Check if a string (first argument, `str`) ends with the given target string (second argument, `target`).

This challenge *can* be solved with the `.endsWith()` method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.

```javascript
function confirmEnding(str, target) {
  return target === (str.substring(str.length - target.length));
}

confirmEnding("Bastian", "n");
```



**Truncate a string**

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a `...` ending.

Note that inserting the three dots to the end will add to the string length.

However, if the given maximum string length `num` is less than or equal to 3, then the addition of the three dots does not add to the string length in determining the truncated string.

```javascript
function truncateString(str, num) {
/******************************************************************  
  // MY SOLUTION:
  var modStr = "";
  var lastThreeStr = "";
  
  // cut string from num place
  modStr = str.slice(0, num);
  
  if (num >= str.length) {
    return str;
  }
  
  if (num <= 3) {
    return modStr.concat("...");
  } else {
    // remove last 3 chars and replace it with ...
    return modStr.substring(0, (modStr.length - 3)).concat("...");
  }
******************************************************************/
  
  if (str.length > num && num > 3) {
    return str.slice(0, (num - 3)) + '...';
  } else if (str.length > num && num <= 3) {
    return str.slice(0, num) + '...';
  } else {
    return str;
  }  
}

truncateString("A-tisket a-tasket A green and yellow basket", 11);
```



**Chunky Monkey**

Write a function that splits an array (first argument) into groups the length of `size` (second argument) and returns them as a two-dimensional array.

```javascript
function chunkArrayInGroups(arr, size) {
  var arr2 = [];
  
  for (var i = 0; i < arr.length; i += size) {
    arr2.push(arr.slice(i, i + size));
  }
  return arr2;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```



