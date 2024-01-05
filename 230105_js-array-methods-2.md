### js array methods

starting point: list

array of objects

## find

=> return the first matched element
=> dataType: array
=> we need a callback function

const array1 = [5, 12, 8, 130, 44];

const found = array1.find((element) => element > 10);

- => callback function in ()
- element is a local variable
- => could also refer to a certain key like element.age
- => age would be the key here

console.log(found);
// Expected output: 12

=> in contrary to filter find return only the first one not all

## findIndex

=> returns index of element in the array or -1 if it is not found
=> is used with a callback-function

const array1 = [5, 12, 8, 130, 44];
const isLargeNumber = (element) => element > 13;
console.log(array1.findIndex(isLargeNumber));
// Expected output: 3

## includes

=> returns a boolean => true || false
=> dataType: array
=> data in array

syntax:
array.includes(elementsWeAreSearchingFor);
=> elementsWeAreSearchingFor can be "string" or number or other dataTypes, "string" must be used with ""

## sort

=> sorts elements of an array ascending according to their value in UTF-16 code
=> it is sorted like the computer sorts folders and files
=> returns sorted array

used just with the elemnt:

const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// Expected output: Array ["Dec", "Feb", "Jan", "March"]

const array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);
// Expected output: Array [1, 100000, 21, 30, 4]

if we don't want the way the computer sorts it (UTF-16) we need a callback funciton:

() =>

a, b => a - b or b - a => depending on how we organize it

=> method sorts by comparing two elements as often as necessary in order to create the new array

a > b => compares first two (swaps if necessary), second two
=> does it again as long as it works
=> a - b => ascending
=> b - a => decending

examples:

const sortedByAge = studends.sort((a, b) => a.age - b.age);

.revers-method => putting .revers after the function => it sorts the same things the other way around

# sort by name

UTF-16 differenciates between upper and lower case => they have a different value

=> we first convert everything toLowerCase || toUpperCase and then compare them

const sortedByName = students.sort((a, b) => {
const nameA = a.name.toLowerCase();
const nameB = b.name.toLowerCase();
if (nameA < nameB) {
return -1
}
if (nameB > nameA) {
return 1;
}
return 0
});

# compare function in general alway operates with -1 and 1:

function compareFn(a, b) {
if (a is less than b by some ordering criterion) {
return -1;
} else if (a is greater than b by the ordering criterion) {
return 1;
}
// a must be equal to b
return 0;
}

## slice

**creates a copy of a function**

const sortedByAge = studends.slice().sort((a, b) => a.age - b.age);

=> slice modifies the original array
=> can be combined with other methods

## some

boolean: checks if a given element occurs in the array

const array = [1, 2, 3, 4, 5];

// Checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// Expected output: true

const AgeOverEighty = students.some(
(student) => student.points === 0
);

checks if a some student has 0 points

## every

returns boolean
asks if all elements meet a certain criteria

const everyStudentIsOderThanThirty = studends.every(
(student) => student.age > 30
);

handleSingleValue(
everyStudentIsOderThanThirty,
"everyStudentIsOderThanThirty"
);

### other methods

- forEach
- map
- filter
