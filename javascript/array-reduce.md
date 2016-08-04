Today I learned array.reduce();
```javascript
const someArray = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, ,10];
const reduceResult = someArray.reduce((prevValue, currentValue, currentIndex, startArray) => {
  if(currentValue !== 0 && currentValue % 2 === 0) prevValue.push(currentValue);
  return prevValue;
}, [])
console.log(reduceResult); // -> [2, 4, 6, 8, 10]
```
`startArray = []`, will not change.
