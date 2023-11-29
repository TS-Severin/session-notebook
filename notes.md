### Git Branches

## create branch

`git switch -c <nameofbranch>`

The name of the branch must not include spaces

In my older version of git the command goes as follows:

`git checkout -b <nameofbranch>`

If unsure how the command is correct it is always possible to type in shell:

`git --help`

this is really useful because it simply shows the different commands available in the used git version

> After creating new branch add and commit the changes locally

## push branch

> this is the usual workflow if working with branches

`git push origin <nameofbranch>`

## merge branch

this is used to implement the changes made in the branch to the main branch which is the project

**Steps**

1. go to github
2. push button "pull request"
3. github automatically checks if it is able to merge
4. if it is able: push button "merge"

**_important_**

when working alone the main branch will not change

**but** when working with others it is important to constantly pull the main branch

## how to pull

`git pull`

## one more note

`git push -u origin <nameofbranch>`

the -u sets up an upstream but we already did this

so it is not necessary

but it saves you to write the origin each time

instead you can always include origin and <nameofbranch>
