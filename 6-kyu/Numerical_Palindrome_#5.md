# Numerical Palindrome #5

## Description:
```
A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward as forward. Examples of numerical palindromes are:

 * 232
 * 110011
 * 54322345

Complete the function to test if the given number (num) can be rearranged to form a numerical palindrome or not. Return a boolean (true if it can be rearranged to a palindrome, and false if it cannot). Return "Not valid" if the input is not an integer or is less than 0.
```

### For this kata, single digit numbers are NOT considered numerical palindromes.

# Solitions

```c
function palindrome(num) { 
  if (num < 0 || typeof num !== 'number') return 'Not valid';
  if (num < 10) return false;
  const obj = {};
  const arr = num.toString().split("");
  let even = 0;
  for (const el of arr) {
    if (el in obj) {
      obj[el]++;
    } else {
      obj[el] = 1;
    }
  }
  const resArr = Object.keys(obj);
  for (const key of resArr) {
    if (obj[key] % 2 === 0) even++;
  }
  return (even === resArr.length || even === resArr.length - 1);
}

```
[Task in Codewars.com](https://www.codewars.com/kata/58e26b5d92d04c7a4f00020a)