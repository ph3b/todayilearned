Today I learned that you can rename destructured variables from objects:

```javascript
const object = {
  slogan: "Make Ecmascript great again"
};

const {slogan: greatSlogan} = object;
console.log(greatSlogan); // -> Make Ecmascript great agai
```
