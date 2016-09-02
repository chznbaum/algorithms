# Repeat a string repeat a string

## Problem

Repeat a given string (first argument) `num` times (second argument). Return an empty string if `num` is not a positive number.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Global String Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

## Solution

```
function repeatStringNumTimes(str, num) {
  if (num > 0) {
  return str.repeat(num);
  } else
    return "";
}

repeatStringNumTimes("abc", 3);
```