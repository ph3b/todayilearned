Today I learned that you can use console.time to time the duration of code block

```javascript
console.time('identifier');
for(var i = 0; i < 5000; i++) {
  someExpensiveCalculation();
}
console.timeEnd('identifier');
```
