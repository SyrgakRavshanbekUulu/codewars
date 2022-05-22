# A small difference

## Descriptions
```
Write a function that given two strings determines if they differ by exactly one character.

The difference may consist of one charater being added, removed or replaced, in which case the function must return true. In all other cases it must return false.
```

## Examples
```c
tower / towe -> true
tower / towner -> true
tower / bower -> true
tower / token -> false
tower / tower -> false
```

# Solitions
```c
function oneCharDifference(s1, s2) {
  if (s1.length === 1 && s2.length === 1) return true
  const arr1 = s1.split("");
  const arr2 = s2.split("");
  let d1, d2;
  for (let i = 0; i < s1.length; i++) {
    d1 = arr1.indexOf(s1[i])
    d2 = arr2.indexOf(s1[i])
    if (d1 !== -1 && d2 !== -1) {
      arr1.splice(d1, 1);
      arr2.splice(d2, 1)
    }
  }
  return (arr1.length + arr2.length === 1 || (
      arr1.length === 1 && arr2.length === 1 &&
      d1 === d2
    )) ? true : false;
}
```