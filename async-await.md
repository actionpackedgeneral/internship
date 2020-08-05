# Async/await

## Async functions

The `async` keyword can be placed before a function. Means a function will return a promise

```JS
async function f(){
    return 1;
}
```

## Await

```JS
let value = await promise;
```

`await` makes JS wait until promise settles and return the result. It suspends the function execution until the promsie settles. You cannot use await in regular functions
