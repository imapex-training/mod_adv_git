## Remotes

A git repo may have many copies in various locations called remotes:

* URL reference to other copies of the repository
* most commonly github
* `origin` - automatically created remote when a repo is cloned
To view remotes configuration
```
cat .git/config
```
To add additional remote:
```
git add remote <name> <url>
```
Additional remote operations:

```
git remote --help
```

