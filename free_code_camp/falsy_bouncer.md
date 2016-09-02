# Falsy Bouncer

## Problem

Remove all falsy values from an array.

Falsy values in JavaScript are `false`, `null`, `0`, `""`, `undefined`, and `NaN`.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Boolean Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
* [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Solution

```
function bouncer(arr) {
  var newArr = [];
  for (i = 0; i < arr.length; i++) {
  if (Boolean(arr[i]) !== false) {
    newArr.push(arr[i]);
  }
} return newArr;
}

bouncer([7, "ate", "", false, 9]);
```