# Confirm the Ending

## Problem

Check if a string (first argument, `str`) ends with the given target string (second argument, `target`).

This challenge can be solved with the `.endsWith()` method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.

Remember to use **Read-Search-Ask** if you get stuck. Write your own code.

Here are some helpful links:

* [String.prototype.substr()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)
* [String.prototype.substring()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)

## Solution

```
function confirmEnding(str, target) {
  //Select the ending characters in str, equal in length to the target
  var ending = str.substring(str.length - target.length);
  if (ending === target) {
    return true;
  } else
    return false;
}

confirmEnding("Bastian", "n");
```