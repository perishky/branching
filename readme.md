## Branching 

```
git log --graph --oneline --all --decorate | cat
```

```
## create reade.md
git add readme.md
git commit -m "readme"
## * c97c514 (HEAD -> main) readme
git push
## * c97c514 (HEAD -> main, origin/main) readme
git branch b1
git checkout b1
## edit readme.md
git add readme.md
git commit -m "edit readme (b1)"
## * 03ae5b3 (HEAD -> b1) edit readme (b1)
## * c97c514 (origin/main, main) readme
git commit -m "edit 2 readme (b1)"
## * 8aa2767 (b1) edit 2 readme (b1)
## * 03ae5b3 edit readme (b1)
## * c97c514 (HEAD -> main, origin/main) readme
## edit readme.md
git commit -a -m "edit readme (main)"
## * a829979 (HEAD -> main) edit readme (main)
## | * 8aa2767 (b1) edit 2 readme (b1)
## | * 03ae5b3 edit readme (b1)
## |/  
## * c97c514 (origin/main) readme
git branch title
git checkout title
## add title to readme.md
git commit -a -m "add title (title)"
## * 4058e62 (HEAD -> title) add title (title)
## * a829979 (main) edit readme (main)
## | * 8aa2767 (b1) edit 2 readme (b1)
## | * 03ae5b3 edit readme (b1)
## |/  
## * c97c514 (origin/main) readme
git checkout main
git merge title
## * 4058e62 (HEAD -> main, title) add title (title)
## * a829979 edit readme (main)
## | * 8aa2767 (b1) edit 2 readme (b1)
## | * 03ae5b3 edit readme (b1)
## |/  
## * c97c514 (origin/main) readme
git branch -d title
## * 4058e62 (HEAD -> main) add title (title)
## * a829979 edit readme (main)
## | * 8aa2767 (b1) edit 2 readme (b1)
## | * 03ae5b3 edit readme (b1)
## |/  
## * c97c514 (origin/main) readme
git checkout b1
## edit readme.md
git commit -a -m "edit 3 readme"
```
