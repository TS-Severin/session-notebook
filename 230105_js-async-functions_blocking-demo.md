### can delay functionality

- creating a loop that runs for a certain time

function blockMainThreadFor5Seconds() {
while (Date.now() - start < 5000) {
// Do nothing
}
}

- If js is executing one function it can't run another

- How can we deal with this?

- we need to know when the background command is finished

setTimeout(() => {console.log("callback function")}, 3000);

=> setTimeout accepts two arguments: a callback function and a number of miliseconds

### promise object

- promise has to kinds of states: pending && settled,fulfilled,resolved || rejected)
- promise is part of the js language

**promise-object provieds methods:**

**then**

=> if it is settled => do something elese

## keyword **await**

await animateBall(soccer); => can be used inside async function => will be called when async function is done

async ()

=> async function

## in general

declare funciton

async funciton myFunction() {
return 42
}

console.log("my Function: ", myFunction());

=> async keyword makes that it doesn't only return the value but also a promise-state => in this case => fullfilled

async-functions always return a promise-state

myFunction().then((result) => {
console.log("result: ", result);
})

(async function() {
const result = await myFunction()
console.log(result);
})()

### try and catch (excusivly for errors)

function throwError() {
throw new Error('error thrown')
}
try {
throwError()
} catch (e) {
console.log('there was something wrong');
} finally {
console.log('finally');
console.log(data);
}

=> try/catch take control over an error => an error interrrupts the application-error
=> try/catch can give a message to the user so that they can interact

### Method: Promise.all([])

=> creates array of promises

### async function

- main idea: we fetch data, we need to wait => while waiting we don't have to wait we get the promise => something happens already and it doesn't block the whole app
- we can make the promise run a certain animation or something so that it shows the user that it's working
- it prevents blocking
- to be save we build in try/catch
