### adding functionality to react

function Counter() {
let counter = 0;
return <button onClick={() => {counter++; console.log(counter)}}>You have clicked this button {counter} times</button>;
}

=> component function is now executed once, so the counter doesn't update
=> the counter doesn't execute the function again

=> Way out

**component states**

import {useState} from "./styles.css";

=> gets the initial value of our state and the return value is an array

import {useState} from "./styles.css";
// useState function makes that it is loaded again

function Counter() {
const [counter, setCounter] = useState(0)
// this it the convention for adding functinality
// it is a short cut for:
// const stateArray = useState(0)
// const counter = stateArray[0]
// const setCounter = stateArray[1]
let counter = 0;
return <button onClick={() => {setCounter(counter + 1);}}>You have clicked this button {counter} times</button>;
}

const counter => value
setCounter => convention to use set as part of the functin name

setter function => reassigend the useState => it can't be reassigned otherwise

=> states are not persistend => the page starts with 0 when refresh
=> state is local to the component
=> they are also called component state

=> very important:
=> console.log must be set beneath the const for the useState
=> if it is behind the counter function it doesn't update

function Counter() {
const [counter, setCounter] = useState(0)
// console.log goes here:
console.log(counter);
let counter = 0;
return <button onClick={() => {setCounter(counter + 1);}}>You have clicked this button {counter} times</button>;
}

## multiple states in a single component

=> with boolean values we often use varialbes like isVegan
=> the is is a convention to show immediatly that it is a boolean

First challenge (box):

import { useState } from "react";
import "./styles.css";

export default function App() {
// let isActive = false;
const [isActive, setIsActive] = useState(false);

function handleClick() {
setIsActive(!isActive);
// Check that the value changes correctly.
console.log(isActive);
}

return (

<main>
<div className={`box ${isActive ? "box--active" : ""}`} />
<button onClick={handleClick}>Activate</button>
</main>
);
}

### journal app favorite button

import { useState } from "react";
import "./FavoriteButton.css";
import { ReactComponent as StarFilled } from "./star-filled.svg";
import { ReactComponent as Star } from "./star.svg";

export default function FavoriteButton() {
// this should be a state variable
// const isFavorite = false;
const [isFavorite, setIsFAvorite] = useState(false);

return (
<button
className="favorite-button"
onClick={() => {
setIsFAvorite(!isFavorite);
console.log("favorite button clicked");
}}
aria-label="favorite" >
{isFavorite ? <StarFilled /> : <Star />}
</button>
);
}

additional class for admin:

.tag--highlight {
color: var(--color-nemo);
}

{role === "admin" ? }
