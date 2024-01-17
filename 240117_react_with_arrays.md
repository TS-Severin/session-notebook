### react with arrays

array for cards

=> the card information must be props
=> then we can send them to the cards

=> if we have a card container:

<card props="props" arrayElement="arrayElement"></card>

## array methods

// forEach
studends.forEach((element) => console.log("student: ", element));

// map
const newArray = students.map((element) => {return {...element, new: true}});
console.log("newArray: ", newArray);

=> it deconstructs the element and then adds a new key: value-pair

## problem about react: if the data is loaded by props sometimes it takes some time until the data is there

=> we can make that sure with an if statement
// map
const newArray = students && students.map((element) => {return {...element, new: true}});
console.log("newArray: ", newArray);

&& => means => if there are students => map
=> if not => undefined

<Card title={movies[0].title} />

=> title of first movie

=> that can be the whole element
function Movies return (
{movies.map((film)=> <Card title={element.title} />)}
);

=> and whe have to ask if the data exists
=> we need a key because the props have to be unique
=> if i have ids use them if not index
{movies && movies.map((element))=> <Card title={element.title} key={element.id} />)}

index:

{movies && movies.map((element, index)=> <Card title={element, index} key={element.index} />)}

That would be the surrounding array and function:

function Drinks() {
const drinks = ["water", "lemonade", "coffee", "tee"];

`return (

<ul>
{drinks.map((drink) => (
<li key={id}>{drink}</li>
))}
</ul>
);
}`

=> import array:
import {array} from "..."

=> array is as .js file and as const in data-folder

const movies = [
...
]
