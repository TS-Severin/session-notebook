### react (or next.js) styled components

-there are different ways of managing css in react
-what we had is a dedicated css-file for every component
-yet another method => both can be used

## main takeaway => knowing different ways

=> best practices are constantly changing

styled-components.com

- how do we get css and react structure together

export default styled.button`

border: none;
curser: pointer
color: white`;

=> creates a button with the styling between ```
=> then we can import the button as <Button> => like another react component

## we can also style a component which already exists

## how to pass props to the component

$color can be a prop

<Button $color="danger">

styling:

`background-color: ${({color}) => 
$color === "danger" ? "var(--secondary-color)" : "var(--primary-clor)"};`

{$color} => destructured prop from the component

&:hover {
color: black;
background-color: var(--primary-background)
}

// the & is a placeholder for the component definded before => everything goes into ```

Sass

sass-lang.com => extended css language
=> scss

## styles.js

=> we create as file called styles.js instead of styles.css
=> global styles-file

in styles.js we can also create variables in
:root {
--primary-color: black;
}

with **props** we can set a default style an add optional style via prop ($color)

=> in the styled component the options are always a function

the $-sign in front of the prop is a convention

### we can nest components within components

=> list within container
=> export container
