# Numerical Palindrome #3.5

## Description

```
A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward as forward. 

Examples of numerical palindromes are: 
  - 2332,
  - 110011,
  - 54322345
```

## Task

```
For a given number num, write a function which returns an array of all the numerical palindromes contained within each number. The array should be sorted in ascending order and any duplicates should be removed.

In this kata, single digit numbers and numbers which start or end with zeros (such as 010 and 00) are NOT considered valid numerical palindromes.

If num contains no valid palindromes, return "No palindromes found". Otherwise, return "Not valid" if the input is not an integer or is less than 0.
```

## Examples

```c
palindrome(1221)      =>  [22, 1221]
palindrome(34322122)  =>  [22, 212, 343, 22122]
palindrome(1001331)   =>  [33, 1001, 1331]
palindrome(1294)      =>  "No palindromes found"
palindrome("1221")    =>  "Not valid"
```

# Solitions

```c
function palindrome(num) {
  if (!Number.isInteger(num) || num < 0) return 'Not valid';
  const arr = num.toString().split("");
  const res = new Set();
  for (let i = 0; i < arr.length; i++) {
    for (let j = i + 1; j < arr.length; j++) {
      if (
        arr.slice(i, j + 1).reverse().join("") === 
        arr.slice(i, j + 1).join("") &&
        (+arr.slice(i, j + 1).join("")).toString() === arr.slice(i, j + 1).join("")
      ) res.add(+arr.slice(i, j + 1).join(""))
    }
  }
  if (res.size) return Array.from(res).sort((a, b) => a - b);
  return 'No palindromes found'
}
```