### react state 3

create unique id

=> npm package uid

=> import statement from documentation on top of the document
=> then call function and add it

remove movie in App

function handleDeleteMovie(id){
console.log("delete movie"); // test first then uncomment console.log

const filtered = movies.filter(movie => movie.id !== id) // it adds a movie to a new array if the id is not the same as the clicked id
setMovies(filtered) // we don't need a new array, because filter creates a shallow copy itself
}

=> add as a prop to element:
onHandleDeleteMovie={handleDeleteMovie}

in compoonent

add onHandleDeleteMovie as prop

=> in element: add onClick={() => onHandleDeleteMovie(id)} // must be an array function to be not called immediately
