# react global state

located on the top level via app:

- redux or zustand are the commonly used apps
- - redux is overengeneered
- - zustand is easier to use (better for trying)

> in general: global states should only be used if the other tools doesn't work any more => not everything has to be accessibale anywhere => it doesn't make it easier

## global state

moving the state up to app.js

```js
<Component {...pageProps} />
```

=> in the respective component we need to update the state and lift it up

=> part of the functionality moves to app.js
=> function and the state

```js
<Component {...pageProps} animals={animals} coutSum={countSum} />
```

=> all the values are being passed as a prop
=> they are calculated in App.js and passed to all components which need it

State organized in Array:

```js
const initialAnimals = [
  { id: 1, name: "Cats", count: 0 },
  { id: 2, name: "Dogs", count: 0 },
  { id: 3, name: "Sheep", count: 0 },
  { id: 4, name: "Dragons", count: 0 },
];
```

=> this array is updated each time on of the buttens is clicked

Function for Adding an animal:

```js
function handleAdd(animalId) {
  setAnimals(
    animals.map((animal) =>
      animal.id === animalId ? { ...animal, count: animal.count + 1 } : animal
    )
  );
}
```

=> is the animal id equal to the clicked id we need to increment in the count, we spread all the existing counts and count gets a new value
=> is the animal id not equal to the clicked, nothing changes

```js
function handleSubtract(animalId) {
  setAnimals(
    animals.map((animal) =>
      animal.id === animalId
        ? { ...animal, count: Math.max(0, animal.count - 1) }
        : animal
    )
  );
}
```

=> Math.max defines 0 as a max => the count can't be lesser than 0

=> the functions can then be passed as props down
=> we can then use them and they are being updated according to their funcitonality in App.js
=>
