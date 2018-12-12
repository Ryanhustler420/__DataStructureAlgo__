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
