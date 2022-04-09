# String array duplicates

## Description

```
In this Kata, you will be given an array of strings and your task is to remove all consecutive duplicate letters from each string in the array.

For example:

  * dup(["abracadabra","allottee","assessee"]) = ["abracadabra","alote","asese"].

  * dup(["kelless","keenness"]) = ["keles","kenes"].

Strings will be lowercase only, no spaces. See test cases for more examples.

```

# Solitions

```c

function dup(s) {
  return s.map((str) => {
    let res = "";
    for (let i = 0; i < str.length; i++) {
      if (str[i] != str[i + 1]) res += str[i];
    }
    return res;
  })
};

```