# git-history-playground

## Move files
`git switch -c move` 
`git mv list.md new-list.md`


## Split files

`git switch -c split`
`git switch -c left`
`git mv list.md left.md`
`git commit -am "mv left.md"`
Remove unneeded content from `left.md`
`git commit -am "split left.md"`

`git switch split`
`git switch -c right`
`git mv list.md right.md`
`git commit -am "mv right`
Remove unneeded content from `right.md`
`git commit -am "split right.md"`


## Concat files

Starting from a branch that has `left.md` and `right.md` files
`git switch merge`
`git switch -c left`
`git mv left.md list.md`
`git commit -am "split left.md"`

`git switch merge`
`git switch -c right`
`git mv right.md list.md`
`git commit -am "split right.md"`

`git switch merge`
`git merge left right`
`git cat-file --filters left:list.md >list.md`
`git cat-file --filters right:list.md >>list.md`
`git add list.md`
`git merge --continue`