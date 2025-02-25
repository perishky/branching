


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
```
