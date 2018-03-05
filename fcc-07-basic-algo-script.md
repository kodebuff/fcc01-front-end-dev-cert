# Basic Algorithm Scripting



**Reverse a String**

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

```javascript
function reverseString(str) {
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

