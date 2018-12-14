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

> Remove Constant

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
##### When Two Different Args Sizes

```javaScript

function compressBoxesTwice(boxes, boxes2){
  boxes.forEach((box) => {
    console.log(box);
  })
  
  boxes2.forEach((box) => {
    console.log(box);
  })
}

// O(2n) > O(n) > Wrong!
// O(a + b) || O(n + m) > Right

function compressBoxesTwice(boxes, boxes2){
  boxes.forEach((box) => {
    console.log(box);
    boxes2.forEach((box) => {
        console.log(box);
    })
  })
}

// O(a*b) > Nested Loop > Trick For Knowing this Notation is when Loop are inside Loop that where '*' works
// O(a + b) > pararell Loop >  Trick For Knowing this Notation is when Loop are Pararell aka Indented At same Level '+' works

```


## O(n^2) -> Quadratic Time 

> Different Terms of Input

![imgBigOn^2](https://4.bp.blogspot.com/-hLg6KKtR6UQ/WQIx98yZswI/AAAAAAAA2dI/9W7WYkKB8Gca7y_aZArPakvRfvYFJ7ApQCLcB/s1600/yaacovapelbaumbigoplot.jpg)

```javaScript

// Log all pairs of array

const boxes = [...Array(5).keys()];

for(let i = 0; i < boxes.length; i++ ){
  for(let j = 0; j < boxes.length; j++){
    console.log([boxes[i], boxes[j]])
  }
}

// Output

[ 0, 0 ]
[ 0, 1 ]
[ 0, 2 ]
[ 0, 3 ]
[ 0, 4 ]
[ 1, 0 ]
[ 1, 1 ]
[ 1, 2 ]
[ 1, 3 ]
[ 1, 4 ]
[ 2, 0 ]
[ 2, 1 ]
[ 2, 2 ]
[ 2, 3 ]
[ 2, 4 ]
[ 3, 0 ]
[ 3, 1 ]
[ 3, 2 ]
[ 3, 3 ]
[ 3, 4 ]
[ 4, 0 ]
[ 4, 1 ]
[ 4, 2 ]
[ 4, 3 ]
[ 4, 4 ]


// O(n * n) > O(n^2) > Quadratic Time 

// ES5 

function logAllPairsOfBoxes(boxes) {
  boxes.forEach(function(firstBox) {
    boxes.forEach(function(seconBox) {
      console.log([firstBox, seconBox])
    })
  })
}

// O(n * n) > O(n^2) > Quadratic Time 

```

```javaScript

function printAllNumbersThenAllPairSums(numbers) {

  console.log('these are the numbers:');
  numbers.forEach(function(number) {
    console.log(number);
  });

  console.log('and these are their sums:');
  numbers.forEach(function(firstNumber) {
    numbers.forEach(function(secondNumber) {
      console.log(firstNumber + secondNumber);
    });
  });
}

printAllNumbersThenAllPairSums([1,2,3,4,5])

// O(n) + O(n^2)
// O(2n^2)
// O(n^2) Just keep the dominant term and drop non dominant term
// care about the most important term
// so we drop 'n'
// because the power of 'n^2' is way more than 'n'. so it wont hurt if we drop that non dominant term. as simple as that

// for example (drop non dominant term)

// O(x^2+3x+100+x/2)
// again we worry about the most dominant term 
// because x^2 is the most significant

// Simplify
// let x = 500;
// O((5^2)+(3*5)+100+(5/2))
// O(250000 + 1500 + 100 + 250)
// O(250000) > all 100, which is non dominant
// O(x^2) > drop all the non dominant term!

// it would be least important if you take x = 5 ! but, for large input it will shine

function O(numbers) {
  numbers.forEach(function(firstNumber) {
    numbers.forEach(function(secondNumber) {
      numbers.forEach(function(thirdNumber) {
        console.log(firstNumber + secondNumber + thirdNumber);
      });
    });
  });
}

// O(n^3) > because 3 nested loop > BAD IDEA

```

# Big O Cheat Sheet: 

  - Big Os
  
    - [x] **O(1)** Constant- no loops
    - [x] **O(n)** Linear- for loops, while loops through n items
    - [x] **O(n^2)** Quadratic- every element in a collection needs to be compared to ever other element. Two nested loops
    - [ ] **O(2^n)** Exponential- recursive algorithms that solves a problem of size N 
    - [X] **O(n!)** Factorial- you are adding a loop for every element
    - [ ] **O(log N)** Logarithmic- usually searching algorithms have log n if they are sorted (Binary Search) 
    - [ ] **O(n log(n))** Log Liniear- usually sorting operations
  
**Iterating through half a collection is still O(n)**

**Two separate collections: O(a * b)**

## What can cause time in a function?

- Operations (+, -, *, /) 
- Comparisons (<, >, ==) 
- Looping (for, while) 
- Outside Function call (function()) 

## Rule Book

Rule 1: Always worst Case 
Rule 2: Remove Constants 
Rule 3: Different inputs should have different variables. O(a+b). 
    A and B arrays nested would be O(a*b) 
    + for steps in order 
    * for nested steps 
Rule 4: Drop Non-dominant terms 

## What causes Space complexity?

- Variables 
- Data 
- Structures 
- Function Call 
- Allocations

> [Big O Chart](http://bigocheatsheet.com/)

## O(n!) -> Evil 

> [Example](https://stackoverflow.com/questions/3953244/example-of-on)


# 3 Pillars Of Programing

- What is good code?
  - Readable
  - Scalable
    - Time And Speed
    - Memory
 
 - Which code is best?
   - Readable
   - Speed [Time Complexity]
   - Memory [Space Complexity]
 

# Space Complexity

> When a program execute it has two ways to remember things. The Heap and The Stack
- Heap = where we store variable that we assign
- Stack = where we keep track the functions call

- sometime we want to optimize for using less memory instead of using less time. Talking about memory or space complexity is very similar to talking about the time cost. we simply look at the total size relative to the size of the input and see how many new variable or new memory ware allocating how much memory is being used.

## Example 

```javaScript

// Space complexity O(1)
function boooo(n) {
    for (let i = 0; i < n; i++) {
        console.log('booooo');
    }
}

// Space complexity O(n)
function arrayOfHiNTimes(n) {
    var hiArray = [];
    for (let i = 0; i < n; i++) {
        hiArray[i] = 'hi';
    }
    return hiArray;
}

arrayOfHiNTimes(6)

```

# Interview Cheat Sheet

## The 3 pillars of good code: 

1. Time Complexity
2. Space Complexity
3. Readable

## What skills interviewer is looking for: 
- Analytic Skills - How can you think through problems and analyze things? 
- Coding Skills - Do you code well, by writing clean, simple, organized, readable code? 
- Technical knowledge - Do you know the fundamentals of the job you're applying for? 
- Communication skills: Does your personality match the companies’ culture? 

## Step By Step through a problem:

1 - When the interviewer says the question, write down the key points at the top (i.e. sorted array). Make sure you have all the details. Show how organized you are.

2 - Make sure you double check: What are the inputs? What are the outputs?

3 - What is the most important value of the problem? Do you have time, and space and memory, etc.. What is the main goal?

4 - Don't be annoying and ask too many questions.

5 - Start with the naive/brute force approach. First thing that comes into mind. It shows that. you’re able to think well and critically (you don't need to write this code, just speak about it).

6 - Tell them why this approach is not the best (i.e. O(n^2) or higher, not readable, etc...).

7 - Walk through your approach, comment things and see where you may be able to break things. Any repetition, bottlenecks like O(N^2), or unnecessary work? Did you use all the information the interviewer gave you? Bottleneck is the part of the code with the biggest Big O. Focus on that. Sometimes this occurs with repeated work as well.

8 - Before you start coding, walk through your code and write down the steps you are going to follow.

9 - Modularize your code from the very beginning. Break up your code into beautiful small pieces. and add just comments if you need to.

10  - Start actually writing your code now. Keep in mind that the more you prepare and understand. what you need to code, the better the whiteboard will go. So never start a whiteboard interview not being sure of how things are going to work out. That is a recipe for disaster. Keep in mind: A lot of interviews ask questions that you won’t be able to fully answer on time. So think: What can I show in order to show that I can do this and I am better than other coders. Break things up in Functions (if you can’t remember a method, just make up a function and you will at least have it there. Write something, and start with the easy part.

11  - Think about error checks and how you can break this code. Never make assumptions about the input. Assume people are trying to break your code and that Darth Vader is using your function. How will you safeguard it? Always check for false inputs that you don’t want. Here is a trick: Comment in the code, the checks that you want to do… write the function, then tell the interviewer that you would write tests now to make your function fail (but you won't need to actually write the tests).

12  - Don’t use bad/confusing names like i and j. Write code that reads well.

13  - Test your code: Check for no params, 0, undefined, null, massive arrays, async code, etc… Ask the interviewer if we can make assumption about the code. Can you make the answer return an error? Poke holes into your solution. Are you repeating yourself?

14  - Finally talk to the interviewer where you would improve the code. Does it work? Are there different approaches? Is it readable? What would you google to improve? How can performance be improved? Possibly: Ask the interviewer what was the most interesting solution you have seen to this problem

15  - If your interviewer is happy with the solution, the interview usually ends here. It is also common that the interviewer asks you extension questions, such as how you would handle the problem if the whole input is too large to fit into memory, or if the input arrives as a stream. This is a common follow-up question at Google, where they care a lot about scale. The answer is usually a divide-and-conquer approach — perform distributed processing of the data and only read certain chunks of the input from disk into memory, write the output back to disk and combine them later.

## Good code checklist:

- [ ] It works 
- [ ] Good use of data structures 
- [ ] Code Re-use/ Do Not Repeat Yourself 
- [ ] Modular - makes code more readable, maintainable and testable 
- [ ] Less than O(N^2). We want to avoid nested loops if we can since they are expensive. Two separate loops are better than 2 nested loops 
- [ ] Low Space Complexity --> Recursion can cause stack overflow, copying of large arrays may exceed memory of machine

## Heurestics to ace the question:
- [ ] Hash Maps are usually the answer to improve Time Complexity 
- [ ] If it's a sorted array, use Binary tree to achieve O(log N). Divide and Conquer - Divide a data set into smaller chunks and then repeating a process with a subset of data. Binary search is a great example of this 
- [ ] Try Sorting your input 
- [ ] Hash tables and precomputed information (i.e. sorted) are some of the best ways to optimize your code 
- [ ] Look at the Time vs Space tradeoff. Sometimes storing extra state in memory can help the time. (Runtime) 
- [ ] If the interviewer is giving you advice/tips/hints. Follow them 
- [ ] Space time tradeoffs: Hastables usually solve this a lot of the times. You use more space, but you can get a time optimization to the process. In programming, you often times can use up a little bit more space to get faster time

**And always remember:** Communicate your thought process as much as possible. Don’t worry about finishing it fast. Every part of the interview matters.

## Arrays

```javaScript

const strings= ['a', 'b', 'c', 'd'];
const numbers = [1,2,3,4,5];
// Variable array is somewhere in memory and the computer knows it.
// When I do array[2], i'm telling the computer, hey go to the array and grab the 3rd item from where the array is stored.


//push
strings.push('e');

//pop
strings.pop();
strings.pop();

//unshift
strings.unshift('x')

//splice
strings.splice(2, 0, 'alien');

console.log(strings)

```

## Implementation Array DS

```javaScript

class MyArray {
  constructor() {
    this.length = 0;
    this.data = {};
  }
  get(index) {
    return this.data[index];
  }
  push(item) {
    this.data[this.length] = item;
    this.length++;
    return this.data;
  }
  pop() {
    const lastItem = this.data[this.length - 1];
    delete this.data[this.length - 1];
    this.length--;
    return lastItem;
  }
  deleteAtIndex(index) {
    const item = this.data[index];
    this.shiftItems(index);
    return item;
  }
  shiftItems(index) {
    for (let i = index; i < this.length - 1; i++) {
      this.data[i] = this.data[i + 1];
    }
    console.log(this.data[this.length - 1]);
    delete this.data[this.length - 1];
    this.length--;
  }
}

const myArray = new MyArray();
myArray.push('hi');
myArray.push('you');
myArray.push('!');
myArray.pop();
myArray.deleteAtIndex(0);
myArray.push('are');
myArray.push('nice');
myArray.shiftItems(0);
console.log(myArray);

```

## Reverse String 

```javaScript

function reverse(str){

  if(!str && str.length < 2 && typeof(str) !== 'string')
  {
    return 'Single AF'
  }  
  const length = str.length - 1;
  const reverseSentence = []; 
  
  for(let index = length; index >= 0; index--){
    reverseSentence.push(str[index]);
  }

  return reverseSentence.join('').trim();
}

const reverse2 = str => {
  return str.split('').reverse().join('');
}

const reverse3 = str => str.split('').reverse().join('');

const reverse4 = str => [...str].reverse().join('');

reverse('My name is gaurav gupta');
reverse2('My name is gaurav gupta');
reverse3('My name is gaurav gupta');
reverse4('My name is gaurav gupta');

```

## Hash Tables

> [MD5](http://www.miraclesalad.com/webtools/md5.php) - MDS Algo for hashing data one direction

> [Hash Tables](https://en.wikipedia.org/wiki/Hash_table) - Wikipidia

> [Hash Tables Animation](https://www.cs.usfca.edu/~galles/visualization/OpenHash.html) - You Can See Data Operation in Hash Tables Real Time

> [Compairson of Programming languages](https://en.wikipedia.org/wiki/Comparison_of_programming_languages_(associative_array))


##### Hash Tables As Object in JS

```javaScript
 let user = {
  age: 54,
  name: 'Kylie',
  magic: true,
  scream: function() {
    console.log('ahhhhhh!');
  }
};

user.age;
user.spell = 'abra kadabra';
user.scream()

//Map --> Gives you some order
//Set --> No duplicate keys
```

## Hash Tables Code Example

```javaScript

class HashTable {
  constructor(size){
    this.data = new Array(size);
  }

  set(string, number) {
    const index = this._hash(string);
    
    // handling collision if occurs
    if(!this.data[index]) {
      this.data[index] = [];
    }
    
    this.data[index].push([string, number]);
    return this.data;
  }

  get(string) {
    const index = this._hash(string);
    const data = this.data[index];

    if(data) {
      for(let i = 0; i < data.length; i++) {
        if(data[i][0] === string){
            return data[i][1];
        }
      }
    }
    return undefined;
  }
  
  // this is hash function which generate index on the basis of String length and String itself
  _hash(key) { // the _ meaning this function should only be use as private function and not directly with instence! you should not! but technically you can!
    let hash = 0;
    for (let i =0; i < key.length; i++){
        hash = (hash + key.charCodeAt(i) * i) % this.data.length
    }
    return hash;
  }
  
}

const myHashTable = new HashTable(50);
myHashTable.set('grapes', 10000)
myHashTable.set('apples', 10001)

myHashTable.get('apples');

```
