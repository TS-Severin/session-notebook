h1### dynamic routes

routes are created by folder and file names

=> with next.js we can also use the functinality of the browser like back and forth

with slug in an arry i can create a linklist

=> how can i create the according sites

### file: **[slug].js**

=> could also be a folder [slug] => with index.js
=> but it is always dynamic

=> what does it do:

it catches everythig after the site above

**movies/[slug]**

=> slug is a variable

what do we do in the page to get the according content:

=> find the correct movie via find. => but we have to get the slug from the url

=>

import { useRouter } from "next/router"

const router = useRouter();

=> it gives me different information about the url
=> part of that is:

query: slug

const currentMovie = movies.find((movie) => movie.slug === router.query.slug);

=> now we accessed the array through the url

edge case for the case there is no movie, this is important otherwise it breaks

if (!currentMovie) {
return (
<>

<h1>this movie doesn't exist</h1>
<Link href="/movies">Back to all movies</Link>
</>
)
}

we can destructure slug at the beginneing

const {slug} = slug;

### how can i navigate as a function

=> like clicking a button that navigates the user to another site

<button
onClick={
() => {
if(confirm("Are you Aquaman")){ // confirm is a js functionality
router.push("movies/aquaman)
}}}> Are you Aquaman?</button>

// router.push puts the url in the browser => pushes a string after the actual domain
