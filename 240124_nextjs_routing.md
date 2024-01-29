### Next.js

-framework that uses react
-react is only frontend
-next.js has backend and frontend

-with react we have one url
-with next.js we can have multiple pages

-routing => getting from one page to another

## predefined structure

-folderstructure we have to follow
-nextjs.org
=> it has its versions and ihts documentation

We use: pages router

$npx create-next-app@latest

=> it asks for:
-name
-typescript ?
-wailwind => no
-src directory => yes
-App router => no
-customize the default import alias => depends on us

##folder system

=> $npm run dev => for seeing the project

### next js structure

src => pages => index.js

index.js => is the root folder

export default function Home() {
return (
<>

<h1>I am the about page</h1>
</h1>
);
}

=> this would be the about page now

        /    index.js
       /     about.js
       /     coridander.js

       => the name of the page defines the url

api-folder => it is the backend

=> next.js is build in react framework

\_app.js
\_documents.js

=> these are the files in next.js which run the whole file
=> they shouldn't be deleted but at the moment also not touched

Each default function needs to have the same name as the file:

animals.js

export default function Animals() {
return (
<>

<h1>Animals</h1>

    )

}

### how to create subpages of animals

if i have lots of routes the file needs to be a folder

Folder => animals
=> former page Animals =>
index.js
lion.js => export default function lion()
elephant.js => export default function elephant()

url: host/animals/lion

index.js => always corresponds to the root

folders with index.js-files structure the whole application

### personalize tab name

next.js has a component

import Head from 'next/head';
import animals from '../../data/animals.json'
import Link from 'next/link'

export default function Animals() {
return (
<>

<Head>
<title>Tab Title</title>
</Head>
<main>
<h1>List of Animals</h1>
<section>
{animals.map((animal, index) => 
<div key={i}> 
<Link href={`/animals/${animal.name.toLowerCase()}`}> // Link instead of a tag
<Image
src={animal.image}
alt={animal.name}
width={540} // we always have to give width and height in next.js
height={326}
/>
<h1>{animal.name}</h1>
</Link>
</div>
)}
</section>
</main>
)
}

<head>
<title>Title of tab</title>
</head>

### page Lion

export default function Lion() {
let animal = animals[0];
console.log('animal: ', animal);

    return(

<>

<Head>
<title>{animal.name}</title>
</Head>
<section>
<h1>{animal.name}</h1>
</section>

    )

}

### next.config.mjs

we have to give it the domains we are allowed to use

=> everytime we touch config => we have to rebuild the project
=> install next.js anew => ctrl + c => and install

images: {
domains: ['https://www.wikipedia.org']
}

=> all pages from wikimedia can be used now

ARRAY we are using includes links:

[
{
"name": "Lion",
"scientificName": "Panthera leo",
"diet": "Carnivore",
"habitat": "Grasslands, savannas, and forests",
"image": "https://upload.wikimedia.org/wikipedia/commons/7/73/Lion_waiting_in_Namibia.jpg"
},
{
"name": "Elephant",
"scientificName": "Loxodonta africana",
"diet": "Herbivore",
"habitat": "Savannas, forests, and deserts",
"image": "https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Elephas_maximus_maximus_-_01.jpg/640px-Elephas_maximus_maximus_-_01.jpg"
},
{
"name": "Tiger",
"scientificName": "Panthera tigris",
"diet": "Carnivore",
"habitat": "Forests, grasslands, and swamps",
"image": "https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Panthera_tigris%2C_2017_%28cropped%29.jpg/640px-Panthera_tigris%2C_2017_%28cropped%29.jpg"
},
{
"name": "Giraffe",
"scientificName": "Giraffa camelopardalis",
"diet": "Herbivore",
"habitat": "Savannas, grasslands, and forests",
"image": "https://upload.wikimedia.org/wikipedia/commons/thumb/8/89/Three_giraffes_01.jpg/640px-Three_giraffes_01.jpg"
}
]
