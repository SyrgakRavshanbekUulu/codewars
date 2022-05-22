# Find the missing term in an Arithmetic Progression

## Description
```
An Arithmetic Progression is defined as one in which there is a constant difference between the consecutive terms of a given series of numbers. You are provided with consecutive elements of an Arithmetic Progression. There is however one hitch: exactly one term from the original series is missing from the set of numbers which have been given to you. The rest of the given series is the same as the original AP. Find the missing term.

You have to write a function that receives a list, list size will always be at least 3 numbers. The missing term will never be the first or last one.
```
## Examples
```c
findMissing([1, 3, 5, 9, 11]) == 7
```
# Solitions
```c
var findMissing = function (list) {
  const firstInterval = list[1] - list[0];
  for (let i = 1; i < list.length - 1; i++) {
    const interval = list[i + 1] - list[i];
    if (firstInterval !== interval) {
      return Math.abs(interval) > Math.abs(firstInterval) ? 
        list[i] + firstInterval :
        list[i] - interval;
    }
  }
}
```