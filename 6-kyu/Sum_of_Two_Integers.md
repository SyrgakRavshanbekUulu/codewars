# Sum of Two Integers

## Task

```
Given Two integers a , b , find The sum of them , BUT You are not allowed to use the operators + and -
```

## Notes

  - The numbers (a,b) may be positive , negative values or zeros .

  - Returning value will be an integer .

  - Javascript: the Array reduce methods are disabled, along with eval, require, and module .

## Input >> Output Examples
```c
1- Add (5,19) ==> return (24) 

2- Add (-27,18) ==> return (-9)

3- Add (-14,-16) ==> return (-30)

```

# Solitions

```c
function add(x, y) {
  const negOne = Math.cos(Math.PI)
  const xArr = new Array(Math.abs(x));
  const yArr = new Array(Math.abs(y));
  const sum = xArr.concat(yArr);
  if (x < 0 && y < 0) return negOne * xArr.concat(yArr).length;
  if (x >= 0 && y >= 0) return xArr.concat(yArr).length;
  if (Math.abs(x) === Math.abs(y)) return 0;
  if (Math.abs(x) > Math.abs(y)) {
    if (x > 0) return xArr.slice(0, yArr.length * negOne).length;
    return negOne * xArr.slice(0, yArr.length * negOne).length;
  }
  if (y > 0) return yArr.slice(0, xArr.length * negOne).length;
  return negOne * yArr.slice(0, xArr.length * negOne).length;  
}

```
