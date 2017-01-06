## Merge

* incorporate changes between branches


```
	  A---B---C feature
	 /
 D---E---F---G master
```

```
git checkout master
git merge feature
```

```
	  A---B---C feature
	 /         \
 D---E---F---G---H master
```
To undo a merge that has conflicts:
```
git merge --abort
```


