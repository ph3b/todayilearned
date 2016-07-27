Today I learned that Object.keys of an empty array returns an empty array.
```javascript
const emptyArray = [];
Object.keys(emptyArray) // -> []
```
