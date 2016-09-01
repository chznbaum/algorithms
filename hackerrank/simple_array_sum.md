# Simple Array Sum

## Problem

Given an array of `n` integers, can you find the sum of its elements?

**Input Format**

The first line contains an integer,`n` , denoting the size of the array. 
The second line contains `n` space-separated integers representing the array's elements.

**Output Format**

Print the sum of the array's elements as a single integer.

**Sample Input**

```
6
1 2 3 4 10 11
```

**Sample Output**

```
31
```

**Explanation**

We print the sum of the array's elements, which is: `1 + 2 + 3 + 4 + 10 + 11 = 31`.

## Solution

```
process.stdin.resume();
process.stdin.setEncoding('ascii');

var input_stdin = "";
var input_stdin_array = "";
var input_currentline = 0;

process.stdin.on('data', function (data) {
    input_stdin += data;
});

process.stdin.on('end', function () {
    input_stdin_array = input_stdin.split("\n");
    main();    
});

function readLine() {
    return input_stdin_array[input_currentline++];
}

/////////////// ignore above this line ////////////////////

function main() {
    var n = parseInt(readLine());
    arr = readLine().split(' ');
    arr = arr.map(Number);
    
    var sum = 0;
    for (i = 0; i < n; i++) {
        sum += arr[i];
    }
    console.log(sum);
}

```