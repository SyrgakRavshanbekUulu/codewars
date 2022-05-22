# Next smaller number with the same digits

## Descriptions
``` 
Write a function that takes a positive integer and returns the next smaller positive integer containing the same digits.
```

## Example
```c
nextSmaller(21) == 12
nextSmaller(531) == 513
nextSmaller(2071) == 2017
```
Return -1 (for Haskell: return Nothing, for Rust: return None), when there is no smaller number that contains the same digits. Also return -1 when the next smaller number with the same digits would require the leading digit to be zero.
```c
nextSmaller(9) == -1
nextSmaller(111) == -1
nextSmaller(135) == -1
nextSmaller(1027) == -1 // 0721 is out since we don't write numbers with leading zeros
```
- some tests will include very large numbers.
- test data only employs positive integers.

# Solitions
```c
const toMin = n => {
  const arr = n.toString().split("").sort()
  const noZeroIndex = arr.findIndex(a => a > 0)
  if (noZeroIndex !== 0) {
    const firstDigit = arr.splice(noZeroIndex, 1);
    return [...firstDigit, ...arr].join("")
  }
  return arr.join("")
}

function nextSmaller(n) {
  const min = toMin(n);
  const checkAnagram = (num) => {
    const sortedNum = toMin(num)
    return min === sortedNum;
  }
  for (let i = n - 1; i >= min; i--) {
    if (checkAnagram(i)) return i;
  }
  return -1;
}
```