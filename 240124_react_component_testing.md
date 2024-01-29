# react component testing

### test pyramid

- ent to end testing => what happens when i do strage stuff to it
- integration test => component test
- unit testing => made for functions
- static syntax checking

> when manually checking stuff it is likely to miss something

### automated tests

- you can simply run them in the terminal
- they can proof an app is running to the client

### test syntax:

```js
import Movie from ".";
import { render, screen } from "@testing-library/react";

test("renders a movie", () => {
  render(<Movie name="The Matrix" />);
  screen.getByText("The Matrix");
  expect(matrixHeading).teBeInTheDocument();
});
```

=> screen is imitating a screen/browser

=> i do in testing what i would do manually => open browser and looking for the headline

> if tests are done accuratly they can serve as a tasklist for a whole appliction

### Test for role

```js
import Movie from ".";
import { render, screen } from '@testing-library/react

test("renders a movie", () => {render(<Movie name="The Matrix" />)
screen.getByRole('heading', {name: 'The Matrix Reloaded')
expect(matrixHeading).teBeInTheDocument()
});
```

-> testing for: is there a heading on the screen with the name of "The Matrix"

```js
import userEvent from "@testing-library/user-event";

test("renders a new movie when the form is submitted with a new movie name", async () => {
  render(<Movie initialMovies={initialMovies} />);
  const user = userEvent.setup();
  const input = screen.getByLabelText("Name");
  await user.type(input, "The Matrix");
  const button = screen.getByRole("button", { name: "Add" });
  await user.click(button);

  const matrixHeading = screen.getByRole("heading", {
    name: "The Matrix",
    level: 2,
  });
  expect(matrixHeading).toBeInTheDocument();
});
```

### test fetching

=> we provide static data instead of the api => we overwrite the fetch-function
=> we abstract form the side effects that could be caused by the api

=> usually one also overwrites the useRouter-components
