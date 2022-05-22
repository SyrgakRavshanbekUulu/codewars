# Look and say numbers

## Description
```
There exists a sequence of numbers that follows the pattern

          1
         11
         21
        1211
       111221
       312211
      13112221
     1113213211
          .
          .
          .
Starting with "1" the following lines are produced by "saying what you see", so that line two is "one one", line three is "two one(s)", line four is "one two one one".

Write a function that given a starting value as a string, returns the appropriate sequence as a list. The starting value can have any number of digits. The termination condition is a defined by the maximum number of iterations, also supplied as an argument.
```

# Solitions
```c
function lookAndSay(data,len){
  const res = [];
  while (len--) {
    let newData = "";
    let count = 1;
    for (let i = 0; i < data.length; i++) {
      if (data[i] === data[i + 1]) {
        count++;
      } else {
        newData += count.toString() + data[i];
        count = 1;
      }
    }
    data = newData;
    res.push(newData);
  }
  return res;
}
```