# nth-most-frequent-element

## Description
Given a list of integers, create a function that returns the nth-rarest item. The function, should be called nth_most_rarest_item(list,n) and its signature should look like this `nth_most_rarest_item(list,n)`; where list is the array of integers and n is the nth rarest term. For example in `([5,4,5,4,5,4,4,5,3,3,3,2,2,1,5], 2)`, if 2 is supplied as n, the answer is 2 as 2 is the 2nd rarest item.

## code
```javascript
const nth_most_rarest_item = (list,n) => {
  const counts = {};

  for (const num of list) {
    counts[num] = counts[num] ? counts[num] + 1 : 1;
  }

  const sorted = Object.entries(counts).sort((a, b) => a[1] - b[1]);

  const nthRarestElement = sorted[n - 1][0];

  return nthRarestElement;
}

console.log(nth_most_rarest_item([5, 4, 5, 4, 5, 4, 4, 5, 3, 3, 3, 2, 2, 2, 1, 5], 2)); // 2
console.log(nth_most_rarest_item([5, 4, 5, 4, 5, 4, 4, 5, 3, 3, 2, 2, 2, 1, 5], 2)); // 3
```
