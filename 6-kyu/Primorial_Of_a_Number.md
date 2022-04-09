# Primorial Of a Number
## Description

```
Is similar to factorial of a number, In primorial, not all the natural numbers get multiplied, only prime numbers are multiplied to calculate the primorial of a number. It's denoted with P# and it is the product of the first n prime numbers.

Given a number N , calculate its primorial.

```
### Notes
> Only positive numbers will be passed (N > 0) .

## Input >> Output Examples:

```c
1- numPrimorial (3) ==> return (30)
```
### Explanation
> Since the passed number is (3) ,Then the primorial should obtained by multiplying 2 * 3 * 5 = 30.
**Mathematically written as , P3# = 30**


```c
2- numPrimorial (5) ==> return (2310)
```
### Explanation
> Since the passed number is (5) ,Then the primorial should obtained by multiplying 2 * 3 * 5 * 7 * 11 = 2310 .
**Mathematically written as , P3# = 30**

```c
3- numPrimorial (6) ==> return (30030)
```
### Explanation
> Since the passed number is (6) ,Then the primorial should obtained by multiplying 2 * 3 * 5 * 7 * 11 * 13 = 30030 .
**Mathematically written as , P6# = 30030 .**

# Solitions

```c
function numPrimorial(n){
  let mult = 1, i = 2;
  const primes = [];
  const isPrime = (num) => {
    for (let i = 2; i < num; i++) {
      if (num % i === 0) return false;
    }
    return true;
  }
  while (primes.length !== n) {
    if(isPrime(i)) {
      mult *= i;
      primes.push(i);
    }
    i++;
  }
  return mult;
}
```



