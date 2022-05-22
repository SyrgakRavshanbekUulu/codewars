# Strip Comments

## Descriptions
```
Complete the solution so that it strips all text that follows any of a set of comment markers passed in. Any whitespace at the end of the line should also be stripped out.
```

## Examples
Given an input string of:
```
apples, pears # and bananas
grapes
bananas !apples
```
The output expected would be:
```
apples, pears
grapes
bananas
```
The code would be called like so:

```c
var result = solution("apples, pears # and bananas\ngrapes\nbananas !apples", ["#", "!"])
// result should == "apples, pears\ngrapes\nbananas"
```

# Solitions
```c
function solution(input, markers) {
  let enter = input.split('\n')
  for (let marker of markers) {
    enter = enter.map(e => e.split(marker)[0].trim())
  }
  return enter.join('\n')
};
```