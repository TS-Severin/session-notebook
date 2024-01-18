### react states 2

types of information in react

-prop => they are not changing => they are read only

-state => it is changing

=> if we want to know how the ui currently looks
=> we need to know the state

=> what piece of information do we need in order to tell the ui what it looks like

if there is a button:
=> we need to know if its clicked or not

if it doesn't change we don't need a state

**state is very important in computer science generally**
=> blockchain is about that

## we are dealing with the ui state

where do we locate the states in the code

## props passing parallel

we can't pass props to components on the same level
=> **lifting the state up**

prop: <Something propname={prop}>
propname is a variable

**call location state => state should be placed as near as possible where you use it**

## excurs array

const results = topics.filter((topic) => topic.includes(searchTerm));

=> topics.filter calls a callback function topic.includes
