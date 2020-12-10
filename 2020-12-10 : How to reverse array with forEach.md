As title,  
How do we loop array in reverse way with forEach?  
Simple, we can acheive this just with the native arguments:  

```js
var array = [1, 2, 3];

// We don't need the first arugument since we want to reverse it
array.forEach((theElement, index, theArray) => {
  const revElement = theArray[theArray.length-1-index];
  console.log(revElement);
});
```
