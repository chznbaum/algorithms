# Astronaut Arrays

## Problem

Twelve people have walked on the Moon. They are:

* Neil Armstrong
* Buzz Aldrin
* Pete Conrad
* Alan Bean
* Alan Shepard
* Edgar Mitchell
* David Scott
* James Irwin
* John W Young
* Charles Duke
* Eugene Cernan
* Harrison Schmitt

You'll notice that these names are listed in the order that they first stepped on the Moon, not alphabetical order. To alphabetize them, it would make sense to write their names as `lastname, firstname`. For example: `Neil Armstrong` becomes `Armstrong, Neil`.

Finish the alphabetizer(`_names`) function, which takes in a names array (of length N) containing strings of names and returns an alphabetized array of names in `lastname, firstname` format.

## Solution

```
var moonWalkers = [
  "Neil Armstrong",
  "Buzz Aldrin",
  "Pete Conrad",
  "Alan Bean",
  "Alan Shepard",
  "Edgar Mitchell",
  "David Scott",
  "James Irwin",
  "John Young",
  "Charles Duke",
  "Eugene Cernan",
  "Harrison Schmitt"
];

function alphabetizer(names) {
    // Your code goes here!
    var moonArray = [];
    for (i = 0; i < names.length; i++) {
        moonArray.push(names[i].split(" "));
    }
    for (j = 0; j < moonArray.length; j++) {
        var temp = moonArray[j][0];
        moonArray[j][0] = moonArray[j][1];
        moonArray[j][1] = temp;
        moonArray[j] = moonArray[j].join(', ');
    }
    moonArray.sort();
    return moonArray;
}

// Try logging your results to test your code!
console.log(alphabetizer(moonWalkers));
```