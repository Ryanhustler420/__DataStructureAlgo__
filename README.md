# __DataStructureAlgo__
Code snippet for Data Structure And coding Interview Questions Set [MTCIDSPLUSA] { { READ_ONLY : true } } 

## Big O

```javaScript

const nemo = ['nemo'];
const everyone = ['dory','bruce','marlin','nemo','gill','bloat','nigel','squirt','darla','hank'];

const large = new Array(100000).fill('nemo'); // 100000 times nemo string fill in this array

function findNemo(array) {
  let t0 = performance.now();
  
  for(let i = 0; i < array.length; i++) {
    if(array[i] === 'nemo'){
      console.log('Found NEMO!');
    }
  }

  let t1 = performance.now();
  
  console.log('Call to find Nemo took ' + (t1 - t0) + ' milliseconds');
}

findNemo(large)

// output:-
// Call to find Nemo took 343.500000457898653 milliseconds 
// 0.34 seconds

```

> As input grows the output time will be different! depends on how powerfull CPU you have or different factor

**Big O is the language which tell us which Algorithem is Good and which one are bad! by campairing through functions and how many number of operation perform by that function! which is as good as how many operation a function has to perform. that will tell us the Big O**


## O(n) -> Linear Time

```javaScript

  const nemo = ['nemo']; // O(n) -> O(1) -> Linear Time
  const everyone = ['dory','bruce','marlin','nemo','gill','bloat','nigel','squirt','darla','hank']; // O(n) -> O(10) -> Linear Time
  const large = new Array(100000).fill('nemo'); // O(n) -> O(100000) -> Linear Time

  for(let i = 0; i < array.length; i++) {
    if(array[i] === 'nemo'){
      console.log('Found NEMO!');
    }
  }
  
  findNemo(large)

```

![imgBigOn](http://cooervo.github.io/Algorithms-DataStructures-BigONotation/images/graphs/linear.svg)


## O(1) -> Constant Time

```javaScript

function compressFirstBox(boxes) {
  console.log(boxes[0];
}

// Or 

function consoleLogBoxex(boxes) {
  console.log(boxes[0]); // O(1)
  console.log(boxes[1]); // O(1)
}

// O(2) = total time taken = where we remove constant terms! in this function that is the number '2'. so which is as good as O(1)
// meaning constant time -> O(1)

```

![imgBigO1](https://justin.abrah.ms/static/images/o_1__plot.png)

> no metter how much the size of array this function will always grabbing the first item! so This is Constant performance

##### Excercise Big O

```javaScript

// What is the Big O of the below function? (Hint, you may want to go line by line)
function funChallenge(input) {
  let a = 10; // O(1)
  a = 50 + 3; // O(1)

  for (let i = 0; i < input.length; i++) { // O(n)
    anotherFunction(); // O(n)
    let stranger = true; // O(n)
    a++; // O(n)
  }
  return a; // O(1)
}
// O(1) times 3 = O(3) = 3.
// O(n) times 4 = n + n + n + n = 4n.
// 3 + 4n
// ......
// BIG O(3 + 4n)
// but, at the end of the day this is just
// BIG O(n)

```

[What is the difference between big oh, big omega and big theta notations?](https://www.quora.com/What-is-the-difference-between-big-oh-big-omega-and-big-theta-notations)

```javaScript

// What is the Big O of the below function? (Hint, you may want to go line by line)

function anotherFunChallenge(input) {
  let a = 5; // O(1)
  let b = 10; // O(1)
  let c = 50; // O(1)
  for (let i = 0; i < input; i++) { // O(n)
    let x = i + 1; // O(n)
    let y = i + 2; // O(n)
    let z = i + 3; // O(n)

  }
  for (let j = 0; j < input; j++) { // O(n)
    let p = j * 2; // O(n)
    let q = j * 2; // O(n)
  }
  let whoAmI = "I don't know"; // O(1)
}

// O(4) + 4n + 3n
// BIG O(4 + 4n + 3n)
// BIG O(4 + 7n) <- which is as good as BIG O(n).

```
##### Drop The Constant

```javaScript

function printFirstItemThenFirstHalfThenSayHi100Times(items) {
    console.log(items[0]); // O(1)

    var middleIndex = Math.floor(items.length / 2); // O(1)
    var index = 0; // O(1)

    while (index < middleIndex) { // O(n/2)
        console.log(items[index]); // O(n/2)
        index++; // O(n/2)
    }

    for (var i = 0; i < 100; i++) { // O(100)
        console.log('hi'); // O(100)
    }
}

// O(n/2) + O(n/2) + O(n/2) = 3(n/2)
// O(1) + O(1) + O(1) + O(100) = O(103)
// O(n/2 + 103) > drop the constant
// O(n)

// Or
// O(n + 5000000) > will be O(n) > just drop the constant 

function compressBoxesTwice(boxes) {
  // itrating two times same step
  boxes.forEach((box) => {
    console.log(box); // O(n)
  }}
  
  boxes.forEach((box) => {
    console.log(box); O(n)
  }}
}

// O(n) + O(n) = O(2n)
// Drop the Constants
// O(n)

```
