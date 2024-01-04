### js structure

```
export function CeaserCipher13(parameter)
```

```
import { caesarCipher13 } from './js/header.js';
```

## how to organize java script

- html has only the structure, it is very small
- everything in main is created in javascript
  => the js is separated in different files

## export functions

- if functions call other functions from different files they have to be imported
- `import { caesarCipher13 } from './js/header.js';`
- from: where to find the function
- in html => `<script module="defer"></script>`
- `const variable(functionTitle);`
- `export function CeaserCipher13(string)`
- to not confuse the elements with the function, functions which are exported are titled with a capital letter
- !: only functions which are exported

## functions in more than one file

- they should have a unique file
- main folder with shared js in different modules
- for example: folder "utils"
- the data should also be in another file
- modules in js should focus on one thing only => like in css

## import function export function

- usually in one file there is another file imported
- and beneath there is function exported to the file

## script.js becomes very small

## data

- data goes to another file called by the data
- export the data
- import the data in script.js
- if we import data as const it is not written with a capital letter
  => `import {data} from '../utils/data.js'`

### important:

- always make sure to pass all the necessary parameters to the functions

## export default function ...

- if we export more than one function in one file and call import the default it only imported
  => it can be renamed than
  => import variable form '../utils/...js'
  => for the import we don't need the curly brackets
  => `import variable from '../utils/...js'`
  => more files could be imported: `import variable {function} from '../utils/...js'`
