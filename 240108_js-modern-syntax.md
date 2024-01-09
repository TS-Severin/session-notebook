### js modern syntax

object destruction is often happening in import-statements
=> objects are more often destructed than arrays

## destructuring

## rest operator ...

we can destructure objects and arrays

const person = {
name: 'sven',
age: 50
}

// classic way
// const name = person.name
//const age = person.age

// modern destructuring
const {name, age} = person
// order is irrelevant => as objects are unodered (no order in an object)

const {name, x} = person
// this would return 'sven' undefinded => no error here

console.log(name, age)
// output for both is the same: 'sven' 50

// creating alias in this way
const {name: personname, age} = person
// => assigns personname to name as if using const

// creating a default value
const {name, age, x = 7} = person
console.log(name, age, x)
// 'sven' 50 7

## destruct nested objects

const person = {
name: 'sven',
age: 50
adress: {
street: 'ritterstr.
}
}

console.log(name, age, adress: {street})

## operator ...

... => spread operator
or
=> rest operator

const person = {
name: 'sven',
age: 50
}

const {name, ...rest} = person;
// collects the rest

// difference array object => array is ordered => every item in an array has a certain index
// an object doesn't have that

## destruct arrays

const animals = ['cat', 'dog', 'mouse']

const [x, y] = animals
console.log(x, y) // => assigns variables to the items on the respective positions
// 'cat 'dog'

const animals = ['cat', 'dog', 'mouse']

const [, , y] = animals
console.log(y)
// => returns 'mouse'

const [cat, ...rest] = animals
console.log(rest)
// => ['dog', 'mouse']

// rest syntax

// function that sums everything without declaring the number of arguments
function sum(...args) {
console.log(args)
}
sum(2, 3, 2, 2)
// [2, 3, 2, 2] => returns exactly the arguments passed no matter how many

## spread operator ...

const numbers = [2, 4, 6, 8]

const copy = numbers

copy.push(10) // => changes object, so no copy possible from the array in the memory

## how to

const numbers = [2, 4, 6, 8]

const copy = [...numbers] // spreads all items in new array

copy.push(10) // => changes object, so no copy possible from the array in the memory

const numbers = [2, 4, 6, 8]
const chars = ['a', 'b', 'c']

const combined = [...numbers, ...chars]

console.log(combined);
// output: [ 2, 4, 6, 8, 'a', 'b', 'c' ]

const numbers = [2, 4, 6, 8]
const newNumber = 10
const allNumbers = [...numbers, newNumber] // witout numbers it would be an array and the newNumber => because numbers is an array
console.log(allnumbers)

## other use case

const persons = [{name: 'x'}, age: 35, {name: 'y', age: 25}]
// => i want to change the array so that every person gets the same age

persons.map(person => person) // returns same array

persons.map(person => {
return {...person, age: 50} // content spreads into new object => object is the same => but age is changed in all objects
})

// spread has to be first => has to be spreaded an than overwritten
