### react nesting

**everything is connected to passing props in react**

=> how can we pass a more complex structure to the elements we are creating

export default function App()
{
return (

<main>
<h1>Animal Shelter</h1>
<p>Please adopt our lovely pets!</p>
<Animal emoji="dogemoji" name="lucky" description={<p>Very cute dog</p>}> // we can pass a whole element in the function
<Animal emoji="turtleemoji" name="archibald" description={<ul>
<li>Very cute turtle</li>
<li>Very very cute</li>
</ul>}/>
</main>
)
}

function Animal({emoji, name, description}) {
return (
<> // there must be something wrapped around, with this element we don't create an extra html element

<h2>
{emoji} {name}
</h2>
{description}
<Button /> // i can also import functions in other elements
</Button>
);
}

=> <Button /> and <Animal /> // must be imported in App

## children prop

function UserCard({ children }) {
return <div className="card">{children}</div>;
}

// prop between opened and closed tag

=> if we use <Button> </Button> now, everything between is passed as children

<Button> Adopt {name} </Button> // Adopt {name} will be rrendered between the tag

## use case

// we can put this in the index.js => and take App as children

export default function Layout({children}) {
<>

<nav>This is my nav
</nav>
{children}
<footer>This is my footer</footer>
}

// In Index js we create the overall layout
<Layout><App /></Layout>

=> now layout is everywhere and App in between
