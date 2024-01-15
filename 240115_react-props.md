### react props

- props transpfer data from one place to another
- like creating components
- but with react its easier
- we create a component and when we need it we import it
- how can we pass different info to the same card
- we did that inside the funciton
- here we need props
- we pass props to a card
- a prop can be an array or an object or whatever
- different data in the same ui component

## main concept of react is functions

- we can create components in the same file
  => it is just another function

- calling a function in react is a tag <Pet />
- i can call the function n times and create the element n times
- to pass new content we need

## **props**

- i use my function for a given element in an extra folder
- i export the funciton and import it in App.js
- then i pass the content:

  - for that we add something looking like attributes
  - function has the argument Pet(props) {}
  - <Pet sound="Meow" name="Cat" />

  - in react we destruct in right away:
    - Pet({name, sound}){
      return (
      <p>{name}</p>
      <p>{sound}</p>
      )
      }

- we can now change the function call: <Pet sound="Woof" name="Dog" />
- we pass from App to the component
- passing back is difficult

## pass function to component

- when using function: onHandleAnimal={handleAnimal}

**Component:**

Pet({name, sound, onHandleAnimal}){
return (
<>

<p>{name}</p>
<p>{sound}</p>
<div onClick={() => handleAnimal}></div> // the function runs automatically when i am not making it a callback function => it needs to be a callback function () => function
</>
)
}

**Function:**

<Pet sound="Woof" name="Dog" onHandleAnimal={handleAnimal} />

passing a function as a boolean

**I can have values without passing them => it will not break the site**

{isHungry? "Feed me" : sound}

=> we can put that int the function as js in {}

=> if (isHungry = true) {render "Feed med! } else {} render sound}

Passing functions with **on** booleans with **is**
