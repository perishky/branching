## Branching 

The `git log` command provides graphical view of the commit history. 

```
git log --graph --oneline --all --decorate 
```

```
## create reade.md
git add readme.md
git commit -m "readme"
```

```
* c97c514 (HEAD -> main) readme
```

```
git push
```

```
* c97c514 (HEAD -> main, origin/main) readme
```

```
git branch b1
git checkout b1
## edit readme.md
git add readme.md
git commit -m "edit readme"
```
```
* 03ae5b3 (HEAD -> b1) edit readme
* c97c514 (origin/main, main) readme
```

```
git commit -m "edit 2 readme"
```

```
* 8aa2767 (b1) edit 2 readme 
* 03ae5b3 edit readme 
* c97c514 (HEAD -> main, origin/main) readme
```

```
## edit readme.md
git commit -a -m "edit readme"
```

```
* a829979 (HEAD -> main) edit readme
| * 8aa2767 (b1) edit 2 readme 
| * 03ae5b3 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git branch title
git checkout title
## add title to readme.md
git commit -a -m "add title"
```
```
* 4058e62 (HEAD -> title) add title 
* a829979 (main) edit readme
| * 8aa2767 (b1) edit 2 readme 
| * 03ae5b3 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git checkout main
git merge title
```
```
* 4058e62 (HEAD -> main, title) add title 
* a829979 edit readme 
| * 8aa2767 (b1) edit 2 readme 
| * 03ae5b3 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git branch -d title
```

```
* 4058e62 (HEAD -> main) add title 
* a829979 edit readme 
| * 8aa2767 (b1) edit 2 readme 
| * 03ae5b3 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git checkout b1
edit readme.md
git commit -a -m "edit 3 readme"
```

```
* 5d1bc0e (HEAD -> b1) edit 3 readme
* 8aa2767 edit 2 readme 
* 03ae5b3 edit readme 
| * 4058e62 (main) add title 
| * a829979 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git checkout main
git merge b1
```

The merge fails due to a conflict between the branches.

```
Auto-merging readme.md
CONFLICT (content): Merge conflict in readme.md
Automatic merge failed; fix conflicts and then commit the result.
```

The conflict is identified in 'readme.md'  using the following notation:

```
 ...
 <<<<<<< HEAD
 conflicting text in main
 =======
 conflicting text in b1
 >>>>>>> b1
 ...
```

```
## edit readme.md to resolve the conflict
git commit -a -m "merge b1"
```

```
*   df561c7 (HEAD -> main) merge b1
|\  
| * 5d1bc0e (b1) edit 3 readme
| * 8aa2767 edit 2 readme 
| * 03ae5b3 edit readme 
* | 4058e62 add title 
* | a829979 edit readme 
|/  
* c97c514 (origin/main) readme
```

```
git push
```

```
*   df561c7 (HEAD -> main, origin/main) merge b1
|\  
| * 5d1bc0e (b1) edit 3 readme
| * 8aa2767 edit 2 readme 
| * 03ae5b3 edit readme 
* | 4058e62 add title 
* | a829979 edit readme 
|/  
* c97c514 readme
```

```
git branch -d b1
```

```
*   df561c7 (HEAD -> main, origin/main) merge b1
|\  
| * 5d1bc0e edit 3 readme
| * 8aa2767 edit 2 readme 
| * 03ae5b3 edit readme 
* | 4058e62 add title 
* | a829979 edit readme 
|/  
* c97c514 readme
 ```

