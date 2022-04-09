# How many pages in a book?

## Description

```
Every book has n pages with page numbers 1 to n. The summary is made by adding up the number of digits of all page numbers.

Task: Given the summary, find the number of pages n the book has.

```

## Example

> If the input is summary=25, then the output must be n=17: The numbers 1 to 17 have 25 digits in total: 1234567891011121314151617.

## Note

  - Be aware that you'll get enormous books having up to 100.000 pages.
  - All inputs will be valid.

# Solitions

```c
function amountOfPages(summary){
  let res = 0;
  const counter = (num) => num.toString().length;
  while (summary) {
    summary -= counter(++res);
  }
  return res;
}
```
