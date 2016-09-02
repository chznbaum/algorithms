# Seek and Destroy

## Problem

You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
* [Array.prototype.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

## Solution

```
function destroyer(arr) {
  // Remove all the values
  var args = Array.prototype.slice.call(arguments);
  var newArray = args.shift();
  return newArray.filter(function(x) {
    return args.indexOf(x) === -1;
  });
  
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```