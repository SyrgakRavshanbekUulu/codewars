# Numerical Palindrome #2

## Descriptions

```


A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward as forward. Examples of numerical palindromes are:

2332
110011
54322345

For this kata, single digit numbers will not be considered numerical palindromes.

For a given number num, write a function to test if the number contains a numerical palindrome or not and return a boolean (true if it does and false if does not). Return "Not valid" if the input is not an integer or is less than 0.



```
> Note: Palindromes should be found without permutating num.

## Example: 
  - palindrome(5) => false
  - palindrome(1221) => true
  - palindrome(141221001) => true
  - palindrome(1215) => true 
  - palindrome(1294) => false 
  - palindrome("109982") => "Not valid"

# Solition:

```c

function palindrome(num) {
  if (!Number.isInteger(num) || num < 0) return 'Not valid';
  if (num < 10) return false;
  const arr = num.toString().split('')
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (
        arr.slice(i, j + 1).reverse().join('') === 
        arr.slice(i, j + 1).join('')
      ) return true;
    }
  }
  return false;
}

```