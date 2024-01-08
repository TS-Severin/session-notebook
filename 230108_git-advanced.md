### git advanced

git diff main <branch>
=> shows difference in terminal

=> who to esc info mode => press esc than q and :

=> if there are conflics on gitHub which makes it impossible to merge, we can merge locally

=> switch to branch which will be the one merged to <main>
=> which it should be incorporated to

git merge <branch feature>

=> merge feature to main

=> error message => code . => open merge editor in vs code
=> work with options in vsc
=> or delete lines created by git indicating the unresolved changes

=> in the end
git add .
git commit -m "fix conflict"

git push origin <branch>
=> possible to merge on gitHub

### array task

// orderedCount("abracadabra") == [['a', 5], ['b', 2], ['r', 2], ['c', 1], ['d', 1]]

function orderedCount(text) {
// create array without duplicates
const arr = [...new Set(text)];
// map over the array and replace every char with an array
return arr.map(char => [char, text.split(char).length - 1]);
// text.split(char).length - 1 => this part is the number of char in text

// add the character and the number of occurences to the arrays
}

orderedCount("abracadabra");

// [['a', 5], ['b', 2], ['r', 2], ['c', 1], ['d', 1]]],

// abrcd

// const str = "abracadabra"

// const arr = [...new Set(str)]

// map over arr
// -> [[], [], [], [], []]
// -> add the character itself in index 0 -> [['a']]

// -> [['a', 5]]

// const str = 'abbcbd'

// str.split('b').length - 1
