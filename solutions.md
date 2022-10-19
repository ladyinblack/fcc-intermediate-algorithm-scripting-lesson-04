## ALTERNATE SOLUTIONS

### Solution 1
```js
function whatIsInAName(collection, source) {
    // "What's in a name? that which we call a rose 
    // By any other name would smell as sweet."
    // -- by William Shakespear, Romeo and Juliet 
    const sourceKeys = Object.keys(source);
    
    // filter the collection 
    return collection.filter(obj => {
        for (let i = 0; i < sourceKeys.length; i++) {
            if (!obj.hasOwnProperty(sourceKeys[i]) || obj[sourceKeys[i]] !== source[sourceKeys[i]]) {
                return false;
            }
        }
        return true;
    });
}
```

### Code Explanation
- We filter through the array using `.filter()`.
- Using a `for` loop we loop through each item in the object.
- We use an `if` statement to check if the object in the collection doesn't have the key and the property value doesn't match the value in source.
- We return `false` if the above `if` statement is correct.  Otherwise, we return `true`.

### REFERENCE LINKS
- [`For` Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
- [`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [`Object.hasOwnProperty()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

### Solution 2
```js
function whatIsInAName(collection, source) {
    // "What's in a name? that which we call a rose 
    // By any other name would smell as sweet."
    // -- by William Shakespeare, Romeo and Juliet 
    const sourceKeys = Object.keys(source);
    
    return collection.filter(obj => sourceKeys.every(key => obj.hasOwnProperty(key) && obj[key] === source[key]));
}
```

### Code Explanation
- We filter through the collection using `.filter()`.
- Next, we return a `Boolean` value for the `.filter()` method.
- Finally, we reduce to `Boolean` value to be returned for the `.every()` method.

## REFERENCE LINKS
- [`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [`Array.prototype.every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
- [`Object.hasOwnProperty()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

### Solution 3
```js
function whatIsInAName(collection, source) {
    // "What's in a name? that which we call a rose 
    // By any other name would smell as sweet." 
    // -- by William Shakespeare, Romeo and Juliet 
    const sourceKeys = Object.keys(source);
    
    // filter the collection
    return collection.filter(obj => sourceKeys.map(key => obj.hasOwnProperty(key) && obj[key] === source[key]).reduce(((a, b) => a && b));
}
```

### Code Explanation
- We start by filtering through `collection` using `Array.filter()`.
- Next, we map through all keys and return Boolean values based on the check conditions: both the key and its corresponding value must exist within the object we are filtering through.
- Then we reduce the mapped Boolean values to a single Boolean that indicates whether all srcKeys pass the conditions checked above.
- This single Boolean will be used to filter through the collection.

### REFERENCE LINKS
- [`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [`Array.prototype.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
- [`Object.hasOwnProperty()`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

