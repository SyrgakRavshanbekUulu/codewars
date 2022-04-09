# Numerical Palindrome #3

## Description

```
A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward as forward. Examples of numerical palindromes are:

  - 2332
  - 110011
  - 54322345
```

## Task

```
For a given number num, write a function which returns the number of numerical palindromes within each number. For this kata, single digit numbers will NOT be considered numerical palindromes.

Return "Not valid" if the input is not an integer or is less than 0.
```

## Examples

```c
palindrome(5) => 0
palindrome(1221) => 2 
palindrome(141221001) => 5  
palindrome(1294) => 0
palindrome("1221") => "Not valid"
```

# Solition

```c
function palindrome(num) { 
  if (!Number.isInteger(num) || num < 0) return 'Not valid';
  const arr = Array.from(num.toString());
  let count = 0;
  for (let i =  0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (
        arr.slice(i, j + 1).reverse().join("") === 
        arr.slice(i, j + 1).join("")
      ) count++;
    }
  }
  return count;
}
```