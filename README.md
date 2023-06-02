# grange

## API

```js
// Create a simple range from start to end, inclusive
const [...foo] = grange(3, 6); // [3, 4, 5, 6]

// Increment by 2 instead of 1
const [...bar] = grange(2, 6, {step: 2}); // [2, 4, 6]

// Transform the output numbers with a transform function
const [...baz] = grange(1, 3, n => n * 2); // [2, 4, 6]

// Reverse the range by passing a larger value into the start position
const [...bif] = grange(3, 1); // [3, 2, 1]

// Create recurring loops
const loopGen = grange(1, 3, {loop: true});
const loop = range(0, 7).map(() => loopGen.next().value); // [1, 2, 3, 1, 2, 3, 1, 2]

// Start can be omitted -- defaults to 0
const [...omittedStart] = grange(6, n => n * 2, {step: 2}); // [0, 4, 8, 12]
```