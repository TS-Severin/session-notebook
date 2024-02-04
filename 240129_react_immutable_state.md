### react immutable state

you can't change a state in react, you write it again => no string is equal

=> we can't change an object which is a state
=> in order to make a component rerender always new data is needed

```js

const initObj {
    name: "Alan",
    job: "teacher",
}

export default function ImmutableState( {
    const [obj, setObj] = useState(initObj);
})

const handleClick = () => {

setObj((prev) => { return {...prev,name: prev.name === "Alan" ? "Marcell": "Alan"}
})

};
```

same goes with arrays:

```js
setArr((prev) => {
  return;
  [...prev, e.target.add.value];
});
```

=> immer helps to circumvent to much fuss about set statusses anew
