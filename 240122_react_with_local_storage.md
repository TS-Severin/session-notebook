### react with local storage

**store date so that it is persistend across sessions**

-local storage
-session storage

local storage: key: value-pairs

Web Storage API
=> client site => part of the browser
=> storage in browser only in browser
=> sensitive data shouldn't be stored here

=> we can see session storage and local storage in the dev tools in app

## session storage

-as long as the browser is open

## local storage

-persistend when browser is closed
-gets deleted when clearing the browser cache
-storage is more than 5mb, much more than a cookie

key: value-pairs => it can only be strings

### code in vanilla js

// target button and banner
const button = document.querySelector("#cookiebanner button");
const cookieBanner = document.querySelector("#cookiebanner");

// we can refert to the stored data now

const consent = localStorage.getItem("consent");
// if(consent === "ok") {
cookieBanner.style.display ="none";
}

// add event listener and set it to
// store key value pair: "consent: ok" in local storage

button.addEventListener("click", () => {
cookieBanner.style.display = "none";
localStorage.setItem("consent", "ok")
})

**in the local storage everything will be stringyfied**
=> only strings can be stored

// we need to stringyfy it to store it in the local storage

localStorage.setItem("person",
JSON.stringify({name: "klaus", age: 34}))

// when retrieving it from the local storage we have to go the other way around:

const javaScriptObject = localStorage.jetItem("person")
JSON.parse(javaScriptObject)
=> it is an object again

##

methods:

setItem(arg1, arg2)
arg1 => key
arg2 => value

getItem(arg1)
arg1 => call key

### storage in react

**step 1**

=> in the useState-Hook we have to make a change

npm i useLocalStorageState

import useLocalStorageState from "use-local-storage-state"

useLocalStorageState()

**step 2**

add key which always looks like this:

const [todos, setTodos] = useLocalStorageState("todos", {defaultValue: []}

=> react translates the string from js in an array of objects
