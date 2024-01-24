### custom hooks

const [name, setName] = useState(() => localStorage.getItem('name') || '');

// sychnronizing the local storage with the input field

useEffect(() => {
windwow.localStorage.setItem('name' name)

}), [name]; // happens when name is updated

## a hook is just a function

use an abstracted hook to update the localStorage
=> then you can always use it again
